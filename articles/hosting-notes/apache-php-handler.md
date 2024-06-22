<!-- Filename: J4.x:Apache_PHP_Handler / Display title: Apache PHP Handlers -->

## Notes

To determine which method your web server is using to handle php files
use the **Administrator / System / System Information* links and select the PHP
Information tab. Search the page for **Server API**. The common ways for
an Apache web server to handle PHP files include the following:

### DSO (mod_php)

- **Advantage:** one of the fastest handlers available.
- **Disadvantage:** only works with a single version of PHP; files saved
  by php scripts are owned by the Apache user **except** when used in
  conjunction with mod_ruid2.
- **To recognise:** Server API - Apache 2.0 Handler

### CGI/FastCGI

- **Advantage:** scripts run as the domain or subdomain user, very fast
  handler.
- **Disadvantage:** slower than mod_php, cannot put PHP configuration
  changes in an .htaccess file.
- **To Recognise:** Server API - CGI/FastCGI

### FPM/FastCGI

- **Advantage:** very fast, additional level of flexibility.
- **Disadvantage:** uses more memory than most of the others, cannot put
  PHP configuration changes in an .htaccess file.
- **To Recognise:** Server API - FPM/FastCGI

### LSAPI (mod_lsapi)

- **Advantages:**
   - Provides support for caching.
   - It is the most performant handler with a low memory footprint.
   - No configuration is required.
   - It can work with multiple PHP versions in a single setup.
   - It supports PHP configuration directives through .htaccess files.
   - Secure because scripts execute as the domain owner.
- **Disadvantages:**
   - It does not make available all LSAPI capabilities.
- **To Recognise:** Server API - ?

On a local laptop or desktop computer you can use mod_php but you may need
to set the Apache user to your own username and point the document root
to a location in your own file space. Otherwise you will have file and
folder permissions problems.

On a hosting service you need to use one of the FastCGI alternatives or LSAPI.
Hosting services may give you a choice.
