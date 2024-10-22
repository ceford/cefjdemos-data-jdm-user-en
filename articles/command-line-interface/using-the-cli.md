<!-- Filename: J4.x:Using_the_CLI / Display title: Using the CLI -->

## The Command Line Interface (CLI)

If you have terminal access to the server running your website you can
use the Joomla CLI to carry out routine tasks without the need to use
Joomla user login credentials. Even without terminal access, such as on
some shared hosting accounts, you can run CLI commands using cron jobs.
CLI commands are often quicker or more convenient than equivalents
accomplished through the Joomla (or cPanel) Administrator interface.
Site backup and setting site offline/online are examples where you might
prefer to use the CLI.

Joomla core has about 30 useful commands and you can add more with
additional extensions. For example, you could fetch external data such
as Geolocation or Exchange rate data for a custom component.

## Using the CLI

The CLI is used by invoking the command line php executable. This is
often different from that used by a web server such as Apache. If you
are using a cron job you may have to supply the complete path to the php
executable, like this:

    /usr/local/bin/php /home/username/public_html/[optional subfolder]/cli/joomla.php

Otherwise, when using the terminal command line, change directory to the
Joomla cli directory and get started running the command without
parameters:

    cd /home/username/public_html/[optional subfolder]/cli
    php joomla.php

![List of commands](../../../en/images/command-line-interface/cli-command-list.png)

And try out some help commands to become familiar with what to expect:

    php joomla.php help
    php joomla.php list
    php joomla.php help cache:clean
    php joomla.php help config:get

Each of the Help descriptions and usage strings are hard-coded in
Console library files or in third party plugins.

Try some simple action commands:

    php joomla.php config:get debug
    php joomla.php cache:clean
    php joomla.php site:down
    php joomla.php site:up

## Options

If you are calling commands from a cron you may not wish to see any
output:

    php joomla.php -q cache:clean

Note that options may use a space or = sign but variables must use an =
sign:

    php joomla.php session:gc --application administrator
    php joomla.php session:gc --application=administrator

    php joomla.php config:set debug=true

## Commands

A brief explanation of each core command.

### Cache

Clear expired entries from the system cache:

    php joomla.php cache:clean --help
    php joomla.php cache:clean

![Output of cache clean](../../../en/images/command-line-interface/cli-cache-clean.png)

    php joomla.php cache:clean expired

![Output of cache clean expired](../../../en/images/command-line-interface/cli-cache-clean-expired.png)

### Config

Get or set a configuration variable, one of the variables in
configuration.php or a group of variables. Valid groups are db, session,
mail,

    php joomla.php config:get debug --help
    php joomla.php config:get debug

![Output of config get debug](../../../en/images/command-line-interface/cli-get-debug.png)

    php joomla.php config:set debug=true

![Output of config set debug](../../../en/images/command-line-interface/cli-set-debug.png)

    php joomla.php config:get --group session

![Output of config get group session](../../../en/images/command-line-interface/cli-config-get-group-session.png)

### Core

Check for updates or update Joomla.

    php joomla.php core:check-updates --help
    php joomla.php core:check-updates

![Output of core check updates](../../../en/images/command-line-interface/cli-check-updates.png)

    php joomla.php core:update --help
    php joomla.php core:update

![Output of cor update](../../../en/images/command-line-interface/cli-core-update.png)

### Database

Export or Import the database. You can export or import all tables or a
selected table. Do not use this feature to import all tables of a
multi-lingual site. There is a problem that could stop Smart Search
working completely.

    php joomla.php database:export --help
    php joomla.php database:export --table f4rc2_banners --folder /home/username/tmp/mydb (one table)
    php joomla.php database:export --folder /home/username/tmp/mydb (all tables)

    php joomla.php database:import --help
    php joomla.php database:import --table /home/username/tmp/mydb/f4rc2_banners (one table)
    [ERROR] The /home/username/tmp/mydb/f4rc2_banners.xml file does not exist.
    php joomla.php database:import --folder /home/username/tmp/mydb (all tables in this folder)

### Extension

List, Discover, Install or Remove extensions.

    php joomla.php extension:list --help
    php joomla.php extension:list
    php joomla.php extension:list --type component
    php joomla.php extension:list --type file
    php joomla.php extension:list --type language
    php joomla.php extension:list --type library
    php joomla.php extension:list --type module
    php joomla.php extension:list --type package
    php joomla.php extension:list --type plugin
    php joomla.php extension:list --type template

    php joomla.php extension:discover --help
    php joomla.php extension:discover
    php joomla.php extension:discover:list
    php joomla.php extension:discover:install --eid=

    php joomla.php extension:install --help
    php joomla.php extension:install --path=
    php joomla.php extension:install --url=

    php joomla.php extension:remove --help
    php joomla.php extension:remove

### Finder

Purges and rebuilds the index (search filters are preserved).

    php joomla.php finder:index --help
    php joomla.php finder:index
    php joomla.php finder:index purge

![Output of finder index purge](../../../en/images/command-line-interface/cli-finder-index-purge.png)

### Scheduler

List, change state, or run scheduled tasks.

    php joomla.php scheduler:list --help
    php joomla.php scheduler:list

    php joomla.php scheduler:state --help
    php joomla.php scheduler:state (interactive prompt for task id)

    php joomla.php scheduler:run --help
    php joomla.php scheduler:run --id ID
    php joomla.php scheduler:run --all

### Session

Perform session garbage collection.

    php joomla.php session:gc --help
    php joomla.php session:gc
    php joomla.php session:gc --application administrator

    php joomla.php session:metadata:gc --help
    php joomla.php session:metadata:gc

### Site

Puts the site offline or online.

    php joomla.php site:down --help
    php joomla.php site:down

    php joomla.php site:up --help
    php joomla.php site:up

### Update

Checks for pending extension updates. Removes old files which should
have been deleted during a Joomla update

    php joomla.php update:extensions:check --help
    php joomla.php update:extensions:check

    php joomla.php update:joomla:remove-old-files --help
    php joomla.php update:joomla:remove-old-files

![Output of update joomla remove old files](../../../en/images/command-line-interface/cli-update-remove-old-files.png)

### User

List and manage users.

    php joomla.php user:list --help
    php joomla.php user:list

    php joomla.php user:add --help
    php joomla.php user:add --username cinderella --name Cinderella --email cinders@localhost --usergroup Manager (prompt for password)
    php joomla.php user:add (prompts for data)

![Output of user add with prompts](../../../en/images/command-line-interface/cli-add-user.png)

    php joomla.php user:addtogroup --help
    php joomla.php user:addtogroup (prompts for data)
    php joomla.php user:addtogroup --usernam=cinderella --group=Manager

    php joomla.php user:removefromgroup --help
    php joomla.php user:removefromgroup (prompts for data)
    php joomla.php user:removefromgroup --usernam=cinderella --group=Manager

    php joomla.php user:reset-password --help
    php joomla.php user:reset-password (prompts for data)
    php joomla.php user:reset-password --username=cinderella (prompts for password)

    php joomla.php user:delete --help
    php joomla.php user:delete (prompts for username)
    php joomla.php user:delete --username=cinderella (prompts for confirmation - y to confirm)
