# Flutter_UI
My experience in one repo


# Container radius corner
  
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
