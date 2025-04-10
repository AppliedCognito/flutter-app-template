# flutter-app-template
A boilerplate Flutter project with:

- GoRouter for navigation
- Riverpod for state management
- Clean folder structure
- Light/Dark theme

## Structure
```
lib/
├── core/
│   ├── router/
│   └── theme/
├── features/
│   └── counter/
│       ├── presentation/
│       └── providers/
└── main.dart
```

## How to Use
1. Click "Use this template" on GitHub
2. Clone the new repo
3. Run `flutter pub get`
4. Start building your features!
# flutter-app-template

A boilerplate Flutter project with:

- 🧭 GoRouter for navigation  
- 🧠 Riverpod for state management (with MVVM pattern)  
- 🗂️ Clean folder structure  
- 🌗 Light/Dark theme support  
- 📦 FVM support for consistent Flutter version across teams  
- 🧑‍💻 Shared VS Code settings for all developers  

---

## 📁 Project Structure

lib/ ├── core/ │ ├── router/ # App-wide navigation (GoRouter) │ └── theme/ # Light & dark theme configuration ├── features/ │ └── counter/ │ ├── presentation/ # UI layer │ └── providers/ # Riverpod state providers ├── providers/ # Global app-level providers ├── presentation/ # Shared widgets across features └── main.dart

yaml
Copy
Edit

---

## 🚀 Getting Started

### 1. Use this Template

- Click **"Use this template"** on GitHub  
- Clone the newly created repo:

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
⚙️ Setup Instructions
2. Install Dependencies
If you're using FVM (recommended):
bash
Copy
Edit
fvm install
fvm use
fvm flutter pub get
If you're not using FVM:
Make sure your Flutter version matches the one in .fvm/fvm_config.json, then:

bash
Copy
Edit
flutter pub get
📌 Why FVM?
FVM (Flutter Version Management) ensures everyone on the team uses the same Flutter version, avoiding version mismatch issues and environment bugs.

To install FVM:
bash
Copy
Edit
dart pub global activate fvm
Then add it to your path:

bash
Copy
Edit
export PATH="$PATH":"$HOME/.pub-cache/bin"
For Windows users, add it via Environment Variables.
More help: https://fvm.app/docs/getting_started/installation

🛠️ VS Code Setup (Recommended)
This project includes a .vscode/settings.json file to ensure:

Everyone uses the same SDK path (via FVM)

Auto formatting on save

Code fixes automatically applied

.vscode/settings.json:
json
Copy
Edit
{
  "dart.flutterSdkPath": ".fvm/flutter_sdk",
  "editor.formatOnSave": true,
  "files.eol": "\n",
  "editor.codeActionsOnSave": {
    "source.fixAll": "always"
  }
}
✅ Note: This file is committed into Git, so everyone gets the same configuration.

👥 Team Collaboration (Git Setup Tips)
1. Git Ignore Setup
Ensure your .gitignore includes:

bash
Copy
Edit
.vscode/*
!.vscode/settings.json
.fvm/
android/.gradle/
build/
.dart_tool/
.idea/
2. Shared Git Workflow
One person is responsible for merging PRs to main.

All others must always pull latest changes before starting work:

bash
Copy
Edit
git pull origin main
3. Create Feature Branches
Each developer should work on their own branch:

bash
Copy
Edit
git checkout -b feature/your-feature-name
Then after work is done:

bash
Copy
Edit
git add .
git commit -m "Add: your feature description"
git push origin feature/your-feature-name
Open a Pull Request → Reviewer checks → Merger merges to main.
---

