<h2>WiFi Python Script</h2>
<a href="forensics">Back</a>
<p>I got this script from a fellow student who discovered it while troubleshooting a password issue for his home business. I can see this script being useful in a forensics settting. This script will show you what WiFi networks a computer has connected to, as well as the password that was used.</p>
<p>If your business has security policies that prevent employees from connecting to outside networks, you could run this script to see if the employee had broken this agreement.</p>

```python
import subprocess
import re
command_output = subprocess.run(["netsh", "wlan", "show", "profiles"], capture_output = True).stdout.decode()
profile_names = (re.findall("All User Profile     : (.*)\r", command_output))
wifi_list = []
if len(profile_names) != 0:
    for name in profile_names:
        wifi_profile = {}
        profile_info = subprocess.run(["netsh", "wlan", "show", "profile", name], capture_output = True).stdout.decode()
        if re.search("Security key           : Absent", profile_info):
            continue
        else:
            wifi_profile["ssid"] = name
            profile_info_pass = subprocess.run(["netsh", "wlan", "show", "profile", name, "key=clear"], capture_output = True).stdout.decode()
            password = re.search("Key Content            : (.*)\r", profile_info_pass)
            if password == None:
                wifi_profile["password"] = None
            else:
                wifi_profile["password"] = password[1]
            wifi_list.append(wifi_profile) 

for x in range(len(wifi_list)):
    print(wifi_list[x]) 
```