---
layout: post
title:  "Set up cron jobs on ubuntu"
date:   2017-3-22
categories: ["linux"]
author: "Leiming Yu"
---
### step 1: install cron
```bash
sudo apt-get update && sudo apt-get install cron
```

### step 2: add crobjob
```bash
sudo crontab  -e
```
Add your script to the file with running frequency. (See example below.)

```bash
PATH=/usr/sbin:/usr/bin:/sbin:/bin                                              
# backup at 12 Sunday  weekly                                                   
0 12 * * 0  /home/leiming/backup.sh
```

### step 3: start the service without reboot
```bash
sudo service cron stop  && sudo service cron start 
```

### step 4: check your job 
```bash
sudo crontab -l
```

### step 5: run job at startup 
```bash
@reboot /home/vivek/bin/installnetkit.sh
```

### step 6: start crond automatically after reboot
```bash
sudo update-rc.d cron defaults
```

### Reference
* https://www.liquidweb.com/kb/how-to-display-list-all-jobs-in-cron-crontab/
* https://vexxhost.com/resources/tutorials/how-to-use-cron-jobs-for-automation-on-ubuntu-14-04/
* https://www.cyberciti.biz/faq/linux-execute-cron-job-after-system-reboot/
