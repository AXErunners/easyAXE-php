# easyAXE-php
A simple class for making calls to AXE's RPC API using PHP.

## Getting Started:
1. Include easyaxe.php into your PHP script:

	`require_once('easyaxe.php');`
2. Initialize AXE connection/object:

	`$axe = new \axerunners\easyAXE('username','password');`

	Optionally, you can specify a host, port. Default is HTTP on localhost port 9998.

	`$axe = new \axerunners\easyAXE('username','password','localhost','9998');`

	If you wish to make an SSL connection you can set an optional CA certificate or leave blank
	`$axe->setSSL('/full/path/to/mycertificate.cert');`

3. Make calls to axed as methods for your object. Examples:

	`$axe->getinfo();`
	`$axe->getrawtransaction('0e3e2357e806b6cdb1f70b54c3a3a17b6714ee1f0e68bebb44a74b1efd512098',1);`
	`$axe->getblock('000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f');`
	`$axe->mnbudget('show');`

## Additional Info:
* When a call fails for any reason, it will return false and put the error message in $axe->error

* The HTTP status code can be found in $axe->status and will either be a valid HTTP status code or will be 0 if cURL was unable to connect.

* The full response (not usually needed) is stored in $axe->response while the raw JSON is stored in $axe->raw_response

## Contribution Info

This is forked from EasyBitcoin-PHP by Andrew LeCody (https://github.com/aceat64/EasyBitcoin-PHP).
Original code is licensed under MIT.
