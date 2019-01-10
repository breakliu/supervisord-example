# Usage

## 1. Install
* pip install supervisor
* git clone
* supervisord -> /etc/, edit conf if you need
* CentOS 7 systemd: supervisord.service -> /usr/lib/systemd/system/

## 2. Changing Limits for files
```
# /etc/security/limits.conf
*         -       nofile      100000
*         hard    nofile      100000
*         soft    nofile      100000
root      hard    nofile      100000
root      soft    nofile      100000
```

## 3. Systemd Commands

* start service: `systemctl start supervisord`
* view service status: `systemctl status supervisord`
* auto start service on system startup: `systemctl enable supervisord`

## 4. Supervisord Common Commands
* current status: `supervisorctl status`
* check if config update: `supervisorctl reread`
* reload programs only config update: `supervisorctl update`
* reload all programs: `supervisorctl reload`
* restart one program: `supervisorctl restart worker`
* generate default supervisord.conf: `echo_supervisord_conf > supervisord.conf`
* maybe: `supervisorctl -c /etc/supervisord/supervisord.conf`
