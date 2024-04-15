Q1.
Slip5.html
<html>
      <head>
            <title> Slip 5
            </title>
	  </head>
	  <body>
	  <form name="f1" method="post" action="slip5.jsp">
	  Enter The Number:<input type="text" name="tname"><br>
	 <input type="submit" name="s1" value="Show">
	 
</form>


 </body>
</html>

Slip 5.jsp

<html>
	<body>
		<font color="red" size="18">
		<%
			int n=Integer.parseInt(request.getParameter("tname"));
			int ld=n%10;
			while(n>9)
				n=n/10;
			
			int fd=n;
			int sum=fd+ld;
			out.println(sum);
			
		%>
		</font>
	</body>
</html>
Web.xml
<web-app>
 <welcome-file-list>
	<welcome-file>slip5.html</welcome-file>
 </welcome-file-list>
</web-app>

Q2.
import java.applet.*;
import java.awt.*;


public class Slip333 extends Applet implements Runnable
{
	static int x;
	
	public void init()
	{
	Thread tx=new Thread(this);
	tx.start();
	}
	
	public void run()
	{
	repaint();
	}
	public void paint(Graphics g)
	{
	g.drawRect(100,100,200,400);
	g.drawOval(120,120,100,100);//red
	g.drawOval(120,240,100,100);//yellow
	g.drawOval(120,360,100,100);//green
		if(x==0)
		{
			g.setColor(Color.red);
			g.fillOval(120,120,100,100);
			x=1;
		}
		
		else if(x==1)
		{
			g.setColor(Color.yellow);
			g.fillOval(120,240,100,100);
			x=2;
		}
		
		else if(x==2)
		{
			g.setColor(Color.green);
			g.fillOval(120,360,100,100);
			x=0;
		}
		
		try{
		if(x==1){Thread.sleep(5000);}
		else if(x==2){Thread.sleep(1000);}
		else if(x==0){Thread.sleep(5000);}
		}
		catch(Exception e){}
		repaint();
	}
}


Q3.
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/tv"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Ness Wadia College of Commerce"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        android:textSize="20dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintHorizontal_bias="0.363"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.155" />

    <Button
        android:id="@+id/btnRed"
        android:layout_width="122dp"
        android:layout_height="65dp"
        android:text="RED"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.134"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.31" />

    <Button
        android:id="@+id/btnBlue"
        android:layout_width="122dp"
        android:layout_height="65dp"
        android:text="BLUE"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.837"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.309" />

    <Button
        android:id="@+id/btnGreen"
        android:layout_width="122dp"
        android:layout_height="65dp"
        android:text="GREEN"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.134"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.468" />

    <Button
        android:id="@+id/btnYellow"
        android:layout_width="122dp"
        android:layout_height="65dp"
        android:text="YELLOW"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.837"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.468" />

</androidx.constraintlayout.widget.ConstraintLayout>

Main activity file
package com.example.changecolordemo;

import androidx.appcompat.app.AppCompatActivity;

import android.graphics.Color;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {
    TextView tv;
    Button btnRed,btnBlue,btnGreen,btnYellow;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        tv = (TextView) findViewById(R.id.tv);
        btnRed = (Button) findViewById(R.id.btnRed);
        btnBlue = (Button) findViewById(R.id.btnBlue);
        btnGreen = (Button) findViewById(R.id.btnGreen);
        btnYellow = (Button) findViewById(R.id.btnYellow);

        btnRed.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                tv.setTextSize(30F);
                tv.setTextColor(Color.parseColor("#FF0000"));
            }
        });

        btnBlue.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                tv.setTextSize(20F);
                tv.setTextColor(Color.parseColor("#0000FF"));
            }
        });

        btnGreen.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                tv.setTextSize(30F);
                tv.setTextColor(Color.parseColor("#00FF00"));
            }
        });

        btnYellow.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                tv.setTextSize(20F);
                tv.setTextColor(Color.parseColor("#FFFF00"));
            }
        });
    }
}


Q4.

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical">

    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/et_no"
        android:layout_gravity="center"
        android:hint="enter the number">

    </EditText>
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/et_ans"
        android:layout_gravity="center"
        android:hint="answer">

    </TextView>
    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/bt_cal"
        android:text="calculate factorial">

    </Button>

</LinearLayout>
.java file:
package com.example.demofactorial;

import androidx.appcompat.app.ActionBar;
import androidx.appcompat.app.AppCompatActivity;


import android.app.AlertDialog;
import android.content.DialogInterface;
import android.content.Intent;
import android.os.Bundle;
import android.view.Display;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;


public class MainActivity extends AppCompatActivity implements View.OnClickListener {
    EditText number;
    TextView answer;
    Button calculate;
    AlertDialog.Builder builder;
    int factorial= 1;



    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        initialize();
        calcFactorial();
        builder = new AlertDialog.Builder(this);
    }
    public void initialize() {
        number = (EditText) findViewById(R.id.et_no);
        answer = (TextView) findViewById(R.id.et_ans);
        calculate = (Button) findViewById(R.id.bt_cal);
        calculate.setOnClickListener(this);
    }
    public void calcFactorial() {
        if (number.getText().toString().equals("")) number.setText("0");
        int num = Integer.parseInt(number.getText().toString());
        for (int i = 1; i <= num; i++) {
            factorial = i * factorial;
        }
    }




    @Override
    public void onClick(View v){
        calcFactorial();
            //Setting message manually and performing action on button click
            builder.setMessage("Factorial of " + number.getText().toString() + " is : " + factorial)
                    .setCancelable(false)
                    .setPositiveButton("ok", new DialogInterface.OnClickListener() {
                        public void onClick(DialogInterface dialog, int id) {
                            finish();
                        }
                    })
                    .setNegativeButton("cancel", new DialogInterface.OnClickListener() {
                        public void onClick(DialogInterface dialog, int id) {
                        }
                   });
        //Creating dialog box
        AlertDialog alert = builder.create();
        //Setting the title manually
        alert.setTitle("FactorialAlertDialogExample");
        alert.show();


        answer.setText("Factorial of " + number.getText().toString() + " is : " +     factorial);


    }
}
