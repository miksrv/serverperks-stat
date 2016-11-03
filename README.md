Killing Floor web stats
===============

This script is a web page that displays the tables and graphs with statistics of the players of the computer game Killing Floor. These statistics are taken from the .ini file, which is updated after each game raunad special server modded games (mutator) - '[ServerPerks'] [1].

> This mutator brings the perks stats tracking back the way it were in KF 2.5 in Unreal Tournament 2004: All player stats are being tracked by the server individually.

[DEMO PAGE](http://miksrv.ru/killingfloor)

----------------------

### Installation

To use this script must be put in a web server folder, and send statistics mutator (fashion) Killing Floor on the remote the FTP-server (your website with statistics).

At its hosting you will need to create an FTP user, set a password and specify the root directory of the script to the web statistics. ServerPerks mutator will use the FTP settings for that would update the file with the statistics of players.

#### Setting up a web statistics script

If the mutator ServerPerks will unload statistics in the root folder of the script, no additional configuration is not necessary to produce. Otherwise, in index.php on line # 47 specify the path to the file with the statistics:

```php
    $ini_array = parse_ini_file("ServerPerksStat.ini", TRUE);
```

#### Setting mutator 'ServerPerks'

Make sure you assign these settings in ServerPerks.ini:

```
RemoteDatabaseURL=FTP_URL_ADDRES
RemotePassword=FTP_USER_PASSWORD
RemoteFTPUser=FTP_USER_NAME
RemoteFTPDir=
bUseRemoteDatabase=True
bUseFTPLink=True
bDebugDatabase=False
FTPKeepAliveSec=60
bUploadAllStats=True
```

----------------------

### Author
* WebSite: http://miksrv.ru
* Facebook: http://facebook.com/miksrv.ru
* Instagram: http://instagram.com/greenexp.ru/

----------------------

### Components used

The following components and classes were used in the development of applications:

* [Highcharts] [2] - Highsoft AS, Sentrumsgata, 6893 VIK I SOGN, Norway.
* [DataTables] [3] - SpryMedia Ltd is registered in Scotland, company no. SC456502.

   [1]: <http://forums.tripwireinteractive.com/forum/killing-floor/killing-floor-modifications/coding-aa/36898-mut-per-server-stats>
   [2]: <http://www.highcharts.com/>
   [3]: <https://datatables.net/>