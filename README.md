Mailgun-PHP
===========
[![Build Status](https://travis-ci.org/travelton/Mailgun-PHP.png?branch=master)](https://travis-ci.org/travelton/Mailgun-PHP)

This is the Mailgun PHP SDK. This SDK contains methods for easily interacting with the Mailgun API. Below are examples to get you started. For additional examples, 
please see our SDK documentation at http://documentation.mailgun.com

Current Release: 0.4-Beta

Installation
------------
To install the SDK, you will need to be using Composer in your project. If you aren't using Composer yet, it's really simple! Here's how to install composer and the Mailgun SDK.

```PHP
# Install Composer
curl -sS https://getcomposer.org/installer | php

# Add Mailgun as a dependency
php composer.phar require mailgun/mailgun-php-sdk:~0.1
``` 

For shared hosts with SSH access, you might need to run this instead (contact your shared host for assistance): 
```
php -d detect_unicode=Off -r "eval('?>'.file_get_contents('https://getcomposer.org/installer'));"
```

Next, require Composer's autoloader, in your application, to automatically load the Mailgun SDK in your project:
```PHP
require 'vendor/autoload.php';
use Mailgun\MailgunClient;
```

Usage
-----
Using the SDK should feel simple, if you're already familiar with our API endpoints. If not, no problem... When you're reviewing our documentation, the endpoints are expressed as a class in the SDK to make things easier. 

For example, here's how to use the "Messages" API endpoint:

```php
# First, instantiate the client with your API credentials and domain. 
$mgClient = new MailgunClient("key-3ax6xnjp29jd6fds4gc373sgvjxteol0", "samples.mailgun.org");

# Next, instantiate a Message object on the messages API endpoint.
$message = $mgClient->Messages();

# Now, compose your message.
$message->setMessage(array('from' => 'me@samples.mailgun.org', 
                           'to' => 'php-sdk@mailgun.net', 
                           'subject' => 'The PHP SDK is awesome!', 
                           'text' => 'It is so simple to send a message.'));

# Finally, send the message.
$message->sendMessage();
```

For usage examples on each API endpoint, go to the "src/Mailgun" folder and browse through each API endpoint folder. A README exists in each folder with examples.

[Address](src/Mailgun/Address/)  
[Bounces](src/Mailgun/Bounces/)  
[Campaigns](src/Mailgun/Campaigns/)  
[Complaints](src/Mailgun/Complaints/)  
[Lists](src/Mailgun/Lists/)  
[Logs](src/Mailgun/Logs/)  
[Messages](src/Mailgun/Messages/)  
[Routes](src/Mailgun/Routes/)  
[Stats](src/Mailgun/Stats/)  
[Unsubscribes](src/Mailgun/Unsubscribes/)  

Support and Feedback
--------------------

Be sure to visit the Mailgun official [documentation website](http://documentation.mailgun.com/) for additional information about our API. 

If you find a bug, please submit the issue in Github directly. [Mailgun-PHP Issues](https://github.com/mailgun/Mailgun-PHP/issues)

As always, if you need additional assistance, drop us a note at [support@mailgun.com](mailto:support@mailgun.com).
