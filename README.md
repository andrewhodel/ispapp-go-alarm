# ispapp-go-alarm

Connects to the ISPApp server using your sessionKey and alarms with sound when hosts or specified hosts are offline.

# Building

```
git clone https://github.com/ispapp/ispapp-go-alarm
cd ispapp-go-alarm
```

Modify the -hostKey and -domain arguments and run this command.

`GO111MODULE=off go run ispapp-go-alarm.go -domain "dev.ispapp.co" -sessionKey "yoursessionkey"`

Only alarm about specific hosts with the -alarmHosts argument.

`GO111MODULE=off go run ispapp-go-alarm.go -domain "dev.ispapp.co" -sessionKey "yoursessionkey" -alarmHosts "host1,host2"`

Ignore specific hosts with the -ignoreHosts argument.

`GO111MODULE=off go run ispapp-go-alarm.go -domain "dev.ispapp.co" -sessionKey "yoursessionkey" -ignoreHosts "host1,host2"`

# Packaging a non-os bundled ca certificate in the program

Storing a ca-bundle file in ispapp-go-alarm.go for ease of distribution.

```
cd tools
go ca-bundle-to-hex-string.go -in /path/to/domain.ca-bundle
```

Then copy the text output with no newlines as the `ca_bundle_hex` variable data in /ispapp-go-alarm.go.

# license

The project ispapp-go-alarm is licensed per the MIT License
