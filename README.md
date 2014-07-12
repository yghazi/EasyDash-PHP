EasyDarkcoin-PHP (https://github.com/elbereth/EasyDarkcoin-PHP)
================
By elberethzone (Alexandre Devilliers)

A simple class for making calls to Darkcoin's API using PHP.

Tips appreciated: Xbon36F261wXDL4p1CEZAX28t8U4ayR9uu

Getting Started
---------------
1. Include easydarkcoin.php into your PHP script:

	`require_once('easydarkcoin.php');`
2. Initialize Darkcoin connection/object:

	`$darkcoin = new Darkcoin('username','password');`

	Optionally, you can specify a host, port. Default is HTTP on localhost port 8332.

	`$darkcoin = new Darkcoin('username','password','localhost','8332');`

	If you wish to make an SSL connection you can set an optional CA certificate or leave blank
	`$darkcoin->setSSL('/full/path/to/mycertificate.cert');`

3. Make calls to darkcoind as methods for your object. Examples:

	`$darkcoin->getinfo();`
	`$darkcoin->getrawtransaction('0e3e2357e806b6cdb1f70b54c3a3a17b6714ee1f0e68bebb44a74b1efd512098',1);`
	`$darkcoin->getblock('000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f');`

Additional Info
---------------
* When a call fails for any reason, it will return false and put the error message in $darkcoin->error

* The HTTP status code can be found in $darkcoin->status and will either be a valid HTTP status code or will be 0 if cURL was unable to connect.

* The full response (not usually needed) is stored in $darkcoin->response while the raw JSON is stored in $darkcoin->raw_response

Contribution Info
-----------------
This is forked from EasyBitcoin-PHP by Andrew LeCody (https://github.com/aceat64/EasyBitcoin-PHP).
Original code is licenced under MIT.
