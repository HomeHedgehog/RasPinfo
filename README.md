[RasPinfo](https://www.github.com/homehedgehog/RasPinfo)
======
RasPinfo copyright (C) 2017-2018, Lasse Oksanen <lasse_oksanen@hotmail.com>

Overview
--------
RasPinfo is a minimal web based monitoring tool for [Raspberry Pi](https://www.raspberrypi.org/)
and [Raspbian](https://www.raspbian.org/). RasPinfo is written in HTML, PHP, JavaScript and Shell. The software size is only 250KB unzipped.

Features
--------
### With RasPinfo users can monitor Raspberry Pi's:
* Hostname
* Distribution name
* Local IP address
* MAC address
* Uptime
* Last boot
* Number of logged in users
* Model name
* CPU model, temperature, core voltage and frequency
* Total RAM and usage
* USB HDD model name, serial number, firmware version, mount point, filesystem, total size and usage in /dev/sda

### Other features:
* Save system data to .txt file
* Display CPU temperature in celsius or fahrenheit
* Display date in year-month-day or day-month-year
* Get notified of too high CPU temperature
* Use one of the three different color themes

Requirements
------------
* Raspberry Pi (Model 3 B)
* Raspbian (Stretch)
* Apache HTTP Server
* PHP 5.4.0 or higher
* JavaScript support in client browser

Tested browsers
------------------
* Mozilla Firefox 58
* Google Chrome 64
* Opera 50
* Microsoft Edge 41
* Internet Explorer 11

Installation
------------
1. Install Apache HTTP Server and PHP support for Raspbian (skip this step if already installed):

```
$ sudo apt-get install apache2 -y
$ sudo apt-get install php libapache2-mod-php -y
```

2. Download the `raspinfo.zip` file to the Apache www folder:
```
$ sudo wget https://github.com/HomeHedgehog/RasPinfo/archive/master.zip -O /var/www/html/raspinfo.zip
```
3. Unzip the `raspinfo.zip` to the Apache www folder:
```
$ sudo unzip /var/www/html/raspinfo.zip -d /var/www/html/raspinfo
```

4. Chmod the `get-data.sh` file to be executable:
```
$ sudo chmod +x /var/www/html/raspinfo/sh/get-data.sh
```

5. Usermod www-data:  
```
$ sudo usermod -G video www-data
```

Configuration
-------------
To configure the RasPinfo settings open the `config.php` in root folder with preferred text editor. Possible attributes to use:

* theme: blue, teal or grey
* date: y-m-d or d-m-y
* temperature: C or F

```
'theme' => 'teal',
'date' => 'y-m-d',
'temperature' => 'C'
```

If some of the attributes are not set correctly the software will use _default settings_ instead:

Features to implement
-----------------
* Graphical UI for configuration
* Finnish language support
* Multiple HDD monitoring

License
-------
RasPinfo is released under GNU Public License version 3, see [COPYING](https://github.com/homehedgehog) for more information.

Bootstrap v3.3.7 is released under MIT license, see https://github.com/twbs/bootstrap/blob/master/LICENSE for more information.

jQuery v3.3.1 is released under MIT license, see https://jquery.org/license for more information.
