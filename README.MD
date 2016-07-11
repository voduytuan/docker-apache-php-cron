# Docker image with Apache, PHP and Crontab #

## Introduction ##
Use this image if you want to add cron for running your php script by schedule. This image is base on my docker-apache-php image, so that, you can provide external website by mounting your website to "/var/www/site" when create container. See more at [https://github.com/voduytuan/docker-apache-php]

## Customize crontab and cronjob.php ##
In docker image, The crontab file is put at "/etc/cron.d/crontab" and php files is put at "/var/www/site/cronjob.php". You can override the crontab and php script by mount volumn to your crontab and php files. Such as:
`... -v /path/to/your/crontab:/etc/cron.d/crontab ... -v /path/to/your/php/cron:/var/www/site/cronjob.php..."

## Example ##
`docker run -ti -d \
  -v /path/to/website:/var/www/site \
  -v /path/to/my/crontab:/etc/cron.d/crontab \
  -v /path/to/my/cronjob.php:/var/www/site/cronjob.php \
  voduytuan/docker-apache-php-cron`
