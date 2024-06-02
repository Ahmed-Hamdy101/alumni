# alumni project collage 

# Overview :
-  Requirements
-  Project Structure
-  Directories
-  Database
-  Studnet portal

# Requirement :
 - Apache Server installed : prefered xammp or mamp
 - MYSQL Database

## Project Structure :
the structure of project is type of MVC 
Model , View , Controller this Architecture is responsibe for arrangement and your code be more readable by others.

### Directories
- each backend process has directory this directory contains on application this app diveded to sub directories
- mode - controller - partials
  
- 1 - `Directory` is `alumni`
-  alumni contains on :
  - login student
  - storage : to store event and images student
  - student application : the logic of login page 
  - portal application : dsahboard of student
  - admin system management for collage : CRUD APPLICATION For Management System
    
- 2 - `Directoy` is `assets`
- assets contains on :
    - css files
    - js files
    - libaray files
     
- 3 - `Directory` `errors` resposible for display errors when the user to unknown directory / unknown routes
- errors contains on :
  - `404-page`

- 4 - `Dir` `home` is responsible for display `home` page and all content of home paeg `/` 
- home contains on :
- `index.php`

- 5 - `Dir` `pages` is responsible for display `pages` of home page like `sub-dir` `CV` `Contact` `PHPMAILER`


#### Database 
- 1 Intialize connection :
   - open `phpmyadmin` you can download Xammp or MAMP to open it
   - create new `database` called `alumni`:
   - import `sql file` `alumni`
- 2 create new file  `config.php` and `db_connection.php`
- in `config.php` :
 ```php
// credential connections
<?php
define("BASE_URL", "/");
define('DB_HOST', "localhost");
define("BASE", "/");
define("DB_USERNAME", "root");
define("DB_PASSWORD", "");
define("DB_DATABASE", "alumni");
define("DB_DATABASE_PORT", "3306");
?>
```
- in `db_connection.php`
  ```php
                <?php
                // start db connection 
                try {
                    $db = new PDO("mysql:host=" . DB_HOST . ";dbname=" . DB_DATABASE . ";port=" . DB_DATABASE_PORT . ";", DB_USERNAME, DB_PASSWORD);
                    $db->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
                    $db->exec("SET NAMES'utf8'");
                } catch (Exception $e) {
                    echo $e->getMessage();
                    exit;
                }
   ```
  
  ####  Routes :
   |  Route |  Page Title | http status code |
   | ----   | ------------ | ----------- |
   |[localhost:/](#) |  Home        | 200 Ok      |
   | http://localhost/cv | CV    | 200 ok   |
   | [http://localhost/about](http://localhost/about) | about    | 200 ok   |
   | [http://localhost/event](http://localhost/event) | Event    | 200 ok   |
   | [http://localhost/contact](http://localhost/contact) | Contact    | 200 ok   |
   | [http://localhost/login](http://localhost/login) | Login    | 200 ok   |
   | [http://localhost/stories](http://localhost/stories) | Stories    | 200 ok   |
   | [http://localhost/acheivment](http://localhost/acheivment) | acheivment    | 200 ok   |
   | [http://localhost/speaker](http://localhost/speaker)| Speaker    | 200 ok   |


  #### Student Portal :
   - Dashboard of student for display data on page
     
   |  Route |  Page Title | http status code | Type |
   | --------   | ------------ | ----------- | ----------- |
   |[/portal_?page=_dashboard](/portal?page=_dashboard_portal) |  Portal Dashboard  | 200 Ok      |GET |
   |[/portal_?page=_profile_student](http://localhost/portal?page=_profile_student) | profile data |200| GET | 
   |[/portal_?page=_register_portal](http://localhost/portal?page=_register_portal)| create register course   | 200 ok    |POST |
   |[/portal_?page=_getcourse_portal](http://localhost/portal?page=_getcourse_portal) | get registered student  | 200 ok   |GET |
   |[/logout](/logout) | logout    | 200 ok   |GET |



  #### admin Portal :
   - Dashboard of management system collage for CRUD Operations 
     
   |  Route |  Page Title | http status code | Type |
   | --------   | ------------ | ----------- | ----------- |
   |[/dashboard.php?page=_dashboard](/portal?page=_dashboard) |  Dashboard | Display Data of student and event | | 200 Ok      |GET |
   |[/dashboard.php?page=_dashboard_management_events_students](http://localhost/alumni/su_admin_13039/dashboard.php?page=_dashboard_management_events_students)| Management |200|PATCH | 
   |[/dashboard.php?page=_create](http://localhost/alumni/su_admin_13039/dashboard.php?page=_create) | switch page create   | 200 ok    |POST |
   |[/dashboard.php?page=_create_student](http://localhost/alumni/su_admin_13039/dashboard.php?page=_create_student) | create student  | 200 ok   |POST |
   |[/dashboard.php?page=_create_event](http://localhost/alumni/su_admin_13039/dashboard.php?page=_create_event) | create event  | 200 ok   |POST |
   |[/dashboard.php?page=_manage_admin](http://localhost/alumni/su_admin_13039/dashboard.php?page=_manage_admin) | manage admin setting | 200 ok   |PATCH |
   |[/dashboard.php?page=_enroll_event](http://localhost/alumni/su_admin_13039/dashboard.php?page=_enroll_event) | enroll page    | 200 ok   |GET |
   |[/logout](/logout) | logout    | 200 ok   |GET |

