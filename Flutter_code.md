#Http requests 

Future<bool> getHttp() async {

    var res = await http.get("");

    print('Response status: ${res.statusCode}');
    print('Response body: ${res.body}');

    return true;
}


