# Flutter_UI
My experience in one repo


# Container radius corner
![cccc](RC.JPG)
```Radius with color border and backGround
Container(
      decoration: BoxDecoration(
          color: model.cardColor,
          border: Border.all(
            color: model.cardStroke,
          ),
          borderRadius: BorderRadius.all(Radius.circular(10))),
    )
```


# FlatButton radius corner

```
FlatButton(
      shape: RoundedRectangleBorder(
          borderRadius: BorderRadius.circular(18.0),
          side: BorderSide(color: Colors.blueGrey)
      ),
      onPressed: (){},
  )
```

# TextField with controller

```
var controllerSearch = TextEditingController();
var nameOfWorkSpace = "";
void updateSearch(){
    nameOfWorkSpace = controllerSearch.text;
}

@override
  void initState() {
    controllerSearch.addListener(updateSearch);
    super.initState();
}

Container(
      decoration: BoxDecoration(
        borderRadius: BorderRadius.all(Radius.circular(10.0)),
        color: Colors.White,
        border: Border.all(color: model.textFieldStroke)
      ),
      child: Padding(
        padding: const EdgeInsets.only(left: 10),
        child: TextField(
          showCursor: true,
          controller: controllerSearch,
          style: TextStyle(color:  Colors.white),
          cursorColor: Colors.white,
          decoration: InputDecoration(
              border: InputBorder.none,
              hintText: "Text hint",
              hintStyle: TextStyle(color: model.cardText)
          ),
        ),
      ),
    )
```


# RxDart simple Example

```
// Rx File
import 'package:rxdart/rxdart.dart';

class RxListUpdate {
  int _noteClass;

  int get noteClass => _noteClass;

  RxListUpdate(this._noteClass){
    this.onListUpdater = BehaviorSubject<int>.seeded(noteClass);
  }
  BehaviorSubject<int> onListUpdater;

  Future onListUpdate(int newList) async {
    _noteClass = model.sortMap(newList);
    onListUpdater.add(_noteClass);
  }
}

// Main File

RxListUpdate listUpdate = RxListUpdate(map);

StreamBuilder<int>(
          stream: listUpdate.onListUpdater,
          builder: (buildContext, snapshot) {
            int list = snapshot.data;
            return ListView(
              children: ,
            );
          })
 ```
