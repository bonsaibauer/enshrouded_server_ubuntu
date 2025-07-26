
🚧 **Experimental - No Guarantee** 🚧

This setup is **experimental** and may not work as expected.

# Experimental Setup for Enshrouded Server using systemd

## 1. Create a systemd service file for Enshrouded
To manage the Enshrouded server as a systemd service, create a custom service file using the following command:

```
sudo nano /etc/systemd/system/enshrouded.service
```

Then, add the following content to the service file:

```
[Unit]
Description=Enshrouded Server
Wants=network-online.target
After=network-online.target

[Service]
User=enshrouded
Group=enshrouded
WorkingDirectory=/home/enshrouded/
ExecStartPre=/usr/games/steamcmd +@sSteamCmdForcePlatformType windows +force_install_dir /home/enshrouded/enshroudedserver +login anonymous +app_update 2278520 +quit
ExecStart=/usr/bin/wine64 /home/enshrouded/enshroudedserver/enshrouded_server.exe
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

Save and close the file.

## 2. Enable the systemd service
To enable the service to start automatically, run:

```
sudo systemctl enable enshrouded
```

This will ensure that the Enshrouded server starts on boot.

---

Check out the repository [here](https://github.com/bonsaibauer/enshrouded_server_ubuntu) for more details and to explore the project.
