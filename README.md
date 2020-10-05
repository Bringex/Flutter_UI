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
