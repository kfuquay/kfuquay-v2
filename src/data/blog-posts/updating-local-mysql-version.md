---
title: Updating Local MySQL Version
slug: updating-local-mysql-version
description: I updated from MySWL 5.7.3 to 8.0.29 on my 2019 MacBook Pro running macOS Monterey v12.4.  This is how I did it
publishDate: 1 Apr 2022
---

Documenting how I updated from MySQL `5.7.3` to `8.0.29` on my 2019 MacBook Pro (intel processor, running macOS Monterey v12.4).

There are many options for how to download, upgrade, and/or configure local MySQL versions.  Following these steps worked for me, but may not be the correct choice for everyone.

## 🥾 Steps

1. Preparation.  This process results in loss of any existing local databases.  I didn’t have any that I needed to keep, but if I had I would have exported & backed up those databases.

2. Download the latest General Availability Community Download - <https://dev.mysql.com/downloads/mysql/>

    Downloads must be compatible with your machines processor & OS.  For my MacBook I needed the `macOS 12 (x86, 64-bit)` package.  I chose to download the `.dmg` file.

    ![MySQL Community Downloads Selection](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ux9ffthhzr7hrrouhz74.png)

3. Open the `.dmg` file once it has downloaded & complete installation.

4. Check that MacBook is now using MySQL version 8.* & update `$PATH`.

    In the terminal run `mysql --version`

    The first time I ran this command I received an `Unknown command` error.  I needed to set a `$PATH` variable that points to the freshly downloaded binaries.

    I checked `System Preferences > MySQL` to find the correct value to use.

    Since I use [fish](https://fishshell.com/) I used the `fish_add_path` command to add my new path value.  Restarting my terminal and running `mysql --version` again confirmed that my `PATH` had been updated.

    ![MacBook system preferences screen with MySQL button highlighted](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ekmr0ch4sw0jzg0uai4z.png)

    ![MySQL preferences screen with path highlighted](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ebe46df2nioutwavmqi1.png)

    ![Terminal showing result of `mysql --version` command - "mysql  Ver 8.0.29 for macos12 on x86_64 (MySQL Community Server - GPL)"](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tuofpg6zqoco4no7zcmi.png)

5. Initialize local database.  

    At this point I set a password for my root user.  **If you use any software that is compatible with MySQL version 5.* you must use legacy authentication**

    ![MySQL preferences screen with "initialize database" button highlighted](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xk6ceg4igzqtj6tvih2z.png)

6. Download compatible version of workbench.

    I use mysql workbench during development and needed to download a version compatible with MySQL 8.*.  

    Similar to downloading the community server, I downloaded a version compatible with my computer & followed the installation prompts.

## 📚 Resources

- <https://dev.mysql.com/downloads/mysql/>
- <https://dev.mysql.com/downloads/workbench/>
- <https://dev.mysql.com/doc/>
