# Scaled Animated Scaffold

A Scaffold-like Widget that animates and reveals a menu.

![Image](https://raw.githubusercontent.com/tapizquent/scaled_animated_scaffold/assets/package_showcase.gif)

## Usage

Make sure to check out [example project](https://github.com/tapizquent/scaled_animated_scaffold/blob/master/example). 

### Installation

Add to pubspec.yaml:

```yaml
dependencies:
  scaled_animated_scaffold: ^0.0.1
```

Then import it to your project:

```dart
import 'package:scaled_animated_scaffold/scaled_animated_scaffold.dart';
```

And finally create the `ScaledAnimatedScaffold` with the `ScaledAnimatedScaffoldMenuConfiguration`:

```dart
@override
Widget build(BuildContext context) {
  return ScaledAnimatedScaffold(
    menuConfiguration: ScaledAnimatedScaffoldMenuConfiguration(
      header: ScaledAnimatedScaffoldMenuButton(
        icon: Icon(
          Icons.account_circle,
        ),
        label: Text('John Wilkins'),
        onPressed: () {},
      ),
      content: Column(
        children: [
          ScaledAnimatedScaffoldMenuButton(
            icon: Icon(Icons.star),
            label: Text('Favorites'),
            onPressed: () {},
          ),
        ],
      ),
      footer: ScaledAnimatedScaffoldMenuButton(
        icon: Icon(
          Icons.settings,
        ),
        label: Text('Settings'),
        onPressed: () {},
      ),
    ),
    body: Center(
      child: Text('Hello World),
    ),
  );
}
```

Using the `ScaledAnimatedScaffoldMenuButton` is not at all required but it nicely aligns the button content to the left, whereas other buttons such as `FlatButton` center the content, but you are free to use any widget you desire


`ScaledAnimatedScaffold` contains many other properties that can be customized such as:
- whether to show the shadow under the Scaffold when the menu is visible with `showShadow`
- the color of the shadow with `shadowColor`
- the opening and closing animation duration with `animationDuration`
- the border radius of the Scaffold when menu is visible with `boderRadius`
- and much more!

### AppBar

Since the opening and closing on the menu is handled internally, a regular material `AppBar` will not work for the `ScaledAnimatedScaffold`. Instead, you can use the adjusted `ScaledAnimatedScaffoldAppBar` which behaves very similarly to the regular `AppBar` but with minor restrictions such as, the leading widget can't be assigned but you can easily change the menu icon by specifying the `leadingIcon` property. Most other properties are kept intact and can be used the same way as the regular AppBar
