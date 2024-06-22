<!-- Filename: https://magazine.joomla.org/all-issues/april-2021/best-practices-to-secure-your-joomla-website / Display title: Best Practices -->

## Security Articles

There are a significant number of articles available on Joomla security going
back many years. Unfortunately, many of them are out of date and perhaps
misleading. For example, there is a series of Security Checklist articles not all of which are actually
about security.

This article is based on a Joomla! Community Magazine article by Ahmad Moussa
in the April 2021 Edition.

## Best Practices to Secure your Joomla Website

Joomla Content Management System (CMS) is widespread on the internet due to its ease of use and popularity since it is the second-largest CMS downloaded over 110 million times. But, even though popular, Joomla and all other websites, apps, eCommerce sites, or other CMSs contain security risks. You cannot escape them but fortunately taking the right precautions from the start can ensure your site is protected.

We compiled this comprehensive and step-wise guide on Joomla security for you. It intends to provide easy-to-follow steps to enhance your Joomla website security. So, if securing your Joomla website from all coming attacks is on your agenda, then give it a read. All tips mentioned in this article are to ensure you’re implementing the best security and maintenance practices to protect your most important assets online.

## 1. Choose Smart Usernames and Passwords

Be smart while choosing your Joomla admin usernames and passwords. Don't use "admin" as your username and choose a complex password. This is probably one of the best ways to harden your Joomla security, and ironically it is one of the easiest.

Using a secure password is necessary for healthy Joomla security. Make sure your login password is long enough (8-14 characters) and includes alphabets, numbers, and symbols. Since, passwords are case sensitive, using both uppercase and lowercase letters make it even stronger. Further, make it a habit to change admin passwords at least once a month.

## 2. Practice the Principle of Least Privilege

Make sure you understand the three distinct permissions groups:

1. Managers: Have the least access to the backend of Joomla. Can create and edit categories and articles. Have access to the media manager and can upload and remove media. Cannot install or remove extensions.
2. Administrators: Have all the rights Managers have, along with a few additional permissions. Have access to the User Management, Menu Manager and Extension Manager. Cannot access the Joomla Global Configuration menu.
3. Super Users: Have full access to the Joomla Backend. Have all the rights of Managers and Administrators, along with access to the Global Configuration. Only Super Users can add, edit, and remove Super Users.

It is important that you distribute these roles carefully to your group of users. Anyone with a Super User role is able to perform any action within the Joomla system. If you delegate tasks to a team member that requires fewer permissions, assign the member’s account with the minimum access description.

## 3. Use Joomla Multi-Factor Authentication

It’s highly recommended to enable Joomla Multi-factor authentication which adds an extra security layer to your Joomla website. Traditionally, when you want to log in to your website, you have to provide your username and password in order to identify yourself in the system. The biggest problem with this approach is that your username and password can be stolen or guessed. Therefore, the Joomla Multi-factor authentication plugins can protect your website from hackers by adding a second layer of security. There are five different methods for you to choose from after entering your username.

## 4. Restrict Access to Joomla Admin Backend

It is wise to limit access to the Joomla admin backend using IP filtering since it is a sensitive resource. This can also be done for other sensitive folders of Joomla by following the steps mentioned below:

Step 1: Firstly create a .htaccess file if not already present in the directory you wish to protect.

Step 2: Add the following code to the .htaccess file:
    ```
    Order Deny, Allow
    Deny from all
    Allow from xx.xx.xx.xx
    ```

Step 3: Enter the dedicated IP address you wish to allow access from in place of the xx.xx.xx.xx.

More information about restricting directory access by IP address using
htaccess can be found in this Joomla! Documentation
article. You may also use security extensions that can restrict access to the Joomla admin backend using the IP filtering feature and includes many other features which strengthen your Joomla website security.

## 5. Use Secure FTP Connections

Ensure that the connections used to access your Joomla website files are secured. You should use SFTP encryption if your hosting provides it, or SSH. If you are using an FTP client then the default port for SFTP is usually 22.

Some FTP clients store passwords in plain text or encoded on your computer. Even some encoded passwords can be converted back to the original. We strongly recommend not saving FTP passwords in the client to avoid being hacked.

## 6. Take Regular Backups

Save time by preparing for the worst-case scenario in case your website gets attacked. Therefore it is advised to create a complete working backup of your Joomla website. A functional backup can restore your website in minutes after a cyber attack.

The two main components of a backup are:

- Joomla Core and other important files
- The Database

Further, the methods of backing up can be flexible too. You can take a backup either in the two ways – Manual and Automated, as described below:

### Manual Process

The manual backup of the Joomla site needs two components: files and the database. To backup your Joomla files and folder, use an FTP utility or the file manager in case you use third-party hosting.

FTP clients can download all the files one by one to your local machine. However, this process may be slow. Once the files have been downloaded, compress the folder into a single zip file then password protects it.

While the database can be backed up by exporting a copy of the database to your computer. Log in to the database that you want to export using phpMyAdmin. Click the database name on the left-hand side of the page. Once you have clicked on your Joomla database, you should come to a screen that has a tab labelled “Export”. Select the Export tab then click on the button labelled "Go". Then save it to a secure location.

### Automated Process

For automated backup, a Joomla extension like Akeeba Backup can help. Install Akeeba Backup extension on your Joomla website after downloading it from the developer official site. After the installation is complete, access the extension Dashboard then backup your site. When the backup is complete, you will be redirected to a page. Here, click on “Manage Backups”. This will open up a page containing all the backups. You can download the backup from here and save it locally.

## 7. Keep Your Joomla Website Updated

Updating your Joomla website can provide security and stability to the site. Further, not all updates are full site version updates; a few updates may be minor and are simply bug fixes, while others are version updates.

Joomla has a dedicated security team that is known for rolling out patches quickly. Not patching your Joomla website can make it vulnerable to hacking.

To check your site for updates you can do the following:

Step 1: Log in to your Joomla site as the administrator

Step 2: Thereafter, navigate to Components>Joomla Update

Step 3: Now, Joomla will check if any new update is available. If it shows a new update, simply click on “Install the Update” option.

Before updating to a newer version of Joomla certain things should be checked up:

- Templates Update: Check if your Joomla templates are compatible with the newer Joomla version. If not, ask the template author to update it or use an alternative.
- Extensions Update: Inspect and make sure that all the Joomla extensions are compatible with the newer Joomla version. Remove all those which are not compatible. To update the extensions, navigate to Extensions>Manage and click on update.
- Clear Cache: After updating to a newer version of Joomla, clear the cache from your Joomla site. This can be done using the inbuilt functionality of Joomla.

## 8. Use Trusted 3rd-Party Extensions and Templates:

It is recommended to use a minimum number of extensions on your website to get the optimal Joomla security level. Using untrusted 3rd-party extensions or templates might pose vulnerabilities and affect your Joomla website performance. Not all 3rd party extensions are free from trouble; if you have the luxury of avoiding a 3rd-party extension, do so! Choose and use professional extensions and templates from reputable companies, and keep them updated to protect your website.

## 9. Update PHP Version of your Joomla website

Protect your website from a variety of hacking attacks and strengthen your Joomla site security by updating your site's PHP version to the latest stable release. Make sure to select a PHP version that is compatible with your Joomla templates and extensions to prevent breaking your site. There's a variety of ways to update your PHP version. The main ones are covered in an article in the September 2020 issue of Joomla Community Magazine: How do I update my PHP version?.

## 10. Harden HTTP Security Headers

It is highly recommended to implement or update HTTP security headers as they provide a layer of security for your Joomla site by helping to mitigate attacks and security vulnerabilities. They usually only require a small configuration change on your web server. These headers tell your browser how to behave when handling your site's content. Below are six common HTTP security headers to be reviewed:

- Content-Security Policy
- X-XSS-Protection
- Strict-Transport-Security
- X-Frame-Options
- Public-Key-Pins
- X-Content-Type

## 11. Use a Joomla Security Extension

It is necessary to limit the login attempts on the Joomla admin backend to avoid brute force attacks to your Joomla website. This can be implemented by various Joomla security extensions that protect your website administrator backend from hacking attempts. You may find such extensions in the Joomla Extensions security list category.

## 12. Choose a Secured Hosting Provider

Make sure that the hosting provider you choose implements Joomla security safeguards. If you choose a shared hosting, make sure that subnetting is implemented taking into consideration Joomla security. Purchasing a shared cheap hosting provider might not be an ideal starting point since your site will be slower, subject to spam due to a 'bad neighbourhood' of sites with low reputation, and might get compromised if other sites got hacked. Also while choosing a hosting plan, check for various parameters like customization, support, reviews, etc.

## 13. Use SSL to Boost Joomla Security

It is highly recommended to install an SSL (Secure Socket Layer) certificate on your website since it will encrypt the communication between your Joomla site and your visitor's browsers. Get an SSL certificate from a verified certifying authority and make sure that all your HTTP traffic is redirected to HTTPS. To do so, append the following code to your .htaccess file:

```
# Redirect HTTP to HTTPS
RewriteEngine On RewriteCond %{HTTPS} off
RewriteCond %{HTTP:X-Forwarded-Proto} !https
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

## 14. Frequent Joomla Security Audit

It is extremely important to uncover vulnerabilities before a hacker does in order to keep your Joomla website safe and secure. This can be done by choosing a professional security audit tool that can save you a lot of time managing your websites. Meticulous security audits are a great way to enhance your Joomla security. Many services do this by automating tasks such as creating website backups, scanning for signs of intrusion, and bulk-updating the extensions you trust. It can also scan your site for the use of security best practices, and perform a deep scan to look for potential security threats. These services use an optimized mix of manual and automated mechanism to discover vulnerabilities in your Joomla site.

## 15. Check Post-installation Messages

It’s highly recommended to read all post-installation messages since the Joomla Team is providing you with important information that needs your attention after upgrading, or after installing Joomla for the first time. These messages mostly contain Joomla security configurations or file changes that should be made manually and which an upgrade can’t change.

## 16. Get to Know the Vulnerable Extensions

Always check the Vulnerable Extensions List website and its social media pages in order to know the latest security risks and possible patches. It’s recommended to uninstall any extension listed in the Vulnerable Extensions List for which no patch is known to exist. Make sure to update your vulnerable extension whenever its patch is available. If your site uses a vulnerable version of an extension that doesn’t have a patch update, then you are recommended to replace it.
Conclusion

Because there will always be risk, Joomla security will remain a continuous process, requiring frequent assessment of possible attack carriers. Website owners and administrators should always improve their website security in order to reduce the risk of a compromise.

