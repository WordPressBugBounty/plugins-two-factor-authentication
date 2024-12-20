=== Two Factor Authentication ===
Tags: two factor, 2fa, tfa, two factor auth, google authenticator
Requires at least: 3.4
Tested up to: 6.7
Stable tag: 1.14.27
Requires PHP: 5.6
Author: DavidAnderson
Contributors: DavidAnderson, DNutbourne
Donate link: https://david.dw-perspective.org.uk/donate
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Secure WordPress login with Two Factor Authentication - supports WP, Woo + other login forms, HOTP, TOTP (Google Authenticator, Authy, etc.)

== Description ==

Secure WordPress login with this two factor authentication (TFA / 2FA) plugin. Users for whom it is enabled will require a one-time code in order to log in. From the authors of <a href="https://updraftplus.com/">UpdraftPlus - WP's #1 backup/restore plugin</a>, with over two million active installs.

Are you completely new to TFA? <a href="https://wordpress.org/plugins/two-factor-authentication/faq/">If so, please see our FAQ</a>.

Features (please see the "Screenshots" for more information):

* Supports standard TOTP + HOTP protocols (and so supports Google Authenticator, Authy, and many others).
* Displays graphical QR codes for easy scanning into apps on your phone/tablet
* TFA can be made available on a per-role basis (e.g. available for admins, but not for subscribers)
* TFA can be turned on or off by each user
* TFA can be required for specified user levels, after a defined time period (e.g. require all admins to have TFA, once their accounts are a week old) (<a href="https://www.simbahosting.co.uk/s3/product/two-factor-authentication/">Premium version</a>), including forcing them to immediately set up (by redirecting them to the page to do so)
* Supports front-end editing of settings, via [twofactor_user_settings] shortcode (i.e. users don't need access to the WP dashboard). (The <a href="https://www.simbahosting.co.uk/s3/product/two-factor-authentication/">Premium version</a> allows custom designing of any layout you wish).
* Site owners can allow "trusted devices" on which TFA codes are only asked for a chosen number of days (instead of every login); e.g. 30 days (<a href="https://www.simbahosting.co.uk/s3/product/two-factor-authentication/">Premium version</a>)
* Encrypt the TFA-generating secret keys using an on-disk encryption key, so that an attacker would need to break into both your WordPress database *and* your files in order to break TFA codes (as well as breaking a user's password in order to use them)
* Works together with <a href="https://wordpress.org/plugins/theme-my-login/">"Theme My Login"</a> (both forms and widgets)
* Includes support for the WooCommerce and Affiliates-WP login forms
* Includes support for Ultimate Membership Pro
* Includes support for CozmosLabs Profile Builder
* Includes support for Ultimate Member login forms (Premium version)
* Includes support for Elementor Pro login forms (Premium version)
* Includes support for bbPress login forms (Premium version)
* Includes support for login forms from the Gravity Forms User Registration add-on (Premium version)
* Includes support for any and every third-party login form (Premium version) without any further coding needed via appending your TFA code to the end of your password
* Does not mention or request second factor until the user has been identified as one with TFA enabled (i.e. nothing is shown to users who do not have it enabled)
* WP Multisite compatible (plugin should be network activated)
* Simplified user interface and code base for ease of use and performance
* Added a number of extra security checks to the original forked code
* Alert users if someone appears to have found out their password, as indicated by successfully entering a password but repeatedly entering an incorrect TFA code.
* Emergency codes for when you lose your phone/tablet (<a href="https://www.simbahosting.co.uk/s3/product/two-factor-authentication/">Premium version</a>)
* When using the front-end shortcode (<a href="https://www.simbahosting.co.uk/s3/product/two-factor-authentication/">Premium version</a>), require the user to enter the current TFA code correctly to be able to activate TFA 
* Works together with <a href="https://wordpress.org/plugins/wp-members/">"WP Members"</a> (shortcode form)
* Administrators can access other users' codes, and turn them on/off when needed (<a href="https://www.simbahosting.co.uk/s3/product/two-factor-authentication/">Premium version</a>)

= Why use TFA / 2FA ? =

Read this! <a href="https://www.wired.com/2012/08/apple-amazon-mat-honan-hacking/">https://www.wired.com/2012/08/apple-amazon-mat-honan-hacking/</a>

= How Does TFA / 2FA Work? =

This plugin uses the industry standard TFA / 2FA algorithm [TOTP](https://en.wikipedia.org/wiki/Time-based_One-time_Password_Algorithm) or [HOTP](https://en.wikipedia.org/wiki/HMAC-based_One-time_Password_Algorithm) for creating One Time Passwords. These are used by Google Authenticator, Authy, and many other OTP applications that you can deploy on your phone etc.

A TOTP code is valid for a certain time. Whatever program you use (i.e. Google Authenticator, etc.) will show a different code every so often.

= Plugin Notes =

This plugin began life in early 2015 as a friendly fork and enhancement of <a href="https://wordpress.org/plugins/two-factor-auth/">Oscar Hane's "two factor auth" plugin</a>.

== Installation ==

This plugin requires PHP version 5.3 or higher and support for either php-openssl or [PHP mcrypt](http://www.php.net/manual/en/mcrypt.installation.php). The vast majority of PHP setups will have one of these. If not, ask your hosting company.

1. Search for 'Two Factor Authentication' in the 'Plugins' menu in WordPress.
2. Click the 'Install' button. (Make sure you picks the right one)
3. Activate the plugin through the 'Plugins' menu in WordPress
4. Find site-wide settings in Settings -> Two Factor Authentication ; find your own user settings in the top-level menu entry "Two Factor Auth".

If you want to add a section to the front-end of your site where users can configure their two-factor authentication settings, use this shortcode: [twofactor_user_settings]

== Frequently Asked Questions ==

= What is two factor authentication (TFA / 2FA) ? =

Basically, it's to do with securing your logins, so that there's more than one link in the chain needing to be broken before an unwanted intruder can get in your website.

By default, your WordPress accounts are protected by only one thing: your password. If that's broken, then everything's wide open.

"Two factor" means adding a second requirement. Usually, this is a code that comes to a device you own (e.g. phone, tablet) - so, someone can't get into your website without getting hold of your device. <a href="https://en.wikipedia.org/wiki/Two_factor_authentication">You can get a longer answer from Wikipedia.</a>

Sometimes it is also called multi-factor authentication instead of two-factor - because someone could secure their systems with as many factors as they like.

= Why should I care? =

Read this: <a href="https://www.wired.com/2012/08/apple-amazon-mat-honan-hacking/">https://www.wired.com/2012/08/apple-amazon-mat-honan-hacking/</a>

= How does two factor authentication (TFA / 2FA) work? =

Since "two factor authentication" just means "a second something is necessary to get in", this answer depends upon the particular set-up. In the most common case, a numeric code is shown on your phone, tablet or other device. This code be sent via an SMS; this then depends on the mobile phone network working. This plugin does not uses that method. Instead, it uses a standard mathematical algorithm to generate codes that are only valid once each, or for only for 30 seconds (depending on which algorithm you choose). Your phone or tablet can know the code after it has been set up once (often, by just scanning a bar-code off the screen).

= What do I need to set up on my phone/tablet (etc.) in order to generate the codes? =

This depends on your particular make of phone, and your preferences. Google have produced a popular app called "Google Authenticator", which is a preferred option for many people because it is easy to use and can be set up via just scanning a bar code off your screen - <a href="https://support.google.com/accounts/answer/1066447"> follow this link, and ignore the first paragraph that is talking about 2FA on your Google account</a> (rather than being relevant to this plugin).

= What if I do not have a phone or tablet? =

Many and various devices and programs can generate the codes. One option is an add-on for your web browser; for example, <a href="https://chrome.google.com/webstore/search/authenticator">here are some apps and add-ons for Google Chrome</a>. Wikipedia <a href="https://en.wikipedia.org/wiki/Time-based_One-time_Password_Algorithm#Client_implementations">lists various programs for different computers</a>.

= I lost my device that has pass-codes - or, they don't work. What to do? =

If your pass-code used to work, but no longer does, then check that the time on your device that generates them is accurate.

If you cannot get in and need to disable two-factor authentication, then add this to your wp-config.php file, using FTP or the file manager in your hosting control panel:

<code>define('TWO_FACTOR_DISABLE', true);</code>

Add it next to where any other line beginning with "define" is.

Alternatively, if you have FTP or cPanel access to your web hosting space, you can de-activate the plugin; <a href="https://updraftplus.com/understanding-wordpress-installs-plugins/">see this article.</a>

= Why does the plugin not support sending the two-factor code by email? =

If someone has access to your email account, then they can send a password-reset code there using the password-reset mechanisms built into WordPress. Therefore, if the two-factor code was also sent there, then ability to read your email allows the breaking of both factors, and hence is no longer truly *two* factor authentication.

Some users might have two factor authentication on their email account, but this is not knowable or controllable from inside WordPress, and so giving this option to users means that the administrator cannot see or enforce two-factor authentication. And even in this case, email is often sent between servers unencrypted, and so is susceptible to man-in-the-middle attacks beyond the control of WordPress.

= What are HOTP and TOTP? =

These are the names of the two mathematical algorithms that are used to create the special codes. These are industry-standard algorithms, devised by expert cryptographers. HOTP is less popular, but the device that generates the codes does not need to know the correct time (instead, the codes are generated in a precise sequence). TOTP is much more popular, and generates codes that are only valid for 30 seconds (and so your device needs to know the time). I'd recommend TOTP, as HOTP can be annoying if something causes the sequences to get out of sync.

= What is the shortcode to use for front-end settings? =

[twofactor_user_settings]

= I deliberately entered a wrong password, and it let me login! =

You have a password manager extension installed in your web browser, with the correct password entered in it. It has automatically replaced your wrong password with the right one from its saved store. This behaviour has been observed and confirmed by several users. You can verify it by using the web developer tools in your browser to look at the HTTP data sent to WordPress, and observe which password is actually in it. You can also open a fresh web browser with no such extension in it to re-test.

Note that the two factor authentication plugin has no mechanism to compare or approve passwords; this is done by WordPress core. If the wrong password is sent, then this is handled by WordPress, and the login will not proceed.

== Screenshots ==

1. Site-wide settings

2. User settings (dashboard)

3. User settings (front-end, via shortcode)

4. Regular WP login form requesting OTP code (after successful username/password entry)

5. WooCommerce login form requesting OTP code (after successful username/password entry)

6. What the user sees if opening a wrong OTP code on the regular WP login form

7. What the user sees if opening a wrong OTP code on the WooCommerce login form

8. Where to find the site-wide settings in the dashboard menu

9. Where to find the user's personal settings in the dashboard menu

10. Emergency codes (Premium version)

11. Adjusting other users' settings as an admin (Premium version)

12. Building your own design for the page with custom short-codes (Premium version)

13. Allowing users to have trusted devices (Premium version)

== Changelog ==

= 1.14.27 - 25/Nov/2024 =

* FIX: 1.14.26 broke saving settings on a front-end page via the shortcode
* TWEAK: Purge empty members of the tfa_incorrect_code_attempts list, to prevent unnecessary growth; and key by user ID, not user login

= 1.14.26 - 13/Nov/2024 =

* TWEAK: Resolve a language deprecation notice on WP 6.7 and non-default language

= 1.14.25 - 11/Nov/2024 =

* FIX: Fix a regression in 1.14.24 Premium in the handling of empty query strings in redirect URLs when running on PHP <= 7.4 (if on such versions, please see https://www.php.net/eol.php ).

= 1.14.24 - 24/Oct/2024 =

* TWEAK: Redirection when TFA is compulsory (Premium feature) should exclude the logout link
* FIX: An issue that prevented turning on TFA when the redirect user URL is set

= 1.14.23 - 25/Jun/2024 =

* TWEAK: Do not require TFA codes for API requests authenticated via an application password
* TWEAK: Improve formatting of "trust this device" checkbox

= 1.14.22 - 28/Nov/2023 =

* FIX: Fix a fatal error that occurred due to a failure to process a WP_Error object on an Affiliates WP login form
* TWEAK: Further improve styling when used on Ultimate Member login forms
* TWEAK: Force unsetting of disabled property before triggering click event

= 1.14.21 - 01/Nov/2023 =

* TWEAK: Improve styling when used on Ultimate Member login forms

= 1.14.20 - 27/Oct/2023 =

* FEATURE: Add support (Premium version) for Ultimate Member login forms

= 1.14.19 - 14/Oct/2023 =

* TWEAK: Change the "not available for your user" message to be more appropriate when output on pages without login
* TWEAK: Prevent PHP coding notice when logging an incorrect login
* TWEAK: Updated bundled updater library to latest series

= 1.14.18 - 30/Aug/2023 =

* TWEAK: The settings for making TFA compulsory (Premium feature) have had their layout and descriptions changed to enhance clarity.
* TWEAK: The filter simba_tfa_apply_redirect_in_admin has had its default value changed from false to true. This means that when users are forcibly redirected to a setup page, this happens in the admin area too.

= 1.14.17 - 26/Aug/2023 =

* FEATURE: Notify user if multiple wrong TFA codes used (which indicates someone has their password)
* FEATURE: Add a Gutenberg block for the [twofactor_user_settings] shortcode.
* TWEAK: Resolve PHP 8.2 deprecation notice introduced in 1.14.15
* TWEAK: Do not look for a TFA code when validating an existing cookie
* TWEAK: Tweak HTML structure where private key is printed to reduce likelihood of copy/paste introducing an unwanted space
* TWEAK: Do not consider empty strings when turning on database encryption
* TWEAK: Update updater library to current version (resolves some PHP 8.2 deprecation notices)

= 1.14.16 - 08/May/2023 =

* FIX: Fix an error on PHP 7.2 introduced in 1.14.15 (PHP 7.2 was end-of-lifed by the PHP group in 2020, so please update! https://www.php.net/eol.php ).
* TRANSLATIONS: Update French and Italian translations (thank you to the translators)
* TWEAK: Correct string identifier for "TFA is configured to not be available for this role" text
* TWEAK: Make role names translatable in one place where they were not

= 1.14.15 - 05/May/2023 =

* FEATURE: Encrypt TFA secret keys that are stored in the database (extra protection in case of your database being hacked)
* FIX: Fix handling of login forms on a page where Gravity Forms was loaded in the JavaScript environment but was not providing the login form
* TWEAK: Make use of hash_equals function when comparing TOTP codes to prevent timing comparisons

= 1.14.14 - 24/Mar/2023 =

* FIX: When on a multisite on a non-main site, the link shown to the network administration for the plugin was wrong
* TWEAK: Cache whether a user is using TFA when moving from the username field, in order to reduce delay when presenting TFA field
* TWEAK: Userlist related css file version to be based on its file's time.
* TWEAK: Add config utility methods and tweak registering settings.
* TWEAK: Add a span with CSS class simba_tfa_otp_login_help to the "check your OTP app to get this password" text
* TWEAK: Add support for CozmosLabs Profile Builder login forms
* TWEAK: Fix some minor problems related to translation domain handling and untranslatable phrases
* TWEAK: Suppress message that these are your personal settings for less-privileged users
* TWEAK: Ensure that user roles are translated
* TWEAK: Updated French translation, thanks to @madmax4ever

= 1.14.13 - 15/Nov/2022 =

* TWEAK: Improve styling of trusted device control when used with Gravity Forms User Registration Login forms

= 1.14.12 - 12/Nov/2022 =

* FEATURE: Add support (Premium version) for Gravity Forms User Registration Login forms
* TWEAK: Fix PHP notice with the AffiliateWP plugin if a user has not enabled TFA

= 1.14.11 - 25/Oct/2022 =

* TWEAK: Provide a link to the user's TFA settings on the user profile page
* TWEAK: Fix a typo (being/begin)
* TWEAK: In the admin settings, show more clearly in the "Make two factor authentication compulsory" section the dependence upon the earlier "Make two factor authentication" section

= 1.14.10 - 10/Oct/2022 =

* TWEAK: Only load Simba_TFA_Login_Form_Integrations class if not already present
* TWEAK: Hide all HTML entities that have `hide-when-displaying-tfa-input` class when 2FA code prompt at login time.

= 1.14.9 - 07/Oct/2022 =

* FEATURE: Allow the site owner to choose when policy enforcement (Premium) begins for already-existing users

= 1.14.8 - 05/Oct/2022 =

* TWEAK: Move JavaScript for displaying QR codes and handling trusted devices into its own file, for better CSP compatibility

= 1.14.7 - 28/Sep/2022 =

* TWEAK: Dynamic (non-explicitly declared) properties are deprecated as of PHP 8.2
* TWEAK: Update bundled Select2 4.0 version to current release
* TWEAK: Move JavaScript for administering other users into its own file, for better CSP compatibility
* TWEAK: When a device is already trusted, show this information as plain text, not in the TFA field
* TWEAK: When the TFA input field is shown, hide error messages from previous logins
* TWEAK: If the AJAX call to check on OTP status fails, show a user-visible message
* TWEAK: Add .localdomain hostnames to those permitted to have trusted devices
* TWEAK: Relabel "Get codes" button
* TWEAK: Add some filters allowing easier customisation of messages displayed
* TWEAK: Show only the base32 encoding of the private key (unless the shortcode explicitly specified otherwise), since for a long time now this is what all known apps accept

= 1.14.6 - 02/Sep/2022 =

* TWEAK: The TFA login script is loaded on the login script if a user has enabled the Two Factor Authentication feature.

= 1.14.5 - 01/Sep/2022 =

* TWEAK: Gave Premium mentions their own CSS class

= 1.14.4 - 15/Aug/2022 =

* FIX: Multisite Plugin Settings link to work in particular site plugins page for main site admin
* REFACTOR: Make the Simba Two Factor Authentication library more re-usable
* REFACTOR: Place premium auto-update code in the main file
* TWEAK: Introduce simba_tfa_get_option_site_id and simba_tfa_skip_adding_options_menu_entry filters

= 1.14.3 - 26/Jan/2022 =

* TWEAK: Change internal translation building and loading mechanism
* TWEAK: "https://" is not a translatable string
* TWEAK: Load translations even if aborting due to incompatible PHP version
* TWEAK: Update updater libraries to current versions

= 1.14.1 - 08/Nov/2021 =

* REFACTOR: The constants SIMBA_TFA_PLUGIN_DIR and SIMBA_TFA_PLUGIN_URL have been abolished. If you had hand-coded any code that used them, then you will want to review and test your customisations carefully first. This applies for all refactoring items and internal changes mentioned below.
* REFACTOR: Internal plugin directory structure changed
* TWEAK: Fix a potential PHP coding notice in 1.13.0 when an administrator viewed a user's QR code

= 1.13.0 - 01/Nov/2021 =

* REFACTOR: Complete re-organisation of all Premium code. If you had hand-coded any code which interacted with it, you will want to review and test your customisations carefully first. This applies for all refactoring items and internal changes mentioned below.
* REFACTOR: Abolished the class Simba_TFA_Plugin_Admin_Dashboard_Integration
* REFACTOR: Moved some TOTP/HOTP-specific methods out of Simba_Two_Factor_Authentication into Simba_TFA_Provider_TOTP
* TWEAK: Class TFA_Frontend renamed to Simba_TFA_Frontend
* TWEAK: The constant SIMBA_TFA_PLUGIN_FILE is no longer used internally and has been abolished
* TWEAK: Move Premium plugin update loader into the main Premium class
* TWEAK: Factor out all Premium features into individual classes
* TWEAK: The method tfa_is_available_and_active() has been removed.
* TWEAK: The method Simba_TFA_Provider_TOTP::getPanicCodesString() has been renamed to Simba_TFA_Provider_TOTP::get_emergency_codes_as_string()

= 1.12.3 - 22/Oct/2021 =

* FIX: Fix the twofactor_user_qrcode shortcode in the Premium version

= 1.12.2 - 21/Oct/2021 =

* FIX: Prevent load-order related fatal error (regression since 1.12.0) on sites that did not have AUTH_KEY defined in wp-config.php
* TWEAK: Update updater library in Premium version to latest version
* TWEAK: Introduce templating method for better code organisation

= 1.12.1 - 18/Oct/2021 =

* REFACTOR: Continuing the major re-factor of the plugin's internal classes. If you had hand-written custom PHP code that hooks into any internal classes, you will want to review your customisations carefully first.
* TWEAK: Update .pot file

= 1.12.0 - 16/Oct/2021 =

* REFACTOR: Major re-factor of the plugin's internal classes. If you had hand-written custom PHP code that hooks into any internal classes, you will want to review your customisations carefully first.
* TWEAK: Harmonise wording on trusted devices label
* TWEAK: Remove redundant hex2bin compatibility for no-longer-supported PHP versions

= 1.11.0 - 14/Sep/2021 =

* FEATURE: (Premium) Add new anti-bot feature for WooCommerce login forms: do not include the login form within the page HTML (making them invisible to most bots), bringing it back via JavaScript. The feature needs to be activated within the plugin settings.

= 1.10.4 - 27/Jul/2021 =

* TWEAK: Fix a couple of minor visual regressions in the WooCommerce login form TFA field layout

= 1.10.3 - 28/Jun/2021 =

* FIX: Incorrect object reference in Affiliate WP integration (regression in 1.10.0)

= 1.10.2 - 26/Jun/2021 =

* TWEAK: The script tfa_frontend.php now uses an external JavaScript file (better compatibility with with content security policies)

= 1.10.1 - 25/Jun/2021 =

* FIX: Fix a bug in the Premium Elementor integration introduced in 1.10.0.

= 1.10.0 - 15/Jun/2021 =

* REFACTOR: Integrate the previously-separate WooCommerce/Affiliates-WP handlers in the main handler, eliminating redundant/duplicate code. Eliminate the internal concept of different form types by re-coding the few "type one"s as type twos. Separate login-form specific data from code.

= 1.9.6 - 04/Jun/2021 =

* FEATURE: Support bbPress login forms (Premium version)

= 1.9.5 - 26/May/2021 =

* TRANSLATIONS: Update bundled Spanish translation (es_ES) in Premium release

= 1.9.4 - 25/May/2021 =

* FIX: Prevent an issue identifying the username field when on a page with both Affiliates WP login and registration forms, when the login form displayed second

= 1.9.3 - 14/Apr/2021 =

* FIX: In the Premium version, when appending the TFA code to the password on third-party login forms with no direct support, only usernames were accepted for the login (not email addresses)

= 1.9.2 - 20/Mar/2021 =

* TWEAK: When checking if a user has TFA enabled on a login page, perform the same sanitisation on the username as WP core, so that if the user mistypes their username (which WP accepts) e.g. by prefixing a space, then they will still be asked for their TFA code (instead of jumping straight to an error for not supplying one)
* TRANSLATIONS: Added an Italian translation, thanks to Edoardo Di Leginio

= 1.9.1 - 15/Feb/2021 =

* TWEAK: Correct the "for" attribute of the "mark as trusted" text label on the WooCommerce login form

= 1.9.0 - 09/Feb/2021 =

* FEATURE: (Premium) If TFA is required for a user, and they have not yet set it up, then force them to be redirected to a configured URL
* TWEAK: Replace the deprecated jQuery.click() and .change() methods

= 1.8.8 - 16/Jan/2021 =

* TWEAK: Replace the deprecated jQuery.unbind() and .focus() methods
* TWEAK: If the free version is active, then throw an error if trying to activate the Premium version, explaining what needs to be done

= 1.8.7 - 11/Jan/2021 =

* TWEAK: Update jQuery document ready, click and submit styles to one not deprecated in jQuery 3.0, and replace :first pseudo-selector with .first()
* TWEAK: Now marked as supporting PHP 5.6+ (now that PHP 8.0 is out)
* TWEAK: Update to the latest version of the bundled updater library (paid versions), which adds integration with WP 5.5+'s auto-updater

= 1.8.6 - 15/Sep/2020 =

* FEATURE: Add a 'TFA' column also to the Users screen in the WP network admin dashboard (multisite installs)
* TWEAK: Update the bundled updater library (paid versions) to the current release

= 1.8.5 - 29/Aug/2020 =

* TWEAK: Fix the "for" attribute of the "trusted" text label on the WooCommerce login form
* TWEAK: If a website's wp-login.php is available under multiple hosts without CORS enabled between them, then AJAX calls would fail; this is now resolved by using a relative URL instead
* TWEAK: Update bundled updater libraries on Premium version (improving compatibility with WP 5.5+'s update settings)

= 1.8.4 - 26/May/2020 =

* TWEAK: Updare .pot file; now both the first two parameters to _n() are also included in the aggregation process

= 1.8.2 - 23/May/2020 =

* FIX: If the site owner was requiring a correct code to be supplied for activation, then this was also being required for de-activation
* TWEAK: Introduce simbatfa_enforce_require_after_check filter, allowing developers to selectively disable the "require TFA after X days" check
* TWEAK: Update .pot file

= 1.8.0 - 18/Apr/2020 =

* FEATURE: Add support in the paid version for Elementor login forms
* TWEAK: Updater in paid version now will make checks on availability without needing login
* TWEAK: Update updater class to current release

= 1.7.4 - 19/Mar/2020 =

* TWEAK: Adjust how the trusted field is referenced from JavaScript, fixing IE11 compatibility
* TWEAK: Introduce the filter simba_tfa_required_for_user

= 1.7.3 - 03/Mar/2020 =

* TWEAK: Provide non-plural alternative for trusted device phrase
* TWEAK: Mark as supporting WP 5.4

= 1.7.2 - 13/Feb/2020 =

* TWEAK: Update message about what to do with translations

= 1.7.1 - 14/Jan/2020 =

* FIX: Missing file in 1.7.0 (free) release

= 1.7.0 - 14/Jan/2020 =

* FEATURE: (Premium version): Add an optional TFA section to the WooCommerce account details section in "My Account"
* TWEAK: Fix div tag balancing issue in settings output
* TWEAK: Update WooCommerce integration to adjust to DOM changes in WooCommerce 3.8
* TWEAK: Update .pot file

= 1.6.4 - 12/Nov/2019 =

* TWEAK: On wp-login.php on WordPress 5.3, the password field was not hiding when the TFA field opened
* TWEAK: Update .pot file
* TWEAK: Add data-lpignore attribute to TFA field to indicate to LastPass that it is not a password field

= 1.6.3 - 18/Oct/2019 =

* FIX: The 'trusted users' option display in the settings defaulted to showing as enabled, whereas in fact the default setting is disabled
* TWEAK: Mark as compatible with WP 5.3

= 1.6.2 - 11/Sep/2019 =

* FIX: On multisites, administration of site users who were not present on the main site was not possible
* TWEAK: Introduce the WP action simba_tfa_activation_status_saved to allow developers to respond to activation status changes
* TWEAK: Update updater class to 1.8 series

= 1.6.1 - 10/Aug/2019 =

* TWEAK: Response to an attempt to turn TFA on can now include an "error" attribute if the attempt failed due to failure to supply the current code

= 1.6.0 - 08/Aug/2019 =

* FEATURE: (Premium version) By using the parameter style="require_current" with the shortcode twofactor_user_settings_enabled, the user will only be able to activate TFA if they enter the current TFA code
* TWEAK: Remove the incorrect suffix "(Premium)" (double-suffix in the actual Premium version) that appeared in the plugin title in 1.5.6

= 1.5.6 - 06/Aug/2019 =

* TWEAK: Allow customisation of a particular message via a filter simbatfa_message_you_should_verify
* TWEAK: Replace "eachother" with "each other"

= 1.5.5 - 30/Jul/2019 =

* TWEAK: Force a global context when creating the initial Simba_Two_Factor_Authentication object, to work around direct accesses from components that do not set the scope correctly

= 1.5.4 - 17/Jul/2019 =

* FEATURE: (Premium version) - allow the site administrator to forbid users who have compulsory TFA to turn it off (supplementing the additional capability to prevent them logging in)

= 1.5.3 - 22/Jun/2019 =

* TWEAK: When using your final emergency code (Premium version), and viewing your settings (which regenerated new ones), then if you did not follow the advice to reset your private key, you would get the same codes as before. This might be thought undesirable (though is not a security flaw, as the emergency codes are no more guessable the second time around than the first). This behaviour has now been changed.

= 1.5.2 - 08/Jun/2019 =

* TWEAK: When php-mcrypt was not installed, pressing the "Reset private key" link in a user's settings would cause an unnecessary PHP notice, and display a wrong "current code" for a few seconds.

= 1.5.1 - 05/May/2019 =

* FEATURE: Support any login form (Premium version) via appending the TFA code onto the end of the password. This allows support even of login forms coded in a way that make integrations (that aren't hacks or inordinate amounts of work-around code) impossible (e.g. PeepSo)
* TWEAK: Minor wording tweak in the explanation of how TOTP works.

= 1.4.12 - 18/Apr/2019 =

* TWEAK: Add a filter simba_tfa_localisation_strings allowing further customisation of front-end strings
* TWEAK: Add an extra instructional message in the "Make two factor authentication compulsory" section (Premium) to explain how to cope with existing users
* TWEAK: Cope with the user entering spaces in their two-factor code (TOTP protocol codes are numbers only, but some apps apparently display formatting and users are not aware)
* TWEAK: Mark as supporting WP 5.2

= 1.4.11 - 08/Mar/2019 =

* FIX: On multisites, the user search should search on all sites, not just the main one

= 1.4.10 - 01/Mar/2019 =

* TWEAK: Introduce a filter, simba_tfa_management_capability, allowing the WP capability (default: manage_options) required by a user to manage the plugin to be changed. (Be careful - giving the ability to manage could potentially mean the ability to lock any user out).

= 1.4.9 - 20/Feb/2019 =

* SECURITY: The security fix in version 1.4.7 was faulty and failed to completely fix the problem; it is now resolved in this release. Our apologies for the double update.

= 1.4.8 - 16/Feb/2019 =

* FIX: On some multisite setups, the link to the site-wide administration settings went to the wrong place

= 1.4.7 - 06/Feb/2019 =

* SECURITY: If a user's WordPress account username was in the form of an email address, and if their actual account email address was something different, and TFA was set up on that account, and used the "username" (that looked like an email address) to login, then TFA controls upon login on that account would be ineffective. Other accounts were not affected (regardless of whether you login by email or not). This vulnerability was inherited from the original "Two Factor Auth" plugin that this plugin was forked from, and so is present in all versions before this one.

= 1.4.6 - 05/Feb/2019 =

* FIX: When displaying a user's trusted devices in the admin page, the time that a device was trusted until was not shown correctly (instead, it showed the current time)
* FIX: Removing the first trusted device in a list did not always work
* TWEAK: Display "(none)" when there are no trusted devices

= 1.4.4 - 04/Feb/2019 =

* FEATURE: Trusted devices are now listed in the user's admin page, allowing them to see and remove trust from their devices.
* TWEAK: Updated .pot file

= 1.4.3 - 28/Jan/2019 =

* FIX: The "Trusted devices" functionality (Premium) checkbox was not appearing when activated
* TWEAK: Add a missing translation domain to a phrase

= 1.4.1 - 25/Jan/2019 =

* FEATURE: Trusted devices: A site owner can now choose to allow particular user levels (e.g. admins, editors) to mark devices as 'trusted' and thereby exempt from needing to enter a TFA code for a chosen number of days. This feature is off by default and requires https (i.e. SSL) on the login form and cookies to be kept in the trusted device.
* FIX: Fix a regression in 1.4.0 whereby when a site owner viewed another user's current code, it could later self-update with the wrong user's value
* TWEAK: Add the robustness in parsing broken JSON present on the standard WP login form to other login forms
* TWEAK: Various internal code documentation improvements
* TWEAK: Suppress mcrypt deprecation notices in places where we would use an alternative if it was not present
* TWEAK: Bumped the support requirement up to WP 3.4. I'm not aware of anything done to break it on 3.3, but this is the official requirement (it's very hard to test old WP versions as they don't run on modern webserver stacks)

= 1.4.0 - 24/Jan/2019 =

* FEATURE: Where the current OTP code is displayed (during setup), this will now self-update automatically (i.e. without needing a manual press on the "update" link).
* TWEAK: Various improvements to the layout and text of the setup page to help make the process more understandable
* TWEAK: The current code is shown next to the UI option for enabling TFA
* TWEAK: Prevent a PHP notice if AUTH_KEY was not defined (on some very old WP installs)

= 1.3.13 - 18/Dec/2018 =

* SECURITY: Fix a logged-in CSRF vulnerability reported by Martijn Korse (www.bitnesswise.com). Due to a missing nonce check, if an attacker was able to persuade a personally-targeted victim who was currently logged in to their WordPress account to visit a personally-crafted (for the individual victim) page in the same browser session, then the attacker would be able to de-activate two-factor authentication for the victim on that WordPress site (thus leaving the targeted account protected by the user's password, but not by a second factor - the absence of a request for a TFA code would be apparent on the user's next login). This vulnerability was inherited from the original "Two Factor Auth" plugin that this plugin was forked from, and so is present in all versions before this one.
* TWEAK: Some minor code-tidying
* TWEAK: Update bundled Premium updater library to current version (1.5.10)

= 1.3.12 - 14/Dec/2018 =

* TWEAK: Prevent a PHP debugging notice when $pagenow is not set

= 1.3.11 - 04/Dec/2018 =

* FEATURE: Add a 'TFA' column on the Users screen in the WP admin dashboard to display TFA status, thanks to Enrico Sorcinelli.

= 1.3.10 - 30/Nov/2018 =

* FIX: TFA codes were not being requested on the login form on a WooCommerce dedicated order payment page (i.e. /checkout/order-pay/123456/?pay_for_order=true&key=wc_order_blahblahblah) (meaning that if a user had TFA activated, login would fail).
* TWEAK: Prevent a PHP notice if AUTH_SALT was not defined (on some very old WP installs)

= 1.3.9 - 30/Oct/2018 =

* SECURITY: If you were not using the recommended option of requiring 2FA for XMLRPC requests, then an attacker could potentially also bypass requirements for 2FA on ordinary logins (i.e. only need the password). Such users will want to immediately update, though we recommend that all users do. This vulnerability was inherited from the original "Two Factor Auth" plugin that this plugin was forked from, and so is present in all versions before this one.

= 1.3.8 - 25/Oct/2018 =

* TWEAK: Update the updater class in the Premium version to the current release (1.5.6)

= 1.3.7 - 15/Oct/2018 =

* TWEAK: Try to mitigate plugins on the login page which cause JavaScript exceptions by enqueuing our scripts earlier.

= 1.3.6 - 04/Oct/2018 =

* TWEAK: Add attribute autocomplete="off" on the WooCommerce login form TFA field (was already present for regular WP login form)
* TRANSLATION: Added Portuguese (Brazilian) translation, courtesy of Dino Marchiori

= 1.3.5 - 02/Oct/2018 =

* TWEAK: Some code-styling consistency clean-ups
* TWEAK: Allow one more window's tolerance by default for codes from devices running fast

= 1.3.4 - 11/Sep/2018 =

* FIX: Sometimes a TML widget login form could fail to work because of a changed/unexpected DOM tree
* FIX: Some further breakage in TML had occurred, causing login buttons to require to be pressed twice

= 1.3.3 - 31/Jul/2018 =

* FIX: Restore support for "Theme My Login", which had been broken by unannounced changes in TML 7.x
* TRANSLATIONS: Update .pot file

= 1.3.2 - 31/May/2018 =

* TWEAK: Add the simbatfa_check_tfa_requirements_ajax_response and simbatfa_verify_code_and_user_result filters to allow over-riding of the response to the "TFA required?" question and the TFA check itself by developers

= 1.3.1 - 25/May/2018 =

* FIX: The WooCommerce 3.3+ login form was requiring two clicks on the 'Log In' button
* TWEAK: The progress spinner had disappeared on WooCommerce 3.3+

= 1.3.0 - 05/Apr/2018 =

* FEATURE: (Premium version) Integration with the WP-Members login form, https://wordpress.org/plugins/wp-members/ . N.B. WP-Members does not pass on the real error message upon a login failure, but displays its own hard-coded message that the username/password were wrong; so you'll see this even if it was really the TFA code that was wrong.
* TWEAK: Change the permission check for editing other users (Premium version) to edit_users (instead of the previous update_plugins, intended just as a proxy for "is an admin")
* TWEAK: Stop using the deprecated jQuery.parseJSON method
* TWEAK: Change a string that was not in a translatable form
* TWEAK: Update the updater class in the Premium version to the current release (1.5.1)

= 1.2.35 - 28/Nov/2017 =

* TWEAK: Upon front-end settings save, do jQuery(document).trigger('tfa_settings_saved'), allowing the user to respond to the action (e.g. reload page)
* TWEAK: Suppress mcrypt deprecation notices on PHP 7.1 (we already know it is deprecated, and already use openssl if it is not installed)

= 1.2.34 - 08/Nov/2017 =

* TWEAK: Remove calls to the deprecated screen_icon() function
* TWEAK: Remove some unnecessary bundled translation files
* TWEAK: Add some translation files not previously included in the Premium version
* TWEAK: Update bundled Premium updater library to current (1.5.0)

= 1.2.33 - 09/Oct/2017 =

* FIX: The available/required settings for super-admins on multisite installs were not saving (Premium feature)
* FIX: When the admin fetched another user's current QR code, it embedded the wrong username (which was a cosmetic issue only - the code itself was correct) (Premium feature)

= 1.2.32 - 06/Oct/2017 =

* TWEAK: Update bundled updater in Premium to latest version (1.4.8)

= 1.2.31 - 05/Oct/2017 =

* FEATURE: (Relevant to Premium version): Automatically generate new emergency codes when they run out, including upon view of settings if there are none (e.g. on upgrade from free to Premium)
* TWEAK: Code-styling consistency tweaks

= 1.2.30 - 18/Sep/2017 =

* FIX: TML shortcode forms were not working properly for non-TFA users

= 1.2.29 - 16/Sep/2017 =

* FIX: Prevent double-show of TFA field on TML default login page (regression)
* FIX: Restore functionality on TML shortcode forms (regression, likely due to changes in TML)
* TWEAK: Restore the spinner to proper size on all forms
* TWEAK: A few very minor code style clean-ups

= 1.2.27 - 29/Aug/2017 =

* TWEAK: Add the new 'PHP Requires' header to readme.txt
* TWEAK: Correct a couple of wrong translation domain references

= 1.2.26 - 08/Aug/2017 =

* FIX: Do not request TFA code on TML reset password form (regression, likely due to changes in TML)
* APOLOGIES: 1.2.25 was a faulty release that would block logins. You should immediately update.

= 1.2.24 - 05/Aug/2017 =

* TWEAK: Update to the latest version of the updater library (Premium)

= 1.2.23 - 15/Jun/2017 =

* TWEAK: Allow admins to reset users' private keys (Premium)

= 1.2.22 - 23/May/2017 =

* TWEAK: Update updater library to current version (Premium)
* TWEAK: Use higher-quality spinner image
* COMPATIBILITY: Mark as compatible with WP 4.8

= 1.2.21 - 22/Feb/2017 =

* TWEAK: Update jquery-qrcode library to latest release (0.14.0)
* TWEAK: Explicitly encode spaces in WordPress usernames (apparently resolves a problem with a particular iPhone app)

= 1.2.20 - 17/Feb/2017 =

* TWEAK: Work around a bug seen with strlen() on one particular PHP install
* FIX: The line purporting to show the current UTC time was in fact taking your WordPress timezone into account. It has now been adjusted to show both to avoid ambiguity.
* FIX: 1.2.18 used a PHP 5.4+ only function, whereas we support PHP 5.3+

= 1.2.17 - 09/Feb/2017 =

* FIX: Fix support for login widgets from Theme My Login

= 1.2.16 - 30/Jan/2016 =

* FIX: Fix issue whereby if you were already logged in and managed to visit a login form, you would not be asked for a TFA code

= 1.2.15 - 23/Jan/2017 =

* FEATURE: Add support for login widgets from Theme My Login
* UPDATER: (Premium version): update to the latest updater class, including the new ability to automatically update

= 1.2.14 - 02/Jan/2017 =

* TWEAK: Add missing internationalisation headers to the main plugin file

= 1.2.13 - 31/Aug/2016 =

* TWEAK: Internationalisation implementation was not previously compatible with wordpress.org's translation system

= 1.2.12 - 20/May/2016 =

* FEATURE: Compatibility with https://wordpress.org/plugins/use-administrator-password/ - when TFA is enabled on an account, the TFA credentials of the user whose password was supplied are allowed (and required)

= 1.2.11 - 18/May/2016 =

* TWEAK: Update bundled select2 to version 4.0.2
* FIX: If the [twofactor_user_qrcode] shortcode (Premium version) was used without other short-codes, then the code would not display

= 1.2.10 - 31/Mar/2016 =

* TWEAK: Prefer openssl, if present, to the deprecated mcrypt. Note that if you migrate a site from a server without openssl to a server without mcrypt, then because of mcrypt's non-compliant padding, you will need to either install php-mcrypt on the new server, or disable TFA (via define('TWO_FACTOR_DISABLE', true); in your wp-config.php) to allow users to be able to log in. This also applies if the source site did have openssl, but for users who hadn't logged in since installing this update.
* TWEAK: Make the $simba_two_factor_authentication_premium object globally available
* COMPATIBILITY: Mark as tested on WP 4.5

= 1.2.8 - 12/Dec/2015 =

* FEATURE: Add support for the Affiliates-WP login form
* TWEAK: Defeat WooCommerce loading an old version of the select2 script onto the TFA settings page, and breaking the user selector (should work this time)

= 1.2.6 - 11/Nov/2015 =

* TWEAK: Defeat WooCommerce loading an old version of the select2 script onto the TFA settings page, and breaking the user selector
* TWEAK: Tested on WordPress 4.4
* TWEAK: Use h1 for heading style on admin page, not h2
* FIX: The "You'll need to use TFA to login in future" link for users for whom TFA is compulsory (Premium) was to the wrong page

= 1.2.4 - 09/Nov/2015 =

* TWEAK: Make window settings filterable

= 1.2.3 - 19/Oct/2015 =

* FIX: Fix bug in 1.2.2 that could lock out users without TFA settings

= 1.2.2 - 16/Oct/2015 =

* TWEAK: Display dashboard notice if TWO_FACTOR_DISABLE is defined in wp-config.php, to prevent time wasted wondering why nothing is happening

= 1.2.1 - 08/Oct/2015 =

* FEATURE: (Premium version) - Require users (of configured roles) to use TFA (optionally after a configurable amount of time)

= 1.1.21 - 25/Aug/2015 =

* TRANSLATIONS: Translation files can now be used (translators welcome!)
* TRANSLATION: Swedish translation added, courtesy of Bo Sving

= 1.1.19 - 20/Aug/2015 =

* TWEAK: Remove a pointless nonce check

= 1.1.18 - 01/Aug/2015 =

* COMPATIBILITY: Tested with WP 4.3 (RC1) and WooCommerce 2.4 (RC1) - no issues found (i.e. previous releases believed to be already compatible)
* FIX: When the admin is showing codes for other users, QR codes were not displaying correctly since 1.1.13

= 1.1.17 - 22/May/2015 =

* TWEAK: Introduce convenience method for developers wanting to verify that TFA is active (Premium)
* FIX: Fix operation of [twofactor_conditional] shortcode (Premium)
* FIX: Fix fatal error introduced in convenience method in 1.1.16

= 1.1.15 - 13/May/2015 =

* FIX: Fix conflict with 'reset password' form with "Theme My Login" plugin

= 1.1.14 - 12/May/2015 =

* FIX: Add TFA support to the WooCommerce login-on-checkout form (previously, TFA-enabled users could not log in using it)

= 1.1.13 - 11/May/2015 =

* TWEAK: Use jquery-qrcode to generate QR codes, replacing external dependency on Google
* TWEAK: Update bundled select2 library to 4.0.0 release (was rc2)

= 1.1.12 - 22/Apr/2015 =

* FIX: Fix corner-case where the user's login looked like an email address, but wasn't the account address. In this case, a OTP password was always requested.
* FIX: When the username does not exist, front-end should not request TFA code.

= 1.1.11 - 21/Apr/2015 =

* TWEAK: Prevent PHP notice if combining with bbPress
* TWEAK: Added more console logging if TFA AJAX request fails
* TWEAK: Add some measures to overcome extraneous PHP output breaking the AJAX conversation (e.g. when using strict debugging)

= 1.1.10 - 20/Apr/2015 =

* SECURITY: Fix possible non-persistent XSS issue in admin area (https://blog.sucuri.net/2015/04/security-advisory-xss-vulnerability-affecting-multiple-wordpress-plugins.html)
* FIX: Don't get involved on "lost password" forms (intermittent issue with "Theme My Login")

= 1.1.9 - 15/Apr/2015 =

* TESTING: Tested with "Theme My Login" - http://wordpress.org/plugins/theme-my-login/ - no issues
* TWEAK: Do a little bit of status logging to the browser's developer console on login forms, to help debugging any issues
* TWEAK: Add a spinner on login forms whilst TFA status is being checked (WP 3.8+)
* TWEAK: Make sure that scripts are versioned, to prevent updates not being immediately effective
* TWEAK: Make sure OTP field on WooCommerce login form receives focus automatically

= 1.1.8 - 14/Apr/2015 =

* FIX: Fix an issue on sites that forced SSL access to admin area, but not to front-end, whereby AJAX functions could fail (e.g. showing latest code)
* FIX: Version number was not shown correctly in admin screen since 1.1.5
* TWEAK: Show proper plugin URI

= 1.1.7 - 10/Apr/2015 =

* FIX: Fix plugin compatibility with PHP 5.6
* FIX: TFA was always made active on XMLRPC, even when the user turned it off

= 1.1.6 - 09/Apr/2015 =

* TWEAK: Change various wordings to make things clearer for new-comers to two-factor authentication.

= 1.1.5 - 07/Apr/2015 =

* FEATURE: Admin users (Premium version) can show codes belonging to other users, and activate or de-activate TFA for other users.
* PREMIUM: Premium version has now been released: https://www.simbahosting.co.uk/s3/product/two-factor-authentication/. Features emergency codes, personal support, and more short-codes allowing you to custom-design your own front-end page for users.
* TWEAK: Premium version now contains support link to the proper place (not to wordpress.org's free forum)
* TWEAK: Added a constant, TWO_FACTOR_DISABLE. Define this in your wp-config.php to disable all TFA requirements.
* FIX: Fix a bug introduced in version 1.1.2 that could prevent logins on SSL-enabled sites on the WooCommerce form when not accessed over SSL

= 1.1.3 - 04/Apr/2015 =

* TWEAK: Provide "Settings saved" notice when user's settings are saved in the admin area (otherwise the user may be wondering).

= 1.1.2 - 03/Apr/2015 =

* FIX: Include blockUI JavaScript (the lack of which caused front-end options not to save if you did not have WooCommerce or another plugin that already used blockUI installed)
* FEATURE: Don't show anything on the WooCommerce login form unless user is using 2FA (i.e. behave like WP login form)
* FEATURE: Added 9 new shortcodes for custom-designed front-end screens (Premium - forthcoming)

= 1.1.1 - 30/Mar/2015 =

* Support added for multisite installs. (Plugin should be network-activated).
* Support added for super-admin role (it's not a normal WP role internally, so needs custom handling)
* Tested + compatible on upcoming WP 4.2 (tested on Beta 3)
* Re-add option to require 2FA over XMLRPC (without specific code, XMLRPC clients don't/can't use 2FA - but requiring it effectively blocks hackers who want to crack your password by using this weakness in XMLRPC)

= 1.0 - 20/Mar/2015 =

* First version, forked from Oskar Hane's https://wordpress.org/plugins/two-factor-auth/
* Support for email "two-factor" removed (email isn't really a second factor, unless you have multiple email accounts and guard where your "lost login" emails go to)
* WooCommerce support added to the main plugin. Load WooCommerce JavaScript only on pages where it is needed.
* Use AJAX to refresh current code (rather than reloading the whole page)
* Added WordPress nonces and user permission checks in relevant places
* Shortcode twofactor_user_settings added, for front-end settings
* User interface simplified/de-cluttered

== Upgrade Notice ==
* 1.14.27 : Fix a regression in 1.14.26, and manage a database option more efficiently. A recommended update for all.
