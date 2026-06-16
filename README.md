# font_awesome_flutter

The Font Awesome Icon pack available as set of Flutter Icons. Based on Font Awesome 6.2.1. Provides over 1600 icons for use in your apps.

## Installation

Add to your `pubspec.yaml`:

```yaml
dependencies:
  font_awesome_flutter: ^10.0.0
```

## Usage

```dart
import 'package:font_awesome_flutter/font_awesome_flutter.dart';

class MyWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return const FaIcon(
      FontAwesomeIcons.flutter,
      color: Colors.blue,
      size: 32,
    );
  }
}
```

### Why `FaIcon` instead of Flutter's `Icon`?

Flutter's Material `Icon` widget wraps all icons in a fixed square `SizedBox`. Many Font Awesome icons are wider than they are tall, causing alignment and clipping issues. `FaIcon` does **not** wrap in a fixed square — it renders icons at their natural proportions.

## Icon styles

| Style | Prefix | Example | Free / Pro |
|---|---|---|---|
| Solid | `solid`+Name | `FontAwesomeIcons.solidFlutter` | Free |
| Regular | plain Name | `FontAwesomeIcons.flutter` | Free |
| Brands | plain Name | `FontAwesomeIcons.flutter` | Free |
| Light | `light`+Name | `FontAwesomeIcons.lightFlutter` | Pro |
| Thin | `thin`+Name | `FontAwesomeIcons.thinFlutter` | Pro |
| Duotone | — | `IconDataDuotone` | Pro |

Light, Thin, and Duotone icons require Font Awesome Pro font files to be installed.

## Development

This repo uses [FVM](https://fvm.app) with Flutter SDK 2.10.3. Prefix all commands with `fvm`:

```bash
fvm flutter pub get        # install dependencies
fvm flutter analyze         # static analysis
fvm flutter test            # run tests
```

### Regenerating icon constants

`lib/font_awesome_flutter.dart` is **auto-generated**. To regenerate:

```bash
./util/configurator.sh
```

This reads icon metadata from `lib/fonts/icons.json` and writes the constants file. Do not edit the generated file manually.
