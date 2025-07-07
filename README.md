# 🧠 Competitive Programming Setup for C++ on macOS (Sublime Text + GCC)

This guide walks you through installing and configuring everything you need for fast and effective C++ competitive programming using Sublime Text on macOS.

---

## ✅ Step 1: Install Homebrew (Package Manager for macOS)

Open Terminal and run:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Check Homebrew is installed:

```bash
brew --version
```

---

## ✅ Step 2: Install GCC (for bits/stdc++.h support)

Install GCC:

```bash
brew install gcc
```

Check installed version:

```bash
ls /opt/homebrew/bin/g++*
```

This gives you something like `/opt/homebrew/bin/g++-13` or `g++-14`.

---

## ✅ Step 3: Install Sublime Text

Download Sublime Text from the official site:

🔗 [https://www.sublimetext.com/](https://www.sublimetext.com/)

Move it to the Applications folder and open it once.

---

## ✅ Step 4: Install Package Control in Sublime Text

1. Open Sublime Text
2. Go to **View → Show Console**
3. Paste the install script from: [https://packagecontrol.io/installation](https://packagecontrol.io/installation)
4. Press Enter

---

## ✅ Step 5: Install Useful Packages via Package Control

Press `Cmd + Shift + P` → **Install Package**, then search and install:

| Package Name | Purpose |
|--------------|---------|
| **Competitive Programming Snippets** | Ready-made CP code templates |
| **C++ Snippets** | STL and utility snippets |
| **SublimeCodeIntel** (optional) | Auto-suggestions & completions |
| **Ayu, Brogrammer, or Dracula** (optional) | Clean, colorful themes |

---

## ✅ Step 6: Create a Custom Build System for C++ with GCC

1. Go to **Tools → Build System → New Build System**
2. Paste the following code:

```json
{
  "cmd": ["/opt/homebrew/bin/g++-13", "$file", "-std=c++17", "-o", "${file_path}/${file_base_name}", "&&", "${file_path}/${file_base_name}"],
  "shell": true,
  "file_regex": "^(...*?):([0-9]*):?([0-9]*)",
  "selector": "source.c++"
}
```

3. 🔁 Replace `g++-13` with your installed version (e.g., `g++-14`)
4. Save the file as: **CP-GCC.sublime-build**
5. Select the build system from: **Tools → Build System → CP-GCC**

Now press `Cmd + B` to compile and run your .cpp files

---

## ✅ Step 7: Create a Competitive Programming Snippet Template

1. Go to **Tools → Developer → New Snippet**
2. Paste the following:

```xml
<snippet>
  <content><![CDATA[
#include <bits/stdc++.h>
using namespace std;

#define int long long
#define endl '\n'
#define fast ios::sync_with_stdio(false); cin.tie(0);

int32_t main() {
    fast;

    int t;
    cin >> t;
    while (t--) {
        // your code here
    }

    return 0;
}
]]></content>
  <tabTrigger>cp</tabTrigger>
  <scope>source.c++</scope>
</snippet>
```

3. Save as **cp.sublime-snippet**

In a .cpp file, type `cp + Tab` to expand the template

---

## ✅ Step 8: Set Up Custom Key Bindings (Optional for Speed)

1. Go to **Preferences → Key Bindings**
2. In the right pane (User), paste:

```json
[
  { "keys": ["super+s"], "command": "save" },
  { "keys": ["super+b"], "command": "build" },
  { "keys": ["super+q"], "command": "cancel_build" },
  { "keys": ["super+w"], "command": "toggle_side_bar" },
  { "keys": ["shift+space"], "command": "move", "args": { "by": "characters", "forward": true } }
]
```

---

## ✅ Step 9: (Optional) Install Colorful Theme for Better Coding Experience

Use `Cmd + Shift + P` → **Install Package**, and search for:

- **Ayu** (Dark / Mirage)
- **Brogrammer** (high contrast, hacker style)
- **Dracula Theme**
- **Material Theme**

Then use:
- `Cmd + Shift + P` → **UI: Select Theme**
- `Cmd + Shift + P` → **UI: Select Color Scheme**

---

## ✅ Step 10: (Optional) Create a Dummy bits/stdc++.h (For clang++ only)

If you still want to use bits/stdc++.h with clang++:

```bash
mkdir -p ~/bits
nano ~/bits/stdc++.h
```

Paste this:

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <cmath>
#include <map>
#include <set>
#include <stack>
#include <queue>
#include <bitset>
#include <unordered_map>
#include <unordered_set>
using namespace std;
```

Then in your .cpp file:

```cpp
#include "~/bits/stdc++.h"
```

⚠️ **Not recommended for contests. Use GCC for native support.**

---

## ✅ You're All Set! 🚀

### 🧪 Now You Can:
- Compile & run C++ code with `Cmd + B`
- Use snippets like `cp` for full templates
- Use `#include <bits/stdc++.h>` without issues
- Enjoy syntax highlighting, fast I/O setup, and productivity boosts

### 💡 Tips for Competitive Programmers
- Create a folder for each contest (`/CF_Round_900`, `/AtCoder_ABC123`, etc.)
- Add more snippets for common algorithms: sieve, DSU, modinv, etc.
- Use a good font: JetBrains Mono, Fira Code, Operator Mono (with ligatures)

### 🔗 Useful Resources
- [Sublime Text](https://www.sublimetext.com/)
- [GCC via Homebrew](https://formulae.brew.sh/formula/gcc)
- [Competitive Programming Snippets](https://packagecontrol.io/packages/Competitive%20Programming%20Snippets)
- [Dracula Theme](https://packagecontrol.io/packages/Dracula%20Color%20Scheme)

---
<img width="1728" alt="Screenshot 2025-07-07 at 3 31 37 PM" src="https://github.com/user-attachments/assets/3a197dd4-3c78-4edd-bcac-4c2b5e59b9c4" />

## 👋 Happy Coding & Good Luck in Contests!

