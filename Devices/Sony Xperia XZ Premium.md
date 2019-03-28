>Change Default Resolution
* Change to 4K
<br>use android adb shell:
```
# Enter adb shell
adb shell
# Change Resolution
wm size 2160x3840
# Change PPI to what you want
wm density 807
```
* Reset to 1080
<br>adb shell command
```
# Enter adb shell
adb shell
# Change Resolution to default
wm size reset
# Change PPI to default
wm density reset

```

>Remove Wifi cross in china
```
adb shell settings put global captive_portal_https_url https://www.google.cn/generate_204
```