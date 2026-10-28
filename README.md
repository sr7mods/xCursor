<div align="center">

# ⚡ xCursor

**Ultra-Precision Floating Virtual Mouse & Laptop Touchpad Engine for Android**

<!-- GitHub Shields / Badges Card -->
<p>
  <a href="https://www.java.com/"><img src="https://img.shields.io/badge/Language-Pure%20Java%2011-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Language Java"></a>
  <a href="https://developer.android.com/about/versions/15"><img src="https://img.shields.io/badge/Target-Android%2015%20(API%2035)-3DDC84?style=for-the-badge&logo=android&logoColor=black" alt="Target Android 15"></a>
  <a href="https://developer.android.com/"><img src="https://img.shields.io/badge/Min%20SDK-API%2024%20(Nougat)-00BCD4?style=for-the-badge&logo=android&logoColor=white" alt="Min SDK 24"></a>
  <a href="https://developer.android.com/guide/topics/ui"><img src="https://img.shields.io/badge/UI-Glassmorphism%20%7C%20Vector%20Drawables-7F52FF?style=for-the-badge&logo=material-design&logoColor=white" alt="UI Style"></a>
  <a href="https://developer.android.com/guide/topics/ui/accessibility"><img src="https://img.shields.io/badge/Engine-Accessibility%20%2B%20Overlay-FF5722?style=for-the-badge&logo=google&logoColor=white" alt="Accessibility Engine"></a>
  <a href="https://developer.android.com/tools/aapt2"><img src="https://img.shields.io/badge/Vector%20Spec-AAPT2%20Binary%20(24dp)-00B0FF?style=for-the-badge&logo=target&logoColor=white" alt="AAPT Binary Spec"></a>
  <a href="https://sr7mods.github.io/xCursor/"><img src="https://img.shields.io/badge/Store-xCursor%20Store-9C27B0?style=for-the-badge&logo=googlechrome&logoColor=white" alt="xCursor Store"></a>
  <a href="https://sr7mods.github.io/about-dev/"><img src="https://img.shields.io/badge/Dev-SR7%20Mods-00E676?style=for-the-badge&logo=github&logoColor=black" alt="Developer SR7 Mods"></a>
</p>

<p align="center">
  <i>Transform any Android phone, foldable, or tablet into a high-precision workstation with an intelligent floating trackpad, hardware OTG/Bluetooth mouse cursor integration, real-time hover transformations, and AAPT-compiled vector cursor packs.</i>
</p>

</div>

---

## 🌟 Key Features

* **🖱️ Dual-Mode Precision Pointer Engine**:
  * **Floating Laptop Touchpad Mode**: A fully interactive, glassy on-screen trackpad floating over all applications. Emulates modern laptop gesture behavior: tap to click, smooth trackpad tracking, and double-tap gestures.
  * **Hardware Mouse Mode**: Direct plug-and-play support for physical USB-OTG or Bluetooth mice, delivering latency-free desktop-grade cursor navigation without root.
  * **Smart Auto-Hide & Idle Suppression**: The pointer stays invisible until mouse or touchpad activity starts, automatically fading out during inactivity to avoid screen distraction.

* **📜 Dual-Layer Bidirectional Scroll Engine**:
  * **Touchpad Quick Mode Bar**: One-touch icon controls located directly at the top of the floating trackpad to switch instantly between **Normal Mode** (point & click) and **Scroll Mode**.
  * **Micro-Delta Gesture Accumulator**: When in Scroll Mode, finger gestures on the touchpad translate into fluid directional scrolling from the cursor's exact coordinates.
  * **Dual-Layer Fallback Architecture**: Combines native `AccessibilityNodeInfo` action scrolling with high-performance `dispatchGesture` stroke synthesis for maximum compatibility across third-party apps, browsers, and social feeds.

* **🎨 Tri-State Adaptive Hover Transformations**:
  * **Default Arrow**: Clean, razor-sharp cursor for general home screen and system navigation.
  * **I-Beam State**: Automatically shifts into an ergonomic text insertion pointer when hovering over input fields, search bars, and editable text boxes.
  * **Link Hand State**: Dynamically morphs into a pointer hand when hovering over clickable URLs, buttons, tabs, or interactive UI elements.
  * **Built-in Curated Packs**: Includes **Neo Glass** (cyan & neon violet aura), **Classic Monochrome** (high-contrast black/white), and **Cyber Amber** (sci-fi gold precision).

* **📐 Strict AAPT-Compiled Vector Importer (24dp Viewport)**:
  * **Binary XML Vector Engine**: Direct native parsing of compiled binary XML drawables to maintain silky 60/120 FPS rendering across all screen densities.
  * **Strict 24x24dp Viewport Validation**: Validates `android:viewportWidth="24"` and `android:viewportHeight="24"` with 4-byte AAPT header magic checking (`0x00080003`), rejecting uncompiled plain text XML files before they can trigger system render exceptions.
  * **Multiple Custom Cursor Styles**: Manage, preview, and switch between multiple custom cursor sets directly inside the app.

* **🛡️ Zero-Zombie Service Architecture & Glassy Ergonomics**:
  * **High-Stability Service Lifecycle**: Closing the floating trackpad automatically toggles off the overlay without terminating the underlying AccessibilityService. Re-enabling the switch instantly restores overlays—no tedious trips to Android System Settings required.
  * **Movable & Minimizable**: Features a dedicated drag handle icon on the trackpad header for smooth repositioning, an instant minimize button that collapses the trackpad into an unobtrusive floating bubble, and a 2-finger 3-second hold gesture fallback.
  * **Full Glassmorphic Customizer**: Real-time slider controls for trackpad width, cursor size, opacity, pointer speed/sensitivity, and tint options (Obsidian Dark, Electric Cyan, Neon Violet, Frosted Glass).

* **🧪 In-App Live Interactive Test Pad**:
  * **Integrated Testing Lab**: Instant real-time testing playground with text inputs, action buttons, link targets, and neutral zones.
  * **Live Coordinate & State Telemetry**: Real-time telemetry badges displaying instant cursor X/Y coordinates and active cursor state (`DEFAULT`, `TEXT`, `POINTER`).

---

## 🛠️ Architecture & Technical Specifications

| Component / Layer | Technology / Implementation | Purpose & Specifications |
| :--- | :--- | :--- |
| **Operating System Support** | Android API 24 (Nougat) to API 35 (Android 15) | Full modern platform compliance, predictive back, edge-to-edge support |
| **Runtime Dependencies** | **100% Pure Java & Android Framework** | **Strictly Zero AndroidX runtime libraries** to ensure unmatched lightweight performance |
| **Overlay Engine** | `WindowManager.LayoutParams.TYPE_ACCESSIBILITY_OVERLAY` | Renders above all full-screen applications, games, and system dialogs |
| **Hover & Gesture Engine** | `AccessibilityService` (`dispatchGesture`) | Tracks focus node boundaries (`AccessibilityNodeInfo`) and injects touch/scroll events |
| **Vector Importer Validator**| `CursorFileHelper` AAPT Header Parser | Validates 4-byte magic `0x00080003` and enforces `viewportWidth/Height == 24` |
| **UI Design System** | Custom Glassmorphic XML Drawables | Translucent glass gradient backgrounds, subtle border strokes, and blur accents |
| **State Persistence** | `SharedPreferences` + Local App Sandboxed Storage | Stores active themes, custom cursor files, sensitivity, size, and layout settings |

---

## 📦 Custom Cursor Importer & AAPT Specification

xCursor is built with an enterprise-grade vector rendering pipeline. To guarantee zero frame drops and prevent runtime crashes, custom cursor XML imports **must be compiled binary XML drawables** produced by Android's asset packaging tool (`aapt2`).

### Why Compiled XML?
Plain-text XML files (created in text editors or downloaded from the web) contain raw ASCII characters that Android's low-level resource parser cannot load dynamically outside of a compiled APK. `aapt2` compiles vector XML into Android's optimized binary chunk format.

### Vector Specifications:
* **Binary Magic Header**: `0x00080003` (validated on file inspection).
* **Viewport Dimensions**: Exactly `24dp` x `24dp` (`android:viewportWidth="24"` and `android:viewportHeight="24"`).
* **Tri-State Structure**: Each custom cursor style supports three discrete states:
  1. **Default Pointer**: Primary arrow pointer.
  2. **Text / I-Beam**: Input and text field pointer.
  3. **Link / Hand**: Interactive button and URL hand pointer.

### How to Compile Custom Vector Drawables:
```bash
# 1. Compile your 24x24 vector XML with AAPT2
aapt2 compile --dir ./my_vectors -o ./compiled/

# 2. Extract or rename the resulting .flat file (or pull compiled XML from an APK)
# 3. Import the compiled binary XML file directly into xCursor via the Customizer
```

> 💡 **Tip:** You can also browse pre-compiled, ready-to-use cursor packs on the [xCursor Store](https://sr7mods.github.io/xCursor/).

---

## 📂 Repository Structure

```
xCursor/
├── .env.example
├── .gitignore
├── metadata.json                                # Platform project metadata & identity
├── build.gradle.kts                             # Root Gradle build script
├── settings.gradle.kts                          # Project name and repository config
├── gradle/
│   └── libs.versions.toml                       # Centralized Gradle version catalog
├── app/
│   ├── build.gradle.kts                         # App module configuration (SDK 35, Java 11)
│   ├── proguard-rules.pro                       # Production optimization rules
│   └── src/
│       ├── main/
│       │   ├── AndroidManifest.xml              # Permissions & AccessibilityService declaration
│       │   ├── java/com/example/
│       │   │   ├── MainActivity.java            # Home, Test Lab, Settings bottom navigation
│       │   │   ├── AddCursorActivity.java       # Custom cursor creator & AAPT file picker
│       │   │   ├── SettingsActivity.java        # Dedicated settings & theme configuration
│       │   │   ├── CursorAccessibilityService.java # Floating overlay, touchpad, & gesture engine
│       │   │   ├── CursorFileHelper.java        # AAPT binary parser & 24dp viewport validator
│       │   │   ├── CursorItem.java              # Cursor style model & state definitions
│       │   │   ├── CursorManager.java           # SharedPreferences & theme persistence manager
│       │   │   └── CursorState.java             # Enum: DEFAULT, TEXT, POINTER
│       │   └── res/
│       │       ├── layout/
│       │       │   ├── activity_main.xml        # Glassmorphic 3-tab layout (Home, Test, Settings)
│       │       │   ├── activity_add_cursor.xml  # Multi-state cursor import interface
│       │       │   ├── activity_settings.xml    # Secondary settings layout
│       │       │   ├── overlay_cursor_view.xml  # Floating cursor pointer view
│       │       │   ├── overlay_mousepad.xml     # Floating touchpad with mode bar & drag handle
│       │       │   └── item_custom_cursor.xml   # Custom cursor pack list item
│       │       ├── drawable/                    # Glass cards, buttons, badges, vector pointers
│       │       ├── values/
│       │       │   ├── colors.xml               # Glassmorphic neon & obsidian palette
│       │       │   ├── strings.xml              # Clean, natural English copy
│       │       │   └── themes.xml               # Window styles & translucent dialogs
│       │       └── xml/
│       │           ├── accessibility_service_config.xml # Accessibility flags & capabilities
│       │           ├── backup_rules.xml
│       │           └── data_extraction_rules.xml
│       └── test/java/com/example/
│           └── ExampleUnitTest.java             # Unit tests for AAPT binary magic & validator
```

---

## 🚀 Getting Started & Building from Source

### Prerequisites:
* **Java Development Kit (JDK)**: Version 11 or higher.
* **Android SDK**: API Level 35 (Android 15) with Build Tools 35.0.0+.
* **Gradle**: 8.x+ (invoked via the standard `gradle` command).

### Build Commands:
```bash
# Clone the repository
git clone https://github.com/sr7mods/xCursor.git
cd xCursor

# Run unit tests (including AAPT binary validator test cases)
gradle :app:testDebugUnitTest

# Assemble Debug APK
gradle :app:assembleDebug

# The built APK will be located at:
# app/build/outputs/apk/debug/app-debug.apk
```

---

## 📱 Permissions Explained

| Permission | Android Identifier | Rationale |
| :--- | :--- | :--- |
| **System Alert Window** | `SYSTEM_ALERT_WINDOW` | Permits drawing the floating cursor pointer and trackpad over other applications. |
| **Accessibility Service** | `BIND_ACCESSIBILITY_SERVICE` | Enables real-time hover detection over text/links and dispatches click/scroll gestures. |
| **Vibrate** | `VIBRATE` | Provides subtle haptic feedback when toggling modes or performing trackpad clicks. |
| **Foreground Service** | `FOREGROUND_SERVICE` | Ensures continuous, unthrottled overlay execution during intensive multitasking. |

---

## 👨‍💻 Developer & Community

<p align="center">
  <b>Designed & Developed with precision by 𝐒𝐑𝟕 𝐌𝐨𝐝𝐬</b><br>
  <i>Empowering Android power users with desktop-class navigation tools.</i>
</p>

<p align="center">
  <a href="https://sr7mods.github.io/about-dev/"><img src="https://img.shields.io/badge/Portfolio-SR7%20Mods-00E676?style=for-the-badge&logo=googlechrome&logoColor=black" alt="Portfolio"></a>
  <a href="https://sr7mods.github.io/xCursor/"><img src="https://img.shields.io/badge/Store-xCursor%20Store-9C27B0?style=for-the-badge&logo=github&logoColor=white" alt="Store"></a>
</p>

---

<div align="center">
  <sub>Built with pure Java and high-performance Android Accessibility APIs. Licensed under <a href="LICENSE">GPL-3.0</a>.</sub>
</div>
