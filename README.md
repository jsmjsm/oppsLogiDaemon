# Opps Logi Darmon

![pic](./logi.png)

## Intro
In order to solve the problem that the `Logi Options Daemon` suspended from time to time on macOS, I kill the `LogiMgrDaemon` process every 45 minutes.

## Usage

just copy & paste

Run this command in your Terminal

```
crontab -l > conf && echo "*/45 * * * * logiMgrDaemonPid=\$(ps -ef | grep "LogiMgrDaemon" | sed '2d' | awk '{print \$2}') && kill \$logiMgrDaemonPid" >> conf && crontab conf && rm -f conf
```

Also, you can down the `FuckYouLogi` exec and place it on the desktop. Run it when you need.