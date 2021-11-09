# Frida

## Install 
- Windows
  - ```pip install frida```
  - ```pip install frida-tools```
  - Find Version: ```frida --version```

- Android
  - Download same version with Windows from ![here](https://github.com/frida/frida/releases)
    -  Nexus 5x => arm64
    -  Genymotion => x86
  - Put the file in tmp directory
    - ``` adb push frida-server-14.2.18-android-x86 /data/local/tmp```
    - ```adb shell```
  - Use these command in adb
    - ```cd /data/local/tmp```
    - ```chmod 777 frida-server-14.2.18-android-x86```
    - ```./frida-server-14.2.18-android-x86```
- Check
  - ```> python```
  - ```>>> import frida # import frida tools```
  - ```>>> frida.get_usb_device() # enum available devices```
  - ```Device(id="192.168.69.101:5555", name="Custom Phone", type='usb')```

## Usage
#### Show process list
```
frida-ps -U
```

#### Objection
- Disable 'Magisk Hide' in Nexus
```
> pip install objection
> objection --gadget “com.sepehrpay.pas” explore
com.sepehrpay.pas on (google: 8.1.0) [usb] # android root disable
```

#### Root detection bypass
- If not work, restart Frida
```
> frida --codeshare dzonerzy/fridantiroot -f com.sepehrpay.pas -U
[Nexus 5X::com.sepehrpay.pas]-> %resume
```

#### Run JS codes
```
> frida -l fridascript.js -f com.sepehrpay.pas -U
```
