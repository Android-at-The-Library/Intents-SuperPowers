# Intents-SuperPowers

Grant Super Powers to any button in your app!


## Launch a Website

Launch a website in the phone browser:

```java
//place your website inside the quotes : D 
String anyWebsite = "https://www.youtube.com/watch?v=QH2-TGUlwu4";

Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(anyWebsite));
startActivity(intent);
```


## Prep an SMS Message

1st place the following in the android_manifest.xml file (in the blank line beneath the "manifest" tag)
```
 <uses-permission android:name="android.permission.SEND_SMS" />
```

Then use the following intent as usual:

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

## Open another page (activity) 
 
**You can use any name in place of "NextPageName" (must be letters only, i.e. no spaces)** and please do.
 
#### Steps

0. Replace "ThisActivity" with your current activity's name (if you're just starting this will likely be `MainActivity`)
1. right click on the "java" folder, and select New -> Activity -> Blank Activity, and give the activity some name (we used "NextPageName" as a placeholder, you can use whatever you want)
2. Replace "NextPageName" in the code snippet below with the name you chose for the next activity.

```java
Intent intent = new Intent(ThisActivity.this, NextPageName.class );
startActivity(intent);
```

