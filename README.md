
# Rapport
Skapade knapp som startar SecondActivity.java, och intent i MainActivity.java.
Intenten hämtas från sträng-filen.
Mainactivity:``
Button button = findViewById(R.id.start_second_activity);
button.setOnClickListener(new View.OnClickListener(){
    @Override
    public void onClick(View view) {
    Intent intent = new Intent(MainActivity.this, SecondActivity.class);
    intent.putExtra("name", "Nu är du på SecondActivity");
    startActivity(intent);
}
});
``Strings.xml:
``
<resources>
<string name="app_name">Screens</string>
<string name="mainText">Nu är du på MainActivity</string>
<string name="buttonText_main">Start Second Activity</string>
<string name="secondText">Close Second Activity</string>
</resources>
``
Intentet hämtas i SecondActivity.java (OM det har ett värde som inte är null visas strängen)
``
Bundle extras = getIntent().getExtras();
if (extras != null) {
    String name = extras.getString("name");
    textView.setText(name);
}
``
Även en knapp för att avsluta SecondActivity.java skapades
``
Button close = findViewById(R.id.close_second_activity);
close.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View view){
    finish();
    }
});
``
- MainActivity:
![](Screenshot_Mainactivity.png)
- SecondActivity
![](Screenshot_secondactivity.png)

