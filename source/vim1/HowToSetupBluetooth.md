title: How To Setup Bluetooth
---

## Android

For Android you can setup Bluetooth via the GUI easily.

## Ubuntu

<ul class="nav nav-tabs" id="myTab" role="tablist">
  <li class="nav-item" role="presentation">
    <a class="nav-link active" id="desktop-tab" data-toggle="tab" href="#desktop" role="tab" aria-controls="desktop" aria-selected="true">Desktop</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="server-tab" data-toggle="tab" href="#server" role="tab" aria-controls="server" aria-selected="false">Server</a>
  </li>
</ul>
<div class="tab-content" id="myTabContent">
<div class="tab-pane fade show active" id="desktop" role="tabpanel" aria-labelledby="desktop-tab">

For desktop systems you can setup Bluetooth via the GUI easily. 

You can refer to connecting media playback devices via Bluetooth --> [How to connect Bluetooth media devices](/vim3/BluetoothInstructions.html)

</div>

<div class="tab-pane fade show" id="server" role="tabpanel" aria-labelledby="server-tab">

For Ubuntu/Debian servers we can use `bluez` & `bluetoothctl` to setup Bluetooth via command line.

* Enable Bluetooth

```
$ sudo hciconfig hci0 up
```

* Launch bluetoothctl and Setup

```
$ sudo bluetoothctl
[NEW] Controller 43:54:A2:00:1F:AC Khadas [default]
Agent registered
[bluetooth]#
```
Setup:

```
[bluetooth]# agent on
[bluetooth]# default-agent
[bluetooth]# power on
[bluetooth]# discoverable on
[bluetooth]# pairable on
[bluetooth]# scan on
```

* Scan for Bluetooth Peripherals

```
[bluetooth]# scan on
Discovery started
[CHG] Controller 43:54:A2:00:1F:AC Discovering: yes
[NEW] Device 46:04:25:5F:1E:8D 46-04-25-5F-1E-8D
[NEW] Device 8C:EB:C6:E7:2E:33 Khadas
```

* Show Devices

```
[bluetooth]# devices
Device 46:04:25:5F:1E:8D 46-04-25-5F-1E-8D
Device 8C:EB:C6:E7:2E:33 Khadas
Device 9C:FB:D5:0D:91:47 9C-FB-D5-0D-91-47
[NEW] Device AC:83:F3:DD:D4:E1 AC-83-F3-DD-D4-E1
[CHG] Device AC:83:F3:DD:D4:E1 Name: LibreELEC
[CHG] Device AC:83:F3:DD:D4:E1 Alias: LibreELEC
```
* Connect to a Device

```
[bluetooth]# connect <device_addr>
```

{% note info Tips %}

`device_addr` is the address of the device you want to connect to.

{% endnote %}

* Exit bluetoothctl

```
[bluetooth]# quit
Agent unregistered
[DEL] Controller 43:54:A2:00:1F:AC Khadas [default]
khadas@Khadas:~$
```
</div>
</div>

### Troubleshooting

If your bluetooth doesn't work anymore, you can try to restart the bluetooth service manually.

```
$ sudo systemctl restart bluetooth-power-fixup.service
```
