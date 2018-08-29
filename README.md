# FreeNAS Useful Scripts

## Disclaimer

These scripts are based on [FreeNAS forums user Bidule0hm scripts](https://forums.freenas.org/index.php?threads/scripts-to-report-smart-zpool-and-ups-status-hdd-cpu-t%C2%B0-hdd-identification-and-backup-the-config.27365/) which are themselves based on [FreeNAS forums user joeschmuck scripts](https://forums.freenas.org/index.php?threads/set-up-smart-reporting-via-email.6211/) and [FreeNAS forums user titan_rw scripts](https://forums.freenas.org/index.php?threads/set-up-smart-reporting-via-email.6211/). Though I still did a lot of work, like rewriting large parts of them and doing some overall code cleaning.

## About the project

This is a collection of useful scripts for FreeNAS admins that want to have more reporting than just what's included in the OS, display useful information like HDD and CPU temperature easily in a terminal and scripting the backup of the FreeNAS config.

## Roadmap

- Change how SMART and zpool reports are displayed in order to use native HTML tables.

## Prerequisites

- FreeNAS 11.1+

## Installation

```bash
git clone https://github.com/PlqnK/freenas-useful-scripts.git
cd freenas-useful-scripts
for file in *.example*; do cp $file $(echo $file | sed -e 's/.example//'); done
```

You then need to adapt the variables in the `user.conf` file according to your setup and needs.

Next, set the scripts as executable:

```bash
find . -name "*.sh" -exec chmod u+x {} \;
```

Finally you will need to create cron jobs in the FreeNAS WebUI in order to execute the reporting and backup script on a schedule. [The FreeNAS documentation explains how to do it.](http://doc.freenas.org/11/tasks.html#cron-jobs)

## Contributing

Contributions in the form of issues or PR are welcome if you see any area of improvement or if you have new ideas for useful scripts!

## License

This project is released under the [BSD 3-Clause License](https://opensource.org/licenses/BSD-3-Clause). A copy of the license is available in this project folder.