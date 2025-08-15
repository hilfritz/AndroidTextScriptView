# Android TextScriptView

A customizable Android `View` that displays main text with **subscript** and **superscript** — perfect for chemical formulas, mathematical expressions, and scientific notations. Offers full control over colors, sizes, margins, and positioning.

<p align="left">
  <a href="https://developer.android.com/studio/releases/gradle-plugin"><img alt="AGP" src="https://img.shields.io/badge/AGP-8.x-blue" /></a>
  <a href="https://gradle.org/releases/"><img alt="Gradle" src="https://img.shields.io/badge/Gradle-8.5%2B-brightgreen" /></a>
  <img alt="JDK" src="https://img.shields.io/badge/JDK-17--19-informational" />
  <img alt="API" src="https://img.shields.io/badge/minSdk-21%2B-ff69b4" />
</p>

---

## Table of Contents
- [Features](#features)
- [Demo](#demo)
- [Getting Started](#getting-started)
  - [Installation](#installation)
  - [Minimum Setup](#minimum-setup)
- [Usage](#usage)
- [Attributes](#attributes)
- [API Reference](#api-reference)
- [Compatibility](#compatibility)
- [Troubleshooting](#troubleshooting)
- [Roadmap](#roadmap)
- [Why This Project Matters to Employers](#why-this-project-matters-to-employers)
- [Credits](#credits)
- [Feedback & Contributions](#feedback--contributions)
- [License](#license)

---

## Features
- **Dual script support**: Display both subscript and superscript alongside the main text.
- **Full style control**: Configure text colors, sizes, margins, and offsets independently.
- **Custom fonts**: Apply different typefaces to main, subscript, and superscript text.
- **Lightweight**: No external dependencies, minimal performance overhead.
- **Easy integration**: Use directly in XML or modify at runtime in Java/Kotlin.

---

## Demo
![TextScriptView Demo](https://github.com/hilfritz/TextScriptView/blob/master/screenshot.png)

---

## Getting Started

### Installation
Copy the `TextScriptView` class and any required resources into your project, or include it as a module if you maintain it as a separate library.

### Minimum Setup
In your module `build.gradle` (AGP 8+):
```gradle
android {
    namespace 'com.example.app' // Replace with your app's package
    compileSdk 34

    defaultConfig {
        minSdk 21
        targetSdk 34
        versionCode 1
        versionName "1.0"
    }

    compileOptions {
        sourceCompatibility JavaVersion.VERSION_17
        targetCompatibility JavaVersion.VERSION_17
    }
}
```

---

## Usage

### XML
```xml
<com.hilfritz.library.textscriptview.TextScriptView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    app:normalText="Bicarbonate - HC"
    app:subText="3"
    app:normalTextColor="@color/black"
    app:subTextColor="@color/black"
    android:layout_marginTop="@dimen/margin_d"
    app:normalBetweenScriptMargin="1dp" />
```

### Java
```java
TextScriptView textScriptView = findViewById(R.id.textScriptView);

textScriptView.setText("E = MC");
textScriptView.setSuperScriptText("2");
textScriptView.setTextColor(R.color.navy);
textScriptView.setSubScriptTextColor(R.color.red);
textScriptView.setSuperScriptTextColor(R.color.black);

// Apply custom typeface
textScriptView.getTextView().setTypeface(FontCache.get(FontCache.FONT_GOTCHAGOTHIC_LIGHT, this));
textScriptView.getSuperscriptTextView().setTypeface(FontCache.get(FontCache.FONT_GOTCHAGOTHIC_LIGHT, this));
textScriptView.getSubscriptTextView().setTypeface(FontCache.get(FontCache.FONT_GOTCHAGOTHIC_LIGHT, this));
```

---

## Attributes

| Attribute | Description |
|-----------|-------------|
| `normalText` | Main text content |
| `subText` | Subscript text content |
| `superText` | Superscript text content |
| `normalTextColor` | Color resource for main text |
| `subTextColor` | Color resource for subscript text |
| `superTextColor` | Color resource for superscript text |
| `normalTextSize` | Size resource for main text |
| `subTextSize` | Size resource for subscript text |
| `superTextSize` | Size resource for superscript text |
| `normalBetweenScriptMargin` | Horizontal spacing between main text and scripts |
| `moveSuperUp` | Moves superscript upward (dimension resource) |
| `moveSubDown` | Moves subscript downward (dimension resource) |

---

## API Reference

| Method | Description |
|--------|-------------|
| `getTextView()` | Returns the main `TextView` |
| `getSubscriptTextView()` | Returns the subscript `TextView` |
| `getSuperscriptTextView()` | Returns the superscript `TextView` |

---

## Compatibility
- **minSdk**: 21+
- **compile/target**: API 34 recommended
- **Gradle**: 8.5+
- **Android Gradle Plugin**: 8.x
- **JDK**: 17–19

---

## Troubleshooting
- **Namespace not specified** → Add `namespace` inside your `android {}` block.
- **`android:exported` error** → Add `android:exported` to components with `<intent-filter>` when targeting Android 12+.
- **Font not applied** → Ensure typeface is set on all three text views (main, subscript, superscript).

---

## Roadmap
- [ ] Kotlin extensions for easier usage
- [ ] XML preview support for scripts
- [ ] Animation support for script text changes

---

## Why This Project Matters to Employers
Building **TextScriptView** demonstrates:
- **Custom View expertise**: Creating reusable UI components beyond stock widgets.
- **Attention to detail**: Managing typography, spacing, and visual consistency.
- **API design skills**: Clear, intuitive attributes and public methods.
- **Cross-functional thinking**: Supports both design aesthetics and developer ergonomics.

---

## Credits
- **Author**: Hilfritz Camallere  
- **Purpose**: Simplify displaying script-based text in Android apps.

---

## Feedback & Contributions
Issues and pull requests are welcome!  
[Open an Issue](https://github.com/hilfritz/TextScriptView/issues) | [Submit a Pull Request](https://github.com/hilfritz/TextScriptView/pulls)

---

## License
Choose a license (MIT or Apache 2.0 recommended).
