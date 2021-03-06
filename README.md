# docker-infinitewp
A Docker container for running InfiniteWP

## Install

1. Download InfiniteWP from https://infinitewp.com/installing-download/<br>This will download a package **IWPAdminPanel_v\*.zip**.
2. Save package to root of this repository.
3. `docker-compose build --build-arg INSTALL=true`<br>
   The build arg leaves the install folder inplace to allow first run wizard to create the config.php file.
4. Create an empty config.php file.<br>
   `touch config.php`
5. Set permissions<br>
   `chmod 666 config.php`
6. `docker-compose up`<br>
   _Wait for "MySQL init process done. Ready for start up" in log_
7. Open browser <http://localhost:3000>
8. Complete InfiniteWP Installation below.

----

### InfiniteWP Installation

#### Licence Agreement

Click the Agree & Install button.

#### Server Requirements

Will automatically check and pass to DB Details.

#### DB Details

| Name                 | Name                 |
|----------------------|----------------------|
| DB Host              | database             |
| DB Port              | 3306                 |
| DB Name              | infinitewp           |
| DB Table Name Prefix | iwp_                 |
| DB Username          | infinitewp           |
| DB Password          | password             |

Click the Next, Create Login button.

#### Create Login

Enter email and password.

Click the Next, Install button.

#### Installation

Installed Successfully :)

Note: Ignore the "We are are not able to remove the **install** folder" warning. A second build of the image below will resolve this.

----

9. \<Ctrl+C\> Docker compose logs.
10. `docker-compose down`
11. Reset permissions on config file.<br>
    `chmod 644 config.php`
12. Rebuild Docker image without install directory.<br>
    `docker-compose build`

You now have a Docker image tagged infinitewp:latest.
