<!-- Filename: J5.x:Enhancing_Password_Security_with_Symbolic_Characters / Display title: User Password Security -->

## Introduction

In the *Users: Options* form *Password Options* tab the minimum values for 
*Numbers*, *Symbols*, *Upper Case* and *Lower Case* are all set to 0 by default.
For better security these values should be set to 1. New or changed passwords 
must then include one of each of these characters.

## Symbols

The *Open Worldwide Application Security Project* (OWASP) recommends that all 
special characters available on a standard US keyboard are recognized and 
accepted when setting password requirements. 

```
 !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~
 ```

It is not obvious, but this list includes the space character.

[OWASP: Password Special Characters](https://owasp.org/www-community/password-special-characters)

Prior to version 5.2 these symbols could be used in passwords but some of them
were not recognised as symbols for password validation purposes: 
```
@[]£^+±~<>/'",.
``` 
