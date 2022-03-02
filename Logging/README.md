## Network switch syslog

All network switch logs are forwarded to Graylog, this including but isn't limited to 

* Port Up and down
* Authentication
* Interfaces up and down

## Docker container logs

Every container sends all logs (syslog, access , error as needed) to Graylog, this is including but not limited to

* Nginx access \ error logs
* Container start stop logs

## Physical server syslog

Both physical production servers send logs to Graylog

## Cronjob email notification

Every single cronjob will generate an email with stdout sent after run
