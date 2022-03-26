---
title: Singularity Notes
#subtitle: 
date: 2022-03-26
categories: ["bash", "singularity"]
layout: single
classes: wide
---
# Singularity Permission Set #
Commands to config namespace and subuid subgid configs:
```
# singularity config fakeroot --add username 
# echo "user.max_user_namespaces=10000" | sudo tee -a /etc/sysctl.conf
# echo 10000 | sudo tee -a /proc/sys/user/max_user_namespaces
```

# Instances #
Run containers with background services, for example allowing you to run httpd services etc
```
# singularity instance start -B var_log_httpd24:/var/log/httpd24 -B httpd_run:/opt/rh/httpd24/root/etc/httpd/run/ -B dex_run:/etc/ood/dex/run OOD.sif oodhttp
INFO:    instance started successfully
```
```
# singularity instance list
INSTANCE NAME    PID      IP              IMAGE
oodhttp          6789                     /home/524070-su/Singularity/Containers/recipefiles/OOD/OOD.sif
```
```
# singularity shell instance://oodhttp
Singularity>
```
```
# singularity instance stop oodhttp
INFO:    Stopping oodhttp instance of /home/524070-su/Singularity/Containers/recipefiles/OOD/OOD.sif (PID=6789)
```
