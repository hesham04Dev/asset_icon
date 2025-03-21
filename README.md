
# <img src="https://raw.githubusercontent.com/hesham04Dev/asset_icon/refs/heads/main/screenshots/logo.png" width="30px"/> AssetIcon

`AssetIcon` is a powerful and customizable Flutter package for rendering asset-based icons with ease. Whether you're working with PNG, SVG,and other formats, this package allows you to adjust properties such as size, color, and opacity. It also offers batch generation of Dart code for your asset keys, making it easier to manage large sets of icons.

## ✨ Features

- **📁 Multiple Format Support**: Display PNG and SVG icons seamlessly, along with support for other formats.
- **🎨 Customization**: Easily modify icon size, color, and opacity to fit your app's theme.
- **🔧 Global Configuration**: Set a default path and color for consistent icon styling throughout your app.
- **🛡️ Accessibility**: Add semantic labels for better screen reader support.
- **🚀 Automated Icon Key Generation**: Generate constant keys for all icons in your assets folder to streamline code usage.

## 📦 Installation

Add `AssetIcon` to your `pubspec.yaml`:

```yaml
dependencies:
  assets_icon: ^latest_version
```

## 🤔 How does the Icon should be?
The Icon should be one color with transparency
![description](https://raw.githubusercontent.com/hesham04Dev/asset_icon/refs/heads/main/screenshots/how_should_the_icon_be.png)



## 🚀 Getting Started
Basic Usage
```dart
import 'package:assets_icon/assets_icon.dart';

AssetIcon(
  'example_icon.png',  // Icon name (stored in assets/icons/)
  semanticLabel: 'Example icon',    // Semantic label for accessibility
)
```
With Label
```dart
import 'package:assets_icon/assets_icon.dart';

AssetIcon.withLabel(
  'example_icon.png',  
  label: 'Example icon',
  position: AssetIconLabelPosition.top
)
```
With Customization
```dart
AssetIcon(
  'example_icon.svg',     // Icon name (must be in the asset folder)
  size: 30.0,                       // Custom size
  color: Colors.blue,               // Custom color
  opacity: 0.7,                     // Custom opacity
  semanticLabel: 'Example icon',    // Semantic label for accessibility
)
```

## 🔄 Comparison with `ImageIcon`

| Feature                         | AssetIcon              | ImageIcon                |
|---------------------------------|------------------------|--------------------------|
| **Support Svg**                 | Yes                    | No                       |
| **Opacity**                     | Yes                    | No                       |
| **Color Customization**         | Yes                    | Yes                      |
| **Constant Key Generation**     | Yes                    | No                       |
| **Online Icon Support**         | No                     | Yes                      |


**Summary**: `AssetIcon` offers more flexibility with SVG support, opacity adjustments, and constant key generation, making it ideal for managing large icon libraries. `ImageIcon` may be sufficient for simple use cases with only PNGs.


## ⚙️ Configuration
To set default values for the color and asset path globally, use the `settings` method:
```dart
AssetIcon.settings(
  defaultColor: Colors.grey,
  defaultPath: 'assets/icons/',
);
```
This will apply the specified defaults to any AssetIcon widget that does not provide these properties individually.

## 💻 Code Generation for `asset_icon`

`asset_icon:generate` provides a streamlined way to generate a Dart class containing keys for your asset files. This command is specifically tailored for handling icon assets such as PNG and SVG files and outputs a Dart file with constant strings for each asset, enabling you to reference icons in your Flutter code effortlessly.

### Command Line Arguments

| Argument                     | Short | Default             | Description                                                                            |
|------------------------------|-------|---------------------|----------------------------------------------------------------------------------------|
| `--help`                     | `-h`  |                     | Display help information.                                                              |
| `--source-dir`               | `-S`  | `assets/icons/`     | The folder containing icon files.                                                      |
| `--class-name`               | `-c`  | `AssetIcons`        | The name of the Dart class to be generated.                                            |
| `--output-dir`               | `-O`  | `lib/generated`     | The output folder where the generated file will be saved.                              |
| `--output-file`              | `-o`  | `icons.g.dart`      | The name of the output Dart file.                                                      |

### Usage

To run the code generator, use the following command in your terminal:

```bash
dart run asset_icon:generate --source-dir assets/icons/ --class-name MyAssetIcons --output-dir lib/generated --output-file my_icons.g.dart
```

Then you can write like this:
```dart
import 'path_to_lib_folder/generated/icons.g.dart';
...
AssetIcon(
  AssetIcons.example,
  semanticLabel: 'Example icon',
)
```

## 📁 Example Folder Structure
Ensure your icons are placed in the specified assets directory. For example:
```md
assets/
└── icons/
    ├── example_icon.png
    ├── example_icon.svg
    └── other_icon.png
```
Then, register the asset path in pubspec.yaml:
```yaml
flutter:
  assets:
    - assets/icons/
```

## 🤝 Contribute
Feel free to contribute to AssetIcon by submitting issues or pull requests. We welcome contributions that enhance functionality or improve performance.

## 📜 License
`AssetIcon` is licensed under the MIT License.

<!-- TODO add the shape of icons and it should be one color and can be with opacity give example with images and how the shape become  -->
