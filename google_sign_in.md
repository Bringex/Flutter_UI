## Google sign in
1 Get new app in https://console.cloud.google.com/  
2 Generate Dubug key:
```
keytool -genkey -v -keystore c:\Users\Mi\NAME.jks -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 -alias NAME
```
after password get SHA-1 and  
3 Create credential  
4 Import this key into project:

```
//app/build.gradle
signingConfigs {
        debug {
            storeFile file('path.jks')
            storePassword 'pass'
            keyAlias 'name'
            keyPassword 'pass'
        }
    }
```

```
// Global
GoogleSignIn googleSignIn;
  GoogleSignIn _googleSignIn = GoogleSignIn(
    scopes: [
      'email'
    ],
  );
```

```
void handleSignIn() async {

    try{

      GoogleSignInAccount user = await _googleSignIn.signIn();
      GoogleSignInAuthentication googleSignInAuthentication = await  user.authentication;
      //print(googleSignInAuthentication.accessToken);
      //print(_googleSignIn.scopes);
      //print(_googleSignIn.currentUser.displayName);
      //setTokenUser(googleSignInAuthentication.accessToken);

      //Get.snackbar("Registered", "Good...");
      //Get.toNamed('/home');

    } catch (error){
      //Get.snackbar("Some error", "Oooopsss...");
      //Get.toNamed('/Auth');
      return null;
    }



  }
```
