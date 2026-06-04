# Ex.No:4 Develop a simple application to display the avaliable sensor in android mobile devices using Sensor Manager in android studio.


## AIM:

To develop a sensor application to use the sensor manager class to identify and get the list of available sensors on a device. in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min.required Giraffe)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as Sensor and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display avaliable sensor in android mobile devices.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the avaliable sensor in android mobile devices”.
Developed by: JAYASEELAN U
Registeration Number : 212223220039
*/
```
## MainActivy.java
```
package com.example.sensors;



import androidx.appcompat.app.AppCompatActivity;

import android.content.Context;
import android.hardware.Sensor;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.view.View;
import android.widget.TextView;

import java.util.List;

public class MainActivity extends AppCompatActivity {

    private SensorManager mgr;
    private TextView txtList;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initialize Sensor Manager
        mgr = (SensorManager) getSystemService(Context.SENSOR_SERVICE);

        // Connect TextView with XML
        txtList = findViewById(R.id.sensorlist);

        // Get all available sensors
        List<Sensor> sensorList = mgr.getSensorList(Sensor.TYPE_ALL);

        // Store sensor names
        StringBuilder strBuilder = new StringBuilder();

        for (Sensor s : sensorList) {
            strBuilder.append(s.getName()).append("\n");
        }

        // Display sensor list
        txtList.setVisibility(View.VISIBLE);
        txtList.setText(strBuilder.toString());
    }
}
```
## activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/sensorlist"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        android:textSize="16sp"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

</androidx.constraintlayout.widget.ConstraintLayout>
```
## OUTPUT
<img width="1824" height="997" alt="Screenshot 2026-05-27 080945" src="https://github.com/user-attachments/assets/1231fbff-decd-461b-8af3-65680ff6ce01" />




## RESULT
Thus a Simple Android Application to display the avaliable sensor in android mobile devices using Sensor Manager in Android Studio is developed and executed successfully.
