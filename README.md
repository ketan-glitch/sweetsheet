# sweetsheet
Show beautiful bottom sheet as confirmation dialog quickly and easily.

## Getting Started

With increasingly large smartphones, it has become almost impossible to have good ergonomics in an application using confirmation dialogs. 
The SweetSheet package allows you to show beautiful bottoms sheets to replace your confirmation dialogs and maintain a good user experience.

## How to use?

Add this to your package's pubspec.yaml file:

```
dependencies:
  sweetsheet: 0.1.0
```

And import it:
```dart
import 'package:sweetsheet/sweetsheet.dart';
```

to start using the sheets, you have to create the instance of the 
`SweetSheet` class first.

```dart
final SweetSheet _sweetSheet = SweetSheet();
```

Now you can show the bottom sheet by calling the method `show()` on the instance.
This is the signature of the `show` method

```dart
show({
    @required BuildContext context,
    @required String title,
    @required String description,
    @required SweetSheetType type,
    @required SweetSheetAction positive,
    SweetSheetAction negative,
    IconData icon,
  }){}
```

This is the signature of the `SweetSheetAction` widget.

```dart
SweetSheetAction({
    @required this.title,
    @required this.onPressed,
    this.icon
});
```

> Attention : At least one action is required.


## Example:
```dart
_sweetSheet.show(
    context: context,
    title: "Connect your watch",
    description:
        'To import your health data, you have to connect your smartwatch fist.',
    type: SweetSheetType.NICE,
    icon: Icons.watch,
    positive: SweetSheetAction(
      onPressed: () {
        Navigator.of(context).pop();
      },
      title: 'CANCEL',
    ),
    negative: SweetSheetAction(
      onPressed: () {
        Navigator.of(context).pop();
      },
      title: 'CONNECT',
      icon: Icon(Icons.open_in_new),
    ),
);
 
```

### That is all. Have fun!