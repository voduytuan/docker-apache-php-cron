# Docker image with Apache, PHP and Crontab #

## Introduction ##
Use this image if you want to add cron for running your php script by schedule. This image is base on my docker-apache-php image, so that, you can provide external website by mounting your website to "/var/www/site" when create container. See more at [https://github.com/voduytuan/docker-apache-php]



## Docker Hub ##
Docker image hosted at: [https://hub.docker.com/r/voduytuan/docker-apache-php-cron/]

## Important ##
- Do not try to mount your custom `crontab` file, because the problem of file owner will prevent cron run your crontab file. If you want to change the cron rules, just create your custom `crontab.sh` file and mount (-v) to `/var/www/crontab.sh` in docker run command.
- In case you want to use your crontab.sh, do not forget to CHMOD 0755 (executable) for your `crontab.sh` file.

## Example ##
```
docker run -ti -d \
  -v /path/to/website:/var/www/site \
  -v /path/to/my/crontab.js:/var/www/crontab.js \
  -v /path/to/my/cronjob.php:/var/www/site/cronjob.php \
  voduytuan/docker-apache-php-cron
```
