
# flutter-app-template

A boilerplate Flutter project with:

- 🧭 GoRouter for navigation  
- 🧠 Riverpod for state management (with MVVM pattern)  
- 🗂️ Clean folder structure  
- 🌗 Light/Dark theme support  
- 🎨 Centralized ColorScheme and AppTextTheme  
- 🧑‍💻 Shared VS Code settings for all developers  
- 🧭 Gap package for spacing  
- 📐 Context Extensions for cleaner code  
- 📦 FVM support for consistent Flutter version across teams  

---

## 📁 Project Structure

```
lib/
├── core/
│   ├── extensions/        # Context-based helpers for theme, media query, etc.
│   ├── router/            # App-wide navigation (GoRouter)
│   └── theme/             # Light & dark theme configuration, AppColors, TextTheme
├── features/
│   └── counter/
│       ├── presentation/  # UI layer
│       └── providers/     # Riverpod state providers
├── providers/             # Global app-level providers
├── presentation/          # Shared widgets across features
└── main.dart              # Entry point with theme and router setup
```

---

## 🚀 Getting Started

### 1. Use this Template

- Click **"Use this template"** on GitHub  
- Clone the newly created repo:

```bash
git clone https://github.com/AppliedCognito/flutter-app-template.git
cd flutter_app_template
```

---

## ⚙️ Setup Instructions

### 2. Install Dependencies

#### If you're using **FVM** (recommended):

```bash
fvm install
fvm use
fvm flutter pub get
```

#### If you're **not using FVM**:

Make sure your Flutter version matches the one in `.fvm/fvm_config.json`, then:

```bash
flutter pub get
```

---

## 📌 Why FVM?

**FVM (Flutter Version Management)** ensures everyone on the team uses the **same Flutter version**, avoiding version mismatch issues and environment bugs.

### To install FVM:

```bash
dart pub global activate fvm
```

Then add it to your path:

```bash
export PATH="$PATH":"$HOME/.pub-cache/bin"
```

More help: [https://fvm.app/docs/getting_started/installation](https://fvm.app/docs/getting_started/installation)

---

## 🛠️ VS Code Setup (Recommended)

This project includes a `.vscode/settings.json` file to ensure:

- Everyone uses the same SDK path (via FVM)
- Auto formatting on save
- Code fixes automatically applied

---

## 🎨 Theme and Extensions

### ✅ AppColors & ColorScheme

Centralized color values defined in `AppColors` and injected into light/dark `ColorScheme`:

```dart
colorScheme: const ColorScheme.light(
  primary: AppColors.primary,
  secondary: AppColors.secondary,
  error: AppColors.error,
  background: AppColors.background,
  onPrimary: AppColors.onPrimary,
  onSecondary: AppColors.onSecondary,
)
```

Access anywhere via:

```dart
context.colorScheme.primary
```

### ✅ AppTextTheme

Custom text styles with semantic naming:

```dart
style: context.textTheme.bodyMedium?.copyWith(
  color: context.colorScheme.primary,
  fontWeight: FontWeight.w500,
)
```

### ✅ Padding Extensions

Clean and reusable padding styles:

```dart
padding: context.paddingHorizontal,
padding: context.paddingS,
padding: context.paddingTopSafe,
```

Extensions live in `core/extensions/context_extensions.dart`.

---

## 🧑‍💻 Example Usage in Screens

```dart
Padding(
  padding: context.paddingHorizontal,
  child: Column(
    children: [
      Text(
        "Hello, this is the base template",
        style: context.textTheme.bodyMedium?.copyWith(
          color: context.colorScheme.primary,
        ),
      ),
    ],
  ),
)
```

This ensures consistency across themes and responsiveness on all devices.

---

## 👥 Team Collaboration (Git Setup Tips)

### Git Ignore Setup

Ensure your `.gitignore` includes:

```
.vscode/*
!.vscode/settings.json
.fvm/
android/.gradle/
build/
.dart_tool/
.idea/
```

### Git Workflow

- Always pull the latest changes before starting work:

```bash
git pull origin main
```

- Create a feature branch for your changes:

```bash
git checkout -b feature/your-feature-name
```

- After completing your feature:

```bash
git add .
git commit -m "Add: your feature description"
git push origin feature/your-feature-name
```

Open a Pull Request → Reviewer checks → Merger merges to `main`.

---

## ✅ You're All Set!

You now have:

- A professional project structure
- Centralized theme and styling utilities
- Consistent dev environment with FVM
- Shared VS Code settings
- Git workflow for team collaboration

Start building scalable, error-free apps as a team! 🚀

---

### 💬 Need Help?

Open an issue or contact the maintainer.
