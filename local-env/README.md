# Local ENV installation

This step by step guide will lead you through your local environment setup. Please follow carefully and do not miss steps below.

**WARNING**: This guide is written for Mac users only. If you are on Unix or Windows, please Google how to execute step 1 and 2 best, sorry... ;-)

## Pre requisites

1. Local docker environment installed. Run `docker compose version` to verify
2. Your favorite IDE installed (this guide uses `VSCode`)
3. No other services running/listening on `localhost:8000`

## Installation

1. Open system DNS host configuration: `sudo nano /private/etc/hosts`
2. Add `birs.local` to your local environment host configuration by adding following line to the end of the file: `127.0.0.1 birs.local`.
3. Save changed file (sudo access required) and flush your local DNS cache: `sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder`
4. Close all browsers and open shells and before continuing (this ensure browser DNS cache is also cleaned). To test your changes, run `ping birs.local` in a newly opened Terminal window. You should get an answer from `127.0.0.1`.
5. Navigate into `wordpress` folder and duplicate/rename `.env.example` to `.evn`
6. Add your own secrets for each config/credential in `.env` (note: feel free to use default passwords)
7. Run local Docker environment: `docker-compose up -d`
8. Open Wordpress config site: http://birs.local:8000/
9. Select `Deutsch Schweiz(Du)` as default language and continue with next step
10. Add following config credentials:
 - Website name: `Black Bird Brew Society`
 - User: `admin`
 - Password: use pre-generated password (make sure to copy the value before continue with next step...)
 - Email: your public email address
 11. Finish installation setup and start using your Wordpress instance

 ## Use wordpress
 After the installation, you can access your local Wordpress installation under: http://birs.local:8000/

 To open the dashboard, navigate to: http://birs.local:8000/wp-admin/

 ## Use PHPMyAdmin
 Additionally to your wordpress installation `docker-compose` will also setup up `PHPMyAdmin` to simplify MariaDB management.

 To use PHPMyAdmin, simply open: http://birs.local:8080/
 