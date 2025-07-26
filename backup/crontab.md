
🚧 **Experimental - No Guarantee** 🚧

This setup is **experimental** and may not work as expected.

# Crontab Setup

## 1. Add Crontab Entries
To edit the crontab, use the following command:

```
sudo crontab -e
```

Then, add the following two lines to the crontab file:

```
0 4 * * * TZ="Europe/Berlin" sudo systemctl stop enshrouded && echo "$(date) - enshrouded stopped" >> /var/log/enshrouded-cron.log
30 4 * * * TZ="Europe/Berlin" sudo systemctl start enshrouded && echo "$(date) - enshrouded started" >> /var/log/enshrouded-cron.log
```

Save and close the file. Set write permissions for the log file used by the cronjob:

```
sudo touch /var/log/enshrouded-cron.log
sudo chmod 664 /var/log/enshrouded-cron.log
```

### 1.1 Verify and Start the Cron Service
First, ensure that the Cron service is running. Open a terminal and run the following command:

```
sudo systemctl status cron
```

If the service is not running, you can start it with this command:

```
sudo systemctl start cron
```

To ensure that Cron starts automatically with the system, run:

```
sudo systemctl enable cron
```

## 2. Edit `.bashrc`
Open the `.bashrc` file in your home directory:

```
nano ~/.bashrc
```

### 2.1 Add the Following Code
Add the following lines at the end of the file:

```
if [ -f /var/log/enshrouded-cron.log ]; then
    echo "Last 10 entries from enshrouded-cron.log:"
    tail -n 10 /var/log/enshrouded-cron.log
else
    echo "Log file /var/log/enshrouded-cron.log does not exist."
fi
```

### 2.2 Apply Changes
To apply the changes immediately, reload the `.bashrc` file:

```
source ~/.bashrc
```

---

Check out the repository [here](https://github.com/bonsaibauer/enshrouded_server_ubuntu) for more details and to explore the project.
