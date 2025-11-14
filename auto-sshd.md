```bash
sudo vim /usr/local/bin/check_ssh.sh
```

```bash
#!/bin/bash

# --- Configuration ---
TARGET_PUBLIC_IP="104.203.110.193"
# ---------------------


# Get the ip
CURRENT_IP=$(curl -s --max-time 5 https://ifconfig.me/ip)

if [ -z "$CURRENT_IP" ]; then
        echo "Could not fetch public ip for some reason. Disabling ssh"
        sudo systemctl stop ssh
        exit 1
fi

if [ "$CURRENT_IP" == "$TARGET_PUBLIC_IP" ]; then
       if ! systemctl is-active --quiet ssh; then
                echo "Public ip ($CURRENT_IP) matches target. starting ssh"
                sudo systemctl start ssh
        fi
else
        if systemctl is-active --quiet ssh; then
                echo "Public ip ($CURRENT_IP) does not match target. Stopping ssh"
                sudo systemctl stop ssh
        fi
fi
```

```bash
sudo chmod +x /sr/local/bin/check_ssh_ip.sh
sudo crontab -e
```

append this to the bottom:
```cron
*/5 * * * * /usr/local/bin/check_ssh_ip.sh
```


