
# flutter-app-template

A boilerplate Flutter project with:

- 🧭 GoRouter for navigation  
- 🧠 Riverpod for state management (with MVVM pattern)  
- 🗂️ Clean folder structure  
- 🌗 Light/Dark theme support  
- 📦 FVM support for consistent Flutter version across teams  
- 🧑‍💻 Shared VS Code settings for all developers  
- 🧭 Gap package for spaces  
- ✨ Custom extensions for theme, colorScheme, padding, and screen dimensions

---

## 📁 Project Structure

```
lib/
├── core/
│   ├── router/        # App-wide navigation (GoRouter)
│   └── theme/         # Light & dark theme configuration
├── features/
│   └── counter/
│       ├── presentation/ # UI layer
│       └── providers/    # Riverpod state providers
├── providers/             # Global app-level providers
├── presentation/          # Shared widgets across features
└── main.dart
```

---

## 🚀 Getting Started

### 1. Use this Template

- Click **"Use this template"** on GitHub  
- Clone the newly created repo:

```bash
git clone <your-repo-url>
cd <your-project-folder>
```

---

## ⚙️ Setup Instructions

### 2. Install Dependencies

#### 🟡 Important Notes About FVM and Flutter Version

The `.fvm/fvm_config.json` in this template sets the version to `"stable"`.  
However, **"stable" is a moving target**. It may change depending on when you clone the project.  
To lock it to a fixed version like `"3.19.6"` (example), update the `fvm_config.json` like this:

```json
{
  "flutterSdkVersion": "3.19.6"
}
```

### ✅ Update FVM Configuration
You can set the version using:

```bash
fvm use 3.19.6
fvm install
```

Then everyone on the team will have the **exact same Flutter version**.

---

### 3. Team Member Setup

After cloning the project:

1. **Install FVM (if not already installed):**
```bash
dart pub global activate fvm
```

2. **Install the correct Flutter version for this project:**
```bash
fvm use 3.19.6  # Or whatever is specified in .fvm/fvm_config.json
fvm install
```

3. **Use FVM commands to run Flutter:**
```bash
fvm flutter pub get
fvm flutter run
```

> ⚠️ Avoid using `flutter run` directly unless your system Flutter version matches the FVM version.

---

## 📌 Why FVM?

**FVM (Flutter Version Management)** ensures everyone on the team uses the **same Flutter version**, avoiding version mismatch issues and environment bugs.

More help: [https://fvm.app/docs/getting_started/installation](https://fvm.app/docs/getting_started/installation)

---

## 🛠️ VS Code Setup (Recommended)

This project includes a `.vscode/settings.json` file to ensure:

- Everyone uses the same SDK path (via FVM)
- Auto formatting on save
- Code fixes automatically applied

```json
{
  "dart.flutterSdkPath": ".fvm/flutter_sdk",
  "editor.formatOnSave": true,
  "files.eol": "\n",
  "editor.codeActionsOnSave": {
    "source.fixAll": "always"
  }
}
```

---

## 📌 Project Extensions

### ✅ Theme & ColorScheme Access

```dart
extension ThemeContext on BuildContext {
  TextTheme get textTheme => Theme.of(this).textTheme;
  ColorScheme get colorScheme => Theme.of(this).colorScheme;
  ThemeData get theme => Theme.of(this);
}
```

### ✅ Padding Extensions

```dart
extension PaddingContext on BuildContext {
  EdgeInsets get paddingS => const EdgeInsets.all(8);
  EdgeInsets get paddingM => const EdgeInsets.all(16);
  EdgeInsets get paddingHorizontal => const EdgeInsets.symmetric(horizontal: 16);
}
```

### ✅ Usage Example in Widgets

```dart
Padding(
  padding: context.paddingHorizontal,
  child: Text('Hello'),
);
```

---

## 🎨 ColorScheme + AppColors Usage

This template uses `ColorScheme` for theme-aware UI.

```dart
class AppColors {
  static const Color primary = Color(0xFF1976D2); // Blue
  static const Color onPrimary = Colors.white;
  static const Color secondary = Color(0xFFFFA000); // Amber
  static const Color error = Color(0xFFD32F2F); // Red
  static const Color background = Colors.white;
  static const Color onBackground = Colors.black;
}
```

Then mapped in `ThemeData.colorScheme`:

```dart
ThemeData(
  colorScheme: ColorScheme.light(
    primary: AppColors.primary,
    onPrimary: AppColors.onPrimary,
    background: AppColors.background,
    onBackground: AppColors.onBackground,
    secondary: AppColors.secondary,
    error: AppColors.error,
  ),
)
```

---

## ✅ You're All Set!

You now have:

- ✅ A professional project structure
- ✅ Consistent dev environment using FVM
- ✅ Shared VS Code settings
- ✅ Git workflow to avoid conflicts
- ✅ AppColors, ColorScheme, and Padding extensions for scalability

Start building scalable, error-free apps as a team! 🚀
