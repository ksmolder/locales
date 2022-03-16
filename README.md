# locales
This project contains non-official locale definitions for Linux.

For official locale definitions compatible with glibc, check https://lh.2xlibre.net/.
This site also contains an installation script in Python for Debian based systems (untested).

## How to install
The following has been tested on Ubuntu 20.04 (commands need to be executed as root).

* Add the locale definition to the list of supported locales:
  `echo 'en_BE.UTF-8 UTF-8' >> /usr/share/i18n/SUPPORTED`
* Copy the locale definition file to the locale definitions directory: 
  `cp en_BE /usr/share/i18n/locales/`
* Compile the new locale: 
  `localedef -f UTF-8 -i en_BE en_BE.UTF-8`
* Add the locale to the list of locales that should be generated: 
  `echo 'en_BE.UTF-8 UTF-8' >> /var/lib/locales/supported.d/en`
* Generate locales
  `locale-gen --purge`

## List of locales

* **en_BE**: Copy of fr_BE with the following changes:
  * Names of weekdays, months,... in English
  * ISO date format (YYYY-mm-dd'T'HH:MM:SS Z, e.g. 2022-03-16T21:48:28 CET)
