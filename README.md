# Maxmind minFraud PHP API Version 1.53 #

## Example Scripts ##

See examples/minfraud.php for complete example how to use this API with the
minFraud service.

See examples/telephone-verification.php for complete example how to use this API with
the Telephone Verification service.

These scripts can be run from the shell.

## API Documentation for minFraud service ##

$ccfs = new CreditCardFraudDetection;
  This creates a new CreditCardFraudDetection object

$ccfs->isSecure
  If isSecure is set to 0 then it uses regular HTTP.
  If isSecure is set to 1 then it uses Secure HTTPS (requires Curl PHP binding)

$ccfs->input($hash)
  Takes a hash and uses it as input for the server.
  See http://dev.maxmind.com/minfraud/ for details on input fields.

$ccfs->query();
  Queries the server with the fields passed to the input method
  and stores the output.

$hash = $ccfs->output();
  Returns the output from the server.
  See http://dev.maxmind.com/minfraud/ for details on output fields.

## Secure HTTPS ##

Secure HTTPS is off by default. If you want secure HTTPS then you need to have
the Curl PHP binding, the curl library and the OpenSSL library.

You can download the curl libary at:
http://curl.haxx.se/download.html
http://curl.haxx.se/docs/install.html for installation details

It is recommended that you install these packages in this order:

1. OpenSSL library
2. Curl library
3. Curl PHP binding

Once you have installed these, you can turn on Secure HTTPS by setting:

```php
$ccfs->isSecure = 1;
```
where `$ccfs` is the CreditCardFraudDetection object.

===============================
Copyright (c) 2013, MaxMind, Inc

All rights reserved.  This package is licensed under the LGPL.  For details
see the COPYING file.