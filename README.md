# multi-systemd-services


###### Systemd is a suite of software that provides fundamental building blocks for a Linux operating system

## Adding the application services to systemd

After we finished the creation of the four systemd unit files, we need to copy them to the systemd configuration directory:

```
$ sudo cp startApp.service app1.service app2.service /etc/systemd/system/
```

Next, we have to ask systemd to reload its configuration:

```
$ sudo systemctl daemon-reload
```

## Testing the application services

After all the work we’re now ready to exercise our configuration. First, let’s enable all the application services:

```
$ sudo systemctl enable startApp app1 app2
```

To start all the services, you can type:
```
$ sudo systemctl start startApp
```

We can disable any service independently of other services. Let’s stop the service app2 and disable it:
```
$ sudo systemctl stop app2
$ sudo systemctl disable app2
```

Systemd logs its messages into the journal. Let’s list the recent log entries with:

```
$ journalctl -e
```


## Conclusion:

systemd is a standard service manager any Linux administrator is familiar with
systemd is battle tested to the extent your proprietary solution probably cannot be
You can discover many other useful systemd features which you can employ right away

# Have fun!
