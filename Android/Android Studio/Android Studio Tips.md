# Android Studio Tips

## Error:
* can not find a member named "stdio"、"div_t"...
```
Answer: Did you using a custom gcc compile in you system path? like MinGW、Cygwin.
```
* Please select Android SDK
```
check the "project"->"sdk", make sure it is correct, somethimes the sdk path change it self to lowercase.
```
* set gloable git username and email failed
```
if you use Windows, check do you have permission to enter "C:\Windows\system32\Config\systemprofile", just use explore to enter this folder, and you will gain the permission untill you reflash you system.
```
* the logcat filter didn't work
```
just reselect the debuggable processes、the log level、the log filter, and it should work now.
```
* can not find lib "libxxx.so" needed by "libnative-lib.so" and no rules to make it
```
did you just add new native lib to you project? if so, you need clean project or rebuild project, to clean the pre-build cache, like the last generated apk. Android Studio use each part of the project to generate sevaral small apks, and use them to create a full apk on you device, if you didn't clean the project, Android Studio won't generate new apks, the new native lib won't be add.
```
* can not find "libxxx.so" in .../arm64-v8a、.../x86_64
```
if you didn't manage the native lib youself by the gradle script and "CMakeLists.txt" or "Android.mk" file, like map native libs, you need make sure every native lib folder must have the same libs. if you have libgzip.so in "armeabi-v7a" and you also have a "armeabi" folder, then you must put a armeabi version libgzip.so in "armeabi" folder, or you can delete the whole "armeabi" folder.
```

## Skills