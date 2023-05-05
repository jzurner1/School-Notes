Localization is the ability for a system to adapt to a specific location, specifically handling characters contained in the local language.

The first step is choosing an appropriate character set for the location.

In Linux, locale information is stored in a special set of environment variables. Programs that need to determine the locale of the Linux system just need to retrieve the appropriate environment variable to see what character set to use.

Linux provides the `locale` command to view these environment variables. They are formatted as `language_country.character set`, such as `en_US.UTF-8`. Other settings can be seen using the `-ck` flag, such as `locale -ck LC_MONETARY`, which shows monetary options.

In order to change these environmental variables, you would use the `export` command