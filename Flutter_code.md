# main routs
```
import 'package:flutter/material.dart';

void main() => runApp(

    MaterialApp(
        home: MaterialApp(
          initialRoute: '/',
          routes: {
            '/': (context) => ChooseScreen(),
            //'/home': (context) => HomeScreen(),
            //'/loader_home': (context) => HomePreloader(),
          },
        )
    )
);

```




# http requests


```
import 'package:http/http.dart' as http;

Future<bool> getHttp() async {

    var res = await http.get("");

    print('Response status: ${res.statusCode}');
    print('Response body: ${res.body}');

    return true;
}
```

# Get location
```
import 'package:location/location.dart';

Location location = new Location();

  Future<LocationData> getLocation() async{
    bool _serviceEnabled;
    PermissionStatus _permissionGranted;
    LocationData _locationData;


    _serviceEnabled = await location.serviceEnabled();
    if (!_serviceEnabled) {
      _serviceEnabled = await location.requestService();
      if (!_serviceEnabled) {
        print("DON'T HAVE PERMISSION");
      }
      print("DON'T HAVE PERMISSION");
    }

    _permissionGranted = await location.hasPermission();
    if (_permissionGranted == PermissionStatus.denied) {
      _permissionGranted = await location.requestPermission();
      if (_permissionGranted != PermissionStatus.granted) {
        print("DON'T HAVE PERMISSION");
      }
      print("DON'T HAVE PERMISSION");
    }

    _locationData = await location.getLocation();


    return _locationData;
  }
```

# Shared Preferences

```
import 'package:shared_preferences/shared_preferences.dart';

//some set:
Future<void> setCheck() async {
    SharedPreferences prefs = await SharedPreferences.getInstance();
    try{ 
      prefs.setInt('counter', 1);
      return true;
    }catch(E){
      return false;  
    }
}

//some get:
Future<String> getPass() async {
    SharedPreferences prefs = await SharedPreferences.getInstance();
    try{
      String pass = prefs.getString('pass');
      return pass;
    }catch(E){
      return "null";
    }
}

```


# alert Dialog

```

Widget okButton = FlatButton(
    child: Text("Ок"),
    onPressed: () {
      Navigator.of(context, rootNavigator: true)
          .pop(); // this is close alert )
    },
  );

AlertDialog alert = AlertDialog(
    title: Text("Ошибка"),
    content: Text("Неверный логин или пароль"),
    actions: [
      okButton, //some buttons
    ],
  );
                              
showDialog(
    context: context,
    builder: (BuildContext context) {
      return alert;
    },
  );

```




