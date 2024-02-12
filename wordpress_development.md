# Copying installation files:
First open Nautilus as a root user. Copy the files and then give full permissions to the `wp-content` folder using the following command:
`sudo chmod -R 777 ~/htdocs/el_shop/wp-content`

# To make it possible to install plugins on local WordPress in Ubuntu without being asked for ftp user & password add the following line to `wp-config` file:
define('FS_METHOD', 'direct');

# Set full permissions on your local installation forlder:
sudo chmod -R 777 /htdocs/

# `php.ini`
To increase sizes you have to edit the `php.ini` file which is accessible on your host.

# Increase Memory size:
Enter the following code into the `wp-config.php` file.
`define('WP_MEMORY_LIMIT', '1024M');`

# How to start or stop lampp installation in ubuntu:
sudo /opt/lampp/lampp start
# or to run the lampp GUI:
sudo /opt/lampp/manager-linux-x64.run

# Slug-Based Permalinks
Always make sure you have a slug-based Permalink Structure so that Gutenberg wouldn't hide slug related fields in the post editor.

# Capability Type
This setting in "jetengine" must always set to "post". Don't ever change this default.

# Slug Changes
Chooose the slugs wisely so you won't never change it in futures. If you change slug after creating the post type in jetengine, then all the related settings for that post type will be omitted.

# Meta: زمینه های سفارشی

# Name/ID conflictes
Always use English names for Name / IDs in jetengine. Also, always make them custom so that they wouln't conflict with the already existing meta-fields saved in the database. For example, you'd better use "_room_numbers" instead of "room_numbers".

# Metboxes in jetengine
If you need to apply a more in depth customization to a specific post, then you can use Metaboxes.

# Glossaries in JetEngine
Remember to use glossary section for creating repetative `check` or `radio` options. They will be available to ACF as well as other parts of JetEngine. They can also be used in `JetEngine Smart Filter` plugin.

# Option Pages
We can use `option pages` to create metafields that are accessible in every page or section of the website.

# JetEngine Listings
Elementor does not give you the option to use various metafields on your archive page. However, by using `listing` feature of JetEngine you can easily add any type of metfields you like.

# Access DirectAdmin or CPanel
For DirectAdmin, use `2222` or `2223` as the port number after the website url. For CPanel use `2083`.

# WooCommerce installation
First install `Farsi WooCommerce` and then install the original `WooCommerce` plugin.

# Direct Bank Gateway
You need to have `Enamad` which is a time-consuming process. However, using non-direct plugins like `Zarrinpal` from the WordPress repositories, you can have payment capability in your website. They usually charge .5 to 1 percent per transaction.

# Updating WordPress
One of the ways to update your WordPress installation is to add this piece of code to your `wp-config.php` file: `define(‘WP_AUTO_UPDATE_CORE’, true);`

# Editing wp-config file
If you want to edit `wp-config.php` but you can't do it throught the file manager of your host, download the `wp-config.php` file and apply edits and reupload it again

# Disable cache in FF:
Go to `about:config` and then make sure these boulean properties have false values: `browser.cache.memory.enable` and `browser.cache.disk.enable`

# Running servers:
`netstat -tnlp | 80`
# Stop running apache2
If the `apache2` service cannot start because another server is already running, first stop the running server: `sudo service apache2 stop`. And here's how to disable it from starting automatically on boot: `sudo update-rc.d apache2 disable` or enabling it by running `sudo update-rc.d apache2 enable` or `sudo update-rc.d apache2 defaults`

# To log errors
`define( 'WP_DEBUG', true );`
`define( 'WP_DEBUG_LOG', true );`
`define('WP_DEBUG_DISPLAY', false);`

# Print the errors in a custom_log file
```
$posts = get_post();
$file = get_stylesheet_directory(  ).'/custom-log.txt';
file_put_contents($file, "Posts: " . print_r($posts, true) . "\n\n", FILE_APPEND);
```
# Block WordPress xmlrpc.php requests
Insert the following lines in the .htaccess file in the root directory of the website.
<Files xmlrpc.php>
order deny,allow
deny from all
</Files>

# To increase your WP resources apply the following changes in php.ini:
php_value upload_max_filesize 128M
php_value post_max_size 128M
php_value max_execution_time 300
php_value max_input_time 300









