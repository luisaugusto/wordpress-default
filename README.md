![GitHub package.json version](https://img.shields.io/github/package-json/v/luisaugusto/wordpress-default)
![GitHub repo size](https://img.shields.io/github/repo-size/luisaugusto/wordpress-default)
![GitHub](https://img.shields.io/github/license/luisaugusto/wordpress-default) 

###### Please consider supporting my work and other projects:

[![Plant a Tree](https://img.shields.io/badge/Plant%20a%20Tree-%F0%9F%8C%B3-green)](https://offset.earth/luisaugusto)
[![Buy Me a Boba Tea](https://img.shields.io/badge/Buy%20Me%20a%20Boba%20Tea-🥤-yellow)](https://www.buymeacoffee.com/luiscodes)


# Wordpress Custom Default Theme

After working on many different Wordpress sites, I wanted to build a skeleton theme that featured modern technologies and build tools to help make the theme process a more enjoyable process.

This theme includes all the required files for a Wordpress, but is very minimal, without any specific templates. It makes use of Typescript and SCSS files which are added to the `src` folder and compiled with Node.

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

## Node Scripts & Compilers

This template make makes use of Node for its scripts and stylesheet compilation. Once you have the repository cloned, make sure to run `npm install`.

To use the watchers, run `npm run watchers`. This will create the `style.css` file and compile all SCSS files to that location. It will also compile TypeScript into the `dist` folder where it will be served.

Alternatively, you can run `npm run sass` to build the stylesheet and `npm run typescript` to build the scripts.