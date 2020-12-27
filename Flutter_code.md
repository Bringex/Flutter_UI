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





