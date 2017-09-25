## Pinger in Python

```python
#!/usr/bin/env python
import os
import platform
import subprocess


proc = subprocess.Popen("ping -q -c 1 www.google.com", shell=True,stdout=subprocess.PIPE,)

stdout_value = proc.communicate()[0]
print stdout_value
```

## IP Address Finder

```python
#!/usr/bin/env python
import os
import platform

def ip_addresses():

	if platform.system() == "Darwin":
		os.system("ifconfig  | grep -E 'inet.[0-9]' | grep -v '127.0.0.1' | awk '{ print $2}'")
		os.system("ifconfig  | grep -E 'inet6.[0-9]' | grep -v '127.0.0.1' | awk '{ print $2}'")

	if platform.system() == "Linux":
		os.system("ifconfig  | grep 'inet addr:'| grep -v '127.0.0.1' | cut -d: -f2 | awk '{ print $1}'")
		os.system("ifconfig  | grep 'inet6 addr:'| grep 'Global' | grep -v 'fe80' | awk '{print $3}'")

if __name__ == '__main__':
	ip_addresses()
```