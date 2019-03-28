#Android Wear开发-----为watchface添加设置界面
>为Android智能手表添加设置界面的方法

## 1. Android Wear WatchFace
Android Wear允许开发者开发自定义的watchface，而WatchFace一般都需要一个设置菜单来对其进行个性化设置。在Android7.0以后，用户可以直接在手表上进行设置操作。

## 2. 设置界面分类
手表的设置界面分为两类，一类是直接在手表上进行操作，另一类是在手机上进行操作。前者有更好的用户体验，可以不借助手机进行设置，缺点是需要API 24以上支持，后者的兼容性更高，但是需要借助手机进行设置。

 - 配置wear端
 打开wear端的配置文件，向watchFace的service添加如下配置中的高亮代码
 >wear端的Manifest文件

```
<service
            android:name=".MyWatchFace"
            android:label="@string/my_analog_name"
            android:permission="android.permission.BIND_WALLPAPER">
            <meta-data
                android:name="android.service.wallpaper"
                android:resource="@xml/watch_face"/>
            <meta-data
                android:name="com.google.android.wearable.watchface.preview"
                android:resource="@drawable/preview_analog"/>
            <meta-data
                android:name="com.google.android.wearable.watchface.preview_circular"
                android:resource="@drawable/preview_analog"/>

            <!--此处开始-->
            <!--配置mobile端-->
            <meta-data
               android:name="com.google.android.wearable.watchface.companionConfigurationAction"	         
                android:value="com.infinitytech.faraday.watchface.CONFIG_DIGITAL"/>
            <!--配置wear端-->
            <meta-data
                android:name="com.google.android.wearable.watchface.wearableConfigurationAction"
                android:value="com.infinitytech.faraday.watchface.CONFIG_DIGITAL"/>
            <!--此处结束-->

            <intent-filter>
                <action android:name="android.service.wallpaper.WallpaperService"/>
                <category
                android:name="com.google.android.wearable.watchface.category.WATCH_FACE"/>
            </intent-filter>
        </service>
```
在wear端新建一个Activity，然后在Manifest文件中做如下配置,注意这里使用了com.google.android.wearable.watchface.category.WEARABLE_CONFIGURATION这个属性，与上文中相同
```
<activity
        android:name=".SettingActivity"
        android:label="@string/title_activity_setting">
            <intent-filter>
                <action android:name="com.infinitytech.faraday.watchface.CONFIG_DIGITAL"/>
                <category android:name="com.google.android.wearable.watchface.category.WEARABLE_CONFIGURATION"/>
                <category android:name="android.intent.category.DEFAULT"/>
            </intent-filter>
</activity>
```

 - 配置mobile端
 手机端配置相对比较简单，新建一个Activity，然后在手机端的Manifest文件中做如下配置,配置文件中使用的是com.google.android.wearable.watchface.category.COMPANION_CONFIGURATION
 ```
 <activity 
        android:name=".MainActivity">
            <intent-filter>
                <action android:name="com.infinitytech.faraday.watchface.CONFIG_DIGTAL"/>
                <category android:name="com.google.android.wearable.watchface.category.COMPANION_CONFIGURATION"/>
                <category android:name="android.intent.category.DEFAULT"/>
            </intent-filter>
        </activity>
 ```

 然后你就可以在这两个Activity中添加你的设置菜单了
 <br/>
 总的来说就是，WEARABLE_CONFIGURATION代表了手表端，COMPANION_CONFIGURATION代表了手机端

