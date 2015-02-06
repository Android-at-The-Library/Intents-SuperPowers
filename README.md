# Intents-SuperPowers
Grant Super Powers to any button in your app!

## Creating sending an email:

```java
Intent intent = new Intent(Intent.ACTION_SEND);
intent.setType("plain/text");
intent.putExtra(Intent.EXTRA_SUBJECT, "your-subject");
intent.putExtra(Intent.EXTRA_EMAIL, new String[] { "someone@email.com" });
intent.putExtra(Intent.EXTRA_TEXT, "your-message");
startActivity(Intent.createChooser(intent, ""));
```

## Send a Txt Message:

```java
Uri smsUri = Uri.parse("tel:" + to);
Intent intent = new Intent(Intent.ACTION_VIEW, smsUri);
intent.putExtra("address", to);
intent.putExtra("sms_body", message);
intent.setType("vnd.android-dir/mms-sms");
startActivity(intent);
```

## Phone a friend

in the android manifest:

```html
<uses-permission android:name="android.permission.CALL_PHONE" />
```

In the button action space (and modify number)
```java
Intent intent = new Intent(Intent.ACTION_CALL, Uri.parse("tel:5557778888"));//area code and number, no spaces
startActivity(intent);
```

## Launch Website:

Launch a website in the phone browser:

```java
Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse("http://www.google.com"));
startActivity(intent);
```
## Open a location with the Google Maps App
 
Show any Latitude or Longitude in GoogleMaps App replace "37..." and "-122..." with your values,

```java
//SF Mission Bay Library
String LATITUDE="37.775268";
STRING LONGITUDE="-122.393179";
Intent intent = new Intent(Intent.ACTION_VIEW, intent.setData(Uri.parse("geo:" + LATITUDE + "," + LONGITUDE) );
startActivity(intent);
```


