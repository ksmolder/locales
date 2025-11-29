> [!WARNING]
> This repository has been migrated to [Codeberg](https://codeberg.org/smeulski/locales)

# locales
This project contains non-official locale definitions for Linux.

For official locale definitions compatible with glibc, check https://lh.2xlibre.net/.
This site also contains an installation script in Python for Debian based systems (untested).

## How to install
Note: all commands need to be run as root.

Ubuntu (tested on 20.04).

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
  
Fedora (tested on 43)
* Copy the locale definition file to the locale definitions directory: 
  `cp en_BE /usr/share/i18n/locales/`
* Compile the new locale: 
  `localedef -f UTF-8 -i en_BE en_BE.UTF-8`
* The above command should add the compiled locale data the archive file _/usr/lib/locale/locale-archive_.

## List of locales

* **en_BE**: Copy of fr_BE with the following changes:
  * Names of weekdays, months,... in English
  * ISO date format (YYYY-mm-dd'T'HH:MM:SS Z, e.g. 2022-03-16T21:48:28 CET)
