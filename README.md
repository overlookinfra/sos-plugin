# Overlook Infratech Support Bundle Plugin

This repository contains an upstream variant of the SOS script's openvox/puppet plugin for situations where your distribution:
- Doesn't come with a new enough version of the SOS package in your repositories, and/or...
- Is unable to run an upstream version due to python incompatibility

For example, you're running an EL8 machine which ships python 3.6. In that situation we may require you to download this python file, which has the necessary upstream changes for openvox/puppet, as a loadable plugin.

Once you have the overlookinfra_puppet.py file, place it under the following directory (or equivelant python dir):
```
/usr/lib/python3.6/site-packages/sos/report/plugins/
```

Then, modify the following file:
```
/etc/sos/sos.conf
```

And set the following under the "report" section:
```
[report]
skip-plugins = puppet
```

Then run the following command:
```
sudo sos report
```

Thiv should provide you with a `/var/tmp/sosreport-*.tar.xz` file. Please attach it to your support ticket.

## Note
It is preferrable to download the file than to copy/paste. For example, navigating to the file in GitHub and clicking "Raw" in the upper right. From there you can right click > save, or copy the url for use with curl/wget.


