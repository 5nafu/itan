itan
====

A small project to store an iTAN list gnupg encrypted. Written in Python

Dependencies
------------

You will need the following python modules:
* `json` -> Used to convert the decrypted string to a dict
* `gnupgp` -> to decrypt the file, obviously
* `getpass` -> to get the decryption password without printing it to the console
* `sys` -> exit and stuff

Assumptions
-----------

The script, at the moment, expects to find an encrypted file `iTAN.gpg` in the Users $HOME
Unencrypted, the script expects a json in the form:

```
{
'1': '225144',
'2': '209194',
'3': '364148',
'4': '213591',
'5': '324204',
'6': '134943',
'7': '150252',
'8': '999176',
'9': '232473',
'10': '187248',
'11': '208301',
[...]
'100': '208301'
}
```

**REMEMBER: Put the TAN and IDs in quotes. Leading 0 will cause errors otherwise; Do not add a comma to the last key/value pair**

Additionally the script expects the tan id to be within the range of 1 to 100.

Usage
----

You can either specify the TAN on the command line

    itan <tanid>

or you will be asked for a tan.

You will also be asked for a password to decrypt the tanlist.

