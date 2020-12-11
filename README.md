# VeryFullScreen
 
<p align="center">
  <img src="https://github.com/gzeinnumer/VeryFullScreen/blob/master/preview/SplashScreenActivity.jpg" width="400"/>
</p>

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest>

    <application>
        <activity
            android:name=".SplashScreenActivity"
            android:theme="@style/Theme.VeryFullScreen.Splash">
        </activity>
    </application>

</manifest>
```
```xml

    <!-- Base application theme. -->
    <style name="Theme.VeryFullScreen" parent="Theme.MaterialComponents.Light.NoActionBar">
    </style>

    <style name="Theme.VeryFullScreen.Splash" parent="Theme.VeryFullScreen">
        <item name="android:statusBarColor">@color/purple_500</item>
        <item name="colorPrimary">@android:color/white</item>
        <item name="colorPrimaryVariant">@android:color/white</item>
        <item name="colorOnPrimary">@android:color/white</item>
        <item name="android:fitsSystemWindows">false</item>
    </style>
```
```java
public class SplashScreenActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setFullScreen();
        setContentView(R.layout.activity_splash_screen);
    }

    private void setFullScreen() {
        int decore = View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY
                | View.SYSTEM_UI_FLAG_LAYOUT_STABLE
                | View.SYSTEM_UI_FLAG_LAYOUT_HIDE_NAVIGATION
                | View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN
                // Hide the nav bar and status bar
                | View.SYSTEM_UI_FLAG_HIDE_NAVIGATION;

        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.M) {
            //enable this tho maker icon status bar become black
            decore+= View.SYSTEM_UI_FLAG_LIGHT_STATUS_BAR;
        }

        getWindow().getDecorView().setSystemUiVisibility(decore);
    }
}
```

---

```
Copyright 2020 M. Fadli Zein
```