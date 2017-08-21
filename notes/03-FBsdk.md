- install the SDK

using yarn

`yarn add react-native-fbsdk`

or npm

`npm i -S react-native-fbsdk`

- then use `react-native link` to link the native code to JS
  - note: linking is enough for most projects, but **react-native-fbsdk needs additional setup**

## Android

Edit the following files:
### **MainApplication.java**

add these imports to the top:

```java
import com.facebook.CallbackManager;
import com.facebook.FacebookSdk;
import com.facebook.reactnative.androidsdk.FBSDKPackage;
```

this props to the **MainApplication class**:

```java
private static CallbackManager mCallbackManager = CallbackManager.Factory.create();
protected static CallbackManager getCallbackManager() {
  return mCallbackManager;
}
```

this Override to the end of the **MainApplication class**:
```java
@Override
public void onCreate() {
  super.onCreate();
  FacebookSdk.sdkInitialize(getApplicationContext());
}
```

and this parameter to the **getPackages() method**:

```java
new FBSDKPackage(mCallbackManager)
```
### **MainActivity.java**

Add import:
```java
import android.content.Intent;
```

Add Override to **MainActiviry class**:
```java
@Override
public void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        MainApplication.getCallbackManager().onActivityResult(requestCode, resultCode, data);
    }
```

### **android/app/src/main/res/values/strings.xml**

add:
```xml
<string name="facebook_app_id">YOUR_APP_ID</string>
```
(get YOUR_APP_ID from facebook developer site and the app you created there)

### **AndroidManifest.xml**
Add before the closing `</application>` tag:
```xml
<activity android:name="com.facebook.FacebookActivity"
    android:configChanges="keyboard|keyboardHidden|screenLayout|screenSize|orientation"
    android:theme="@style/com_facebook_activity_theme"
    android:label="@string/app_name" />
<meta-data android:name="com.facebook.sdk.ApplicationId" android:value="@string/facebook_app_id"/>
```
## IOS
*To be added*
## Using it

In your component, import LoginButton:

```JavaScript
import { LoginButton } from 'react-native-fbsdk'
```

and use it in a view:

```JavaScript
<LoginButton
  onLoginFinished={() => ({})}
  onLogoutFinished={() => ({})}
  defaultAudience='everyone'
/>
```