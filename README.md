GUMBO-CMS - MULTILINGUAL PHP5-MVC CMS w/Apache-MySQLL
Copyright (C) 2014 Roland CLEMENCEAU admin.lkiev@gmail.com

See LICENSE.txt for the GNU GENERAL PUBLIC LICENSE V2

See https://sourceforge.net/p/gumbo-cms/wiki/Installation%20-%20FR/ for installation instructions in French language

Gumbo is fairly easy to install on a server.

*** Server Requirements

To install Gumbo, you need:

PHP 5.6 +, at least 5.4 (with GD / JPEG support)
Apache 2.4 + (w/mod_rewrite enabled for clean urls)
MySQL 5.6 +

*** Installation

To install Gumbo, follow these simple steps:

1 . Download Gumbo from https://sourceforge.net/projects/gumbo-cms/files/, extract the archive,
and place the files either on your local Apache server document folder or on a remote server where you want your new site to appear.

2 . Create a MySQL database and import gumbo.sql

3 . Open config.php, look for the database settings and insert your own.
Equally, look for any option you may want to customize, such as admin email addresses and so on.

4 . Open .htaccess and modify the line that starts with SetEnv APP_ROOT_PATH http... so it looks like this :
(assumming you have just created a folder named my_project_name at root on your local station)

SetEnv APP_ROOT_PATH http://127.0.0.1/my_project_name   (depending on your system, you may have to use localhost instead of 127.0.0.1)

Repeat the same action but in the admin folder this time, appending the suffix '/admin', so it will look this:

SetEnv APP_ROOT_PATH http://127.0.0.1/my_project_name/admin

If you are already going live, it will look like SetEnv APP_ROOT_PATH http://www.my-site.com and SetEnv APP_ROOT_PATH http://www.my-site.com/admin

And you're all set, that's all there is to it, happy customization!

*** TROUBLESHOOTING

    If clean URLs don't work, check that Apache's mod_rewrite is enabled. Optionally, check you Apache's config file, probably named httpd.conf or apache2.conf. Ultimately, check that CLEAN_URLS is set to true in config.php and that you have entered the right base URL in both your_site.com/.htaccess and your_site.com/admin/.htaccess. But if Apache's mod_rewrite is enabled but loading Gumbo in your browser redirects you to weird urls, check that .htaccess files are not being denied or rejected in your apache's vhost files.

    If you find your Gumbo installation to be running a little slow, with weird things happening, eg: mousing over Javascript menus does not trigger sub-menus as expected, or CSS files not loading etc., then check that PHP is being run as a module only, therefore neither as CGI nor fastCGI. Although those specific issues might be caused by something else of course.

    If you're having problems updating a language's flag image, check your permissions are high enough within the language folder, do not just 777 everything though.

    If the captcha image in the user registration form does not load, make sure that the GD library is enabled AND that there is support for JPEG as well.
