# portfolio-app


its an android app which i have made by using android studio (java and xml ) which includes the some libraries that converts any website into app 


changes to be made in the code as follows  


//while choosing an project choose empty views activity and langauge in java 
// name the project api should be latest one i have used api 34 
//android gradle plugin version : 8.1.1
//gradle version : 8.0 


#  activity_main.xml



<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
<WebView
        android:id="@+id/myweb"
        android:layout_width="409dp"
        android:layout_height="729dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>


# MainActivity.java

package com.example.myweb;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.webkit.WebView;
import android.webkit.WebViewClient;

public class MainActivity extends AppCompatActivity {

WebView myweb;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        myweb =findViewById(R.id.myweb);
        myweb.getSettings().setJavaScriptEnabled(true);
        myweb.setWebViewClient(new WebViewClient());
        myweb.loadUrl("https://syedadil8496.github.io/Portofolio/");
        //the above line is used to load the website which u need as an app 
        
    }
}


#AndroidManifest.xml

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">
    
<uses-permission android:name="android.permission.INTERNET"/>
//above line should be added 
    <application
        android:usesCleartextTraffic="true"
      //the above line is to be added 
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.MyWeb"
        tools:targetApi="31">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

   <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>

