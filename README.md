# test_plugin

Test Plugin for Kotlin and Swift.

## Getting Started

This Plugin simple takes a Flutter Parameter and 'kicks' it back via iOS (Swift) or Android (Kotlin). This was simply used to test Swft and Kotlin Plugin with ObjC and Java plugins.

install in YAML: 
test_plugin: 0.0.1

package: import 'package:test_plugin/test_plugin.dart';

TestPlugin.kickBackValue(message);

### Example Setup
String _kickBack = 'nothing yet';

Future<void> getKickBack() async {
  String kickBack;
  // Platform messages may fail, so we use a try/catch PlatformException.
  String message = "dynamic text";

  try {
    kickBack = await TestPlugin.kickBackValue(message);
  } on PlatformException {
    kickBack = 'Failed to get message back from OS.';
  }

  // If the widget was removed from the tree while the asynchronous platform
  // message was in flight, we want to discard the reply rather than calling
  // setState to update our non-existent appearance.
  if (!mounted) return;

  setState(() {
    _kickBack = kickBack;
  });
}


For help getting started with Flutter, view our online
[documentation](https://flutter.io/).

For help on editing plugin code, view the [documentation](https://flutter.io/developing-packages/#edit-plugin-package).
