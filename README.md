# Hubot as a Service
A systemd service file to start Hubot. Handles reboots and crashes.

###### Getting Started
1. Set ENV variables and location/user in the service file.
2. Place in `/etc/systemd/system`
3. To load the service file: `systemctl daemon-reload`
4. To start the service: `service hubot start`
5. Verify Hubot is active in Slack

###### Viewing Console Output
Hubot's console output can be viewed with: `tail /var/log/syslog`

###### Updating
To update the service file ---
1. Stop the Hubot service: `service hubot stop`
2. Copy over the new service file or edit the existing one.
3. Reload it: `systemctl daemon-reload`
4. Start it: `service hubot start`
5. Re-verify Hubot is active in Slack

###### Restarting Hubot
To restart Hubot: `service hubot restart`

###### Notes
ENV Variables should not include any quotes or escaping (Correct Example: `Environment=HUBOT_DARK_SKY_DEFAULT_LOCATION=90210`)

For more information on preventing restart loops with StartLimitInterval & StartLimitBurst, [please see the manual](https://www.freedesktop.org/software/systemd/man/systemd.unit.html#StartLimitIntervalSec=).
