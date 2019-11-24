# Wordpress Default

## Configuring Local Development
Download the latest version of [Wordpress](https://wordpress.org/download/) and clone this repository into the `/wp-content/themes` directory.
```
$ git clone git@github.com:luisaugusto/wordpress-default.git
```
Next, download and install [MAMP](https://www.mamp.info/en/downloads/) to setup a local environment. In the preferences, make sure that the PHP version is set to at least `7.2.14` and the web server is pointed at the Wordpress root directory. Once all of that is setup, you should be able to start the server and go to [localhost:8888](http://localhost:8888/) and be redirected to Wordpress Config Setup page.

### MAMP Tools

 Tool | URL
  --- | ---
MAMP Start Page | [localhost:8888/MAMP](http://localhost:8888/MAMP/)
phpMyAdmin | [localhost:8888/phpMyAdmin](http://localhost:8888/phpMyAdmin/)
phpINfo | [localhost:8888/MAMP/index.php?language=English&page=phpinfo](http://localhost:8888/MAMP/index.php?language=English&page=phpinfo)

### Setting Up an Existing Site

If you are setting up an already working Wordpress installation, you'll need to import the site's database. You will also need to copy over the `wp-config.php` file to the Wordpress root directory in order to bypass the Wordpress Config Setup.
 
 ### Setting Up a New Site
 
Create a new database in [phpMyAdmin](http://localhost:8888/phpMyAdmin/), making sure that the collation is set to `utf8_general_ci`. Then, run the Wordpress config setup using the database you created and Wordpress will populate your database for you and create a `wp-config.php` file in the Wordpress root directory.

> If you get an error establishing a database connection, try changing the hostname from `localhost` to `localhost:8889` or append whichever port your MySQL server is running on. 

#### WP Config Settings

In your `wp-config.php`, find the `WP_DEBUG` definition and set it to `true`. Also, add the following lines below it:

```
define( 'WP_DEBUG_DISPLAY', true );  
define( 'WP_DEBUG_LOG', true );
```

To learn about what these do, go to the [Wordpress Developer Documentation](https://developer.wordpress.org/themes/getting-started/setting-up-a-development-environment/#wp_debug)