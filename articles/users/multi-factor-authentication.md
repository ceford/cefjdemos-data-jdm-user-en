<!-- Filename: J4.x:Multi-factor_Authentication / Display title: Multi-factor Authentication -->

## Introduction

The Joomla! Multi-factor Authentication system is based on Akeeba
Loginguard and much of this documentation has been derived with
permission from Akeeba.

## What does it do?

It adds multiple, optional Two Step Verification methods for Joomla!
login. After logging in with just your username and password you are
asked to provide your second step verification, for example a code
generated by Google Authenticator. Until you provide a correct second
step verification you will not be able to access any pages on the site.
You will always be redirected to the "captive login" page. This is
similar to what Google does when you try to login to GMail.

This differs from the original Joomla! two factor authentication method
which required the second authentication factor (e.g, the code generated
by Google Authenticator) to be entered together with the username and
password.

The advantages of Two Step Verification are:

- It is less confusing for the user. There is no longer a need for the
  "Secret Key" field which confuses users.
- It can work with non-password login methods such as social login (e.g.
  Facebook), secure hardware token, SSO (single sign-on) etc.
  Clarification: Two Step Verification can be configured to be requested
  after a user logs in with a non-password login method. It does not
  implement non-password login methods.
- It has better access control. You can set User Options to Require or
  Disable Multi-factor Authentication by user group.
- It allows alternative authentication methods in a single account. You
  can have several authentication methods on your account. For example
  you may set up a Google Authenticator app and a YubiKey.
- It supports methods which do not require entering a code. For example
  FIDO2 dongles, biometric verification etc. These need to interact with
  the browser and/or the operating system through native HTML5 APIs.
- It supports methods which require user interaction. For example
  sending a code via push message, SMS or email. These methods require
  knowing which user is being authenticated before pushing the
  authentication code to the user.
- It is free of charge. Unlike third party services providing
  multi-factor authentication you do not have to pay an upfront setup
  fee or a monthly / yearly maintenance fee for each site or user using
  Two Step Verification. The software is free of charge.

## How does it work

You log in to your site normally, for example by providing a username
and password. It is important to note that you do not need to enter your
second step authentication credentials at this stage.

The system detects that you are now logged in but have not performed the
second step authentication. It stores the URL you were supposed to see
and immediately redirects you to the captive login page. Any attempt to
navigate to a different page will result in the captive page appearing.

Modules on your site can contain privileged information. To ensure
confidentiality, modules are forcibly deactivated at render time. This
means that no module position will be rendered on the page. Remember
that in case you notice the header or other key design areas of your
site are missing in the captive login page.

Do note that plugins, on the other hand, are NOT disabled. This is both
because Joomla makes it extremely hard to remove specific plugins once
they are loaded and because most plugins perform critical functionality
on your site.

After providing your second step verification a flag is set in the user
session, indicating that you are fully authorised to use the site.
Moreover you will be redirected to the URL it stored right after you
initially logged in.

## Two Factor Authentication versus WebAuthn logins

Logging in with WebAuthn is the most secure option. You only provide a
username which is supposed to be considered public, unprivileged
information. The site creates a cryptographic challenge which is signed
by the browser using secure hardware — an external secure hardware token
or the Trusted Platform Module / Secure Enclave of your device — and
returned to the server. The server validates the signature. This
validation uses public key cryptography with the site only storing the
public key. This makes the login virtually unphishable and extremely
secure. If you use that you don't need a second authentication factor —
but if you really want to, you can use WebAuthn for it too.

Barring the use of any federated login methods (such as logging in with
your social media account, a Single Sign-On service, an LDAP server etc)
a conventional username + password login is nowhere near as secure as a
WebAuthn login. Entering a username and a password can be intercepted,
stolen or guessed. This makes trusting just a username and a password
very problematic.

For Multi-factor authentication you only provide your username and
password. A successful phishing attack would only get this first
authentication factor but not your second authentication factor. After
successful login you are presented with a captive page. You cannot do
anything else on the site until you provide your second factor. Since
the second factor input is presented in its own page it can be
interactive (e.g. WebAuthn), asynchronous (e.g. receiving an OTP via
email, text message or push notification) or user-initiated (e.g. a TOTP
or a Yubikey OTP). Even better, a user can have multiple second factor
methods enabled on their account to prevent accidental lockouts from the
site. For example, you may be using WebAuthn with an external secure
hardware dongle as your primary, most secure second factor. You could
also have a regular TOTP set up in case you lose the dongle or forget to
take it with you. Some second factor methods allow for multiple
instances, for example you can have multiple WebAuthn authenticators so
you can use the built-in authenticator in your Windows computer, your
iPhone and your Android tablet without having to remember to pack a
hardware dongle and adapters every time you leave your desk.

Let's recap. From most secure to least secure your options are:

- WebAuthn as your primary login method with secondary Multi-factor
  Authentication.
- WebAuthn as your only login method.
- Username and password as your primary login method with secondary
  Multi-factor Authentication.
- Just a username and password as your only login method.

## Plugins

Each of the factors in Multi-factor Authentication is implemented via
plugins. They can be enabled or disabled as required. And new ones added
when new methods come along. The plugins shipped with Joomla core
include:

- **Verification Code**: six digit verification codes generated by an
  authenticator app (Google Authenticator, Authy, LastPass
  Authenticator, etc), a password manager (1Password, BitWarden, Keeper,
  KeePassXC, Strongbox, etc) or, in some cases, their browser.
- **YubiKey**: Allows users on your site to use Multi-factor
  Authentication using a YubiKey secure hardware token. Users need their
  own YubiKey available from www.yubico.com.
- **Web Authentication**: supported by all modern browsers. Most
  browsers offer device-specific authentication protected by a password
  and/or biometrics (fingerprint sensor, face scan, ...).
- **Authentication Code by Email**: Use time limited, six digit security
  codes sent to you by email. The default setting is 2 minutes.
- **Fixed Code**: this is intended for testing and illustration and is
  disabled by default. It should not be enabled on a production site.

Note that there is a separate **System - WebAuthn Passwordless Login**
plugin to handle login from the Web Authentication button in the login
form.

## Users Options

The Users: Options form has a Mult-Factor Authentication form to
Configure how Multi-factor Authentication works in Joomla. Select the
Toggle Inline Help button for information about each option.

<img
src="https://docs.joomla.org/images/thumb/6/66/J4.x-multi-factor-authentication-user-optionsen.png/800px-J4.x-multi-factor-authentication-user-optionsen.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/6/66/J4.x-multi-factor-authentication-user-optionsen.png 1.5x"
data-file-width="1000" data-file-height="1673" width="800" height="1338"
alt="Screenshot of users options multi factor authentication settings" />

## User Profile

The Administrator / Users: Edit Profile form has separate tabs for
WebAuthn Login and Multi-factor Authentication but the latter is only
visible to the account owner. Even Super Users do not see this tab for
other users.

The Site / Edit Your Profile form has the backend form tabs laid out one
above the other, which can be confusing because Web Authentication
appears twice, first for passwordless login and second for Multi-Factor
Authentication. The following illustration shows the Multi-factor
Authentication part of the form after a method has been created. That
automatically sets the feature to Enabled and shows the option to create
Backup Codes.

<img
src="https://docs.joomla.org/images/thumb/0/0b/J4.x-multi-factor-authentication-user-profileen.png/800px-J4.x-multi-factor-authentication-user-profileen.png"
class="thumbborder" decoding="async"
srcset="https://docs.joomla.org/images/0/0b/J4.x-multi-factor-authentication-user-profileen.png 1.5x"
data-file-width="1000" data-file-height="1371" width="800" height="1097"
alt="Screenshot of an individual user multi factor authentication form" />

As mentioned above, you can try each out by selecting the + Add ...
button, but select Cancel in the subsequent form if you decide not to
proceed.