# EasyEnergi-PHP
https://github.com/energicryptocurrency/EasyEnergi-PHP

A simple class for making calls to Energi's RPC API using PHP.

## Getting Started:
1. Include easyenergi.php into your PHP script:

	`require_once('easyenergi.php');`
2. Initialize Energi connection/object:

	`$energi = new \energi\EasyEnergi('username','password');`

	Optionally, you can specify a host, port. Default is HTTP on localhost port 9998.

	`$energi = new \energi\EasyEnergi('username','password','localhost','9998');`

	If you wish to make an SSL connection you can set an optional CA certificate or leave blank
	`$energi->setSSL('/full/path/to/mycertificate.cert');`

3. Make calls to energid as methods for your object. Examples:

	`$energi->getinfo();`
	`$energi->getrawtransaction('0e3e2357e806b6cdb1f70b54c3a3a17b6714ee1f0e68bebb44a74b1efd512098',1);`
	`$energi->getblock('000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f');`
	`$energi->mnbudget('show');`

## Additional Info:
* When a call fails for any reason, it will return false and put the error message in $energi->error

* The HTTP status code can be found in $energi->status and will either be a valid HTTP status code or will be 0 if cURL was unable to connect.

* The full response (not usually needed) is stored in $energi->response while the raw JSON is stored in $dash->raw_response

## Contribution Info

This is forked from EasyBitcoin-PHP by Andrew LeCody (https://github.com/aceat64/EasyBitcoin-PHP).
Original code is licenced under MIT.
