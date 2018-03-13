#### Note: I no longer have the time to continue development of Passera, but pull requests are more than welcome! The number one requested item would be an updated Firefox extension, since the latest API change broke the current release.

# Passera

A simple tool that allows users to have strong unique
passwords for each website, without the need to store them either
locally or with an online service. It is available as a command-line tool for Linux/Mac/Windows and an Android app.

Passera turns any entered text into a strong password up to 64
characters long and copies it to clipboard. Figure out a decent system
for yourself that will allow unique passphrases for every website, such
as combining website name/URL with a phrase that you would not forget.
To login, fire up Passera and enter the passphrase you chose and your
real password will be copied to clipboard.

#### Turn `MyFancy#Github%password` into `@ZfKS*ePs1ll9yRG`

This software is for privacy-aware people who understand the need to
have strong unique passwords for each website, yet don't want to use
any password managing software or services. Relying on password managing software means trusting your passwords to be kept safe by a third-party
company, or trusting them to a single file on your disk.

<p align="center">
  <img alt="Passera" title="Passera for Linux/Mac/Windows/Android" src="http://mw.gg/i/passera_full_logo.png" />
</p>

To make it somewhat more conspicuous, when you start Passera it copies
a random password to clipboard. The real password is then only stored
in clipboard for 10 seconds, before being overwritten by another
random string.

## Password security considerations

Passera is not designed to produce a hash of a given string by reinventing the wheel of cryptography. Instead, it produces a unique string of specified length, suitable for usage as a strong password. The cryptographic methods used are ensuring that the produced passwords are as "random" as possible, and are absolutely impossible to trace back to original passphrases.

When it comes to cryptography, a password's security is multiplied by the complexity of the passphrase. Users are strongly advised to use passphrases that would be to unique to them. This can be achieved by including "keywords", such as email addresses, pet names, city names, etc. This ensures that passphrases are personal to each individual user.

Passwords produced by Passera, being random combinations of symbols, are impossible to brute-force, since it would take an extremely long time (as opposed to using combinations of real words and sentences as passwords). If a password gets leaked from a compromised website, an attacker would not be able to determine any of your other passwords. And if the attacker is aware that Passera has been used to create the password, brute-forcing with intent to find out the original passphrase would also take an extremely long time due to the nature of the cryptographic algorythms.

Passera does not ask for a website URL or a "master password" when generating a password, because these values would be included into the hashing algorithm in a particular way, potentially known to an attacker. Instead, users have the freedom to combine anything in any order, shape or form in the initial passphrase, making it exponentially more difficult to brute-force, to the point of being impossible.

## Downloads
Direct download links to the latest builds.

#### Command line tool

* [Linux executable](http://mw.gg/d/passera-linux.tar.gz "Passera for Linux") (i386/x64/ARMv7)
* [Mac OSX executable](http://mw.gg/d/passera-osx.tar.gz "Passera for Mac OSX") (i386/x64)
* [Windows executable](http://mw.gg/d/passera-windows.zip "Passera for Microsoft Windows") (i386/x64)

#### Firefox extension

Requires Firefox 30+

* [Download from Mozilla Add-Ons](https://addons.mozilla.org/en-US/firefox/addon/passera/)

#### Android app

Requires Android 3.0+

* [Download from F-Droid](https://f-droid.org/repository/browse/?fdid=gg.mw.passera "Passera for Android on F-Droid")

## Command-line tool
The software does one thing and does it good. Fire it up and it will
prompt you for the passphase you chose for a particular service you
wish to login. It will produce your password and copy it to clipboard,
counting down from 10 seconds before overwriting it with a fake one.
```
$ passera
>> 
Copied to clipboard
Clearing in 9
```

Specify password length (defaults to 16):

```
$ passera -l 64
```

Disable copying fake passwords to clipboard before and after the real password:

```
$ passera -d 
```

Disable copying passwords to clipboard altogether, only show the real password on the screen (not saved in bash history):

```
$ passera -s
```

Specify time delay (in seconds) before clipboard is replaced with a phony password (keep in mind it may be overwritten by other programs): 
```
$ passera -t 60
```

Create a password without special characters ($, ^, @, !, etc.):
```
$ passera -c
```

Enter passphrases twice to ensure correct entry:
```
$ passera -v
>> 
>>> 
Copied to clipboard
Clearing in 9
```
Or otherwise:
```
$ passera -v
>> 
>>> 
Passwords did not match
```

## Firefox extension

Allows you easy access to Passera when using Firefox. It is self-explanatory and behaves in similar ways to the command-line tool and is almost identical to the Android app. In the current version it is only possible to show the generated password and manually copy it to clipboard. In future versions it will be possible to transfer the password directly to the chosen password fields on a webpage.

![Passera on Android](http://mw.gg/i/passera_firefox_24aug14.png)

## Android app
The new Android app for Passera has been released. It can copy generated passwords to clipboard or show them on the screen. You may find password generation being fairly slow on some devices, this is due to the nature of the cryptographic algorithms working behind the scenes and is a required redundancy to keep your passwords unhackable.

![Passera on Android](http://mw.gg/i/passera_android_2aug14.png)

## To Do & WIP:
* Linux/Mac/Windows GUI

### Known issues:
* Windows i386 binary generates improper passwords, not recommended for use. Windows x64 binary appears to work properly.

### Changelog:

##### August 9, 2014:
* Passera Android app added to F-Droid FOSS catalog/repo.

##### August 1, 2014:
* Linux ARMv7 binary added.

##### July 31, 2014:
* Android app released.

##### July 24, 2014:
* Added/updated binaries for Linux/Mac/Windows i386/amd64.

##### July 22, 2014:
* Added `-c` option to create passwords without special characters.
* Behaviour of the `-s` option changed, shown passwords no longer saved in bash/terminal history and gets overwritten after 10 seconds (or other amount of time specified by the `-t` option).
*Added `-v` option to verify entered passphrases twice, to ensure correct input when setting password on a website.

-----
<p align="center">
<img alt="Bitcoin" title="Donate with Bitcoin" src="http://mw.gg/i/bitcoin.png" /> 3HrjGijbDvhxSNZXZkmAqBH7eFfKyXRmfm</p>
