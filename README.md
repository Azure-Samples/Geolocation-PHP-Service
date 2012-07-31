# Geolocation - PHP Web Service
The Geolocation web service is a PHP app made to store and retrieve geotagged photos and videos.  There are three end points to the service:
* a method to fetch all of the tagged locations given a latitude and longitude as well as a radius in meters.
* a method to get a shared access signature for uploading a new photo or video to Windows Azure Blob Storage.
* a method to save a new tagged location to the database along with the URL of the blob saved to storage.

This sample is designed to be deployed to Windows Azure Web Sites and uses a MySQL Database for persistence of locations in addition to Windows Azure blob storage for storing photos and videos. You can run this site in either shared or reserved mode on Windows Azure Web Sites with any number of instances.

Below you will find requirements and deployment instructions.

## Requirements
* Silex - a PHP micro-framwork - [Available Here](http://silex.sensiolabs.org/).  See below for placement.
* Windows Azure Account - [Sign up for a free trial](https://www.windowsazure.com/en-us/pricing/free-trial/).

## Additional Resources


#Installing Silex
Silex is a Micro-PHP framework that is used for this site.  [You can download it from here](http://silex.sensiolabs.org/).
After downloading Silex, you should place the phar in the following directory under your site's root:
vendor/Silex/

#Specifying your connection string
Once you've set up your Windows Azure Website and found your MySQL database connection string, open source/src/Geo/GeoCode.php and edit these lines with your database details:

		//Local
		private $db_server = 'localhost';
		private $db_user   = 'phptestuser';
		private $db_password = 'phptestuser';
		private $db_name     = 'shorty';

#Specifying your Windows Azure Storage Account
Once you've set up your Windows Azure Storage account and found your account name and key, open source/src/app.php and edit these lines with your account details:

		//Define our storage account name and keys
		define("STORAGE_ACCOUNT_NAME", "<Your Storage Account Name>");
		define("STORAGE_ACCOUNT_KEY", "<Your Storage Account Key>");

## Contact

For additional questions or feedback, please contact the [team](mailto:chrisner@microsoft.com).