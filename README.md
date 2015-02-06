# Intents-SuperPowers

Grant Super Powers to any button in your app!


## Launch a Website

Launch a website in the phone browser:

```java
//place your website inside the quotes : D 
String anyWebsite = "https://www.youtube.com/watch?v=dQw4w9WgXcQ";

Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(anyWebsite));
startActivity(intent);
```


## Send a Text Message

```java
String phoneNumber = "6505551234"; //Modify this, areacode & number, no spaces
String smsMessage = "Hello from my app : )";

Uri myUri = Uri.parse("smsto:" + phoneNumber); 
Intent intent = new Intent(Intent.ACTION_SENDTO, myUri); 
intent.putExtra("sms_body", smsMessage); 
startActivity(intent); 
```

## Phone a friend

in the android manifest:

```html
<uses-permission android:name="android.permission.CALL_PHONE" />
```

In the button action space (and modify number)
```java
String phoneNumber = "6505551234"; 
Intent intent = new Intent(Intent.ACTION_CALL, Uri.parse("tel:" + phoneNumber));//area code and number, no spaces
startActivity(intent);
```



## Send Email from your Mobile App

```java
String emailAddress = "friend.of.yours@email.com";
String subject = "App Send An Email"
String message = "Sup. My app just send you an email whenever I press this button..."

Intent intent = new Intent(Intent.ACTION_SEND);

intent.setType("plain/text");
intent.putExtra(Intent.EXTRA_SUBJECT, subject);
intent.putExtra(Intent.EXTRA_EMAIL, new String[] { emailAddress });
intent.putExtra(Intent.EXTRA_TEXT, message);

startActivity(Intent.createChooser(intent, ""));
```



## Zero in on a location (with the Google Maps App)
 
Show any Latitude or Longitude in GoogleMaps App replace "37..." and "-122..." with your values,

```java
//SF Mission Bay Library
String LATITUDE="37.775268";
STRING LONGITUDE="-122.393179";
Intent intent = new Intent(Intent.ACTION_VIEW, intent.setData(Uri.parse("geo:" + LATITUDE + "," + LONGITUDE) );
startActivity(intent);
```


