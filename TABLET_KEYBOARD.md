# German PC-style tablet layout

This HeliBoard fork uses the existing German QWERTZ subtype on phones and in tablet portrait. On a tablet in landscape it switches to `german_tablet_pc.json`, a full-width PC-inspired layout with:

- German QWERTZ, umlauts, a dedicated number row, and long-press French accents
- Esc and F1–F12
- Insert/Delete/Home/End/Page Up/Page Down and arrow keys
- A permanently visible right-side numeric keypad, with a wider zero key and decimal comma
- Ctrl, Meta, Alt, Fn, AltGr, and a full-width space bar
- A working forward-Delete key in the navigation cluster

The keyboard keeps HeliBoard's selected theme, colors, key borders, and height/spacing preferences. Enable key borders and adjust **Settings → Preferences → Keyboard height** for a more PC-like appearance. HeliBoard's theme editor can be used to tune key colors and contrast.

The numpad is integrated into the landscape letter layout; the separate HeliBoard numpad view remains unchanged. The current key model gives keys uniform row height, so numpad Enter is a normal-height key rather than a vertically spanning desktop key. `Num` is a visual indicator because Android soft keyboards do not expose a Num Lock state here.

## Language setup

Use German as the main language and add French and English under **Settings → Languages & Layouts → Multilingual typing**. Add the matching dictionaries under **Settings → Dictionaries**. QWERTZ remains the physical arrangement in all three languages.

French long-press variants include `é è ê ë`, `à â`, `ç`, `ô œ`, `î ï`, `ù û`, and `ÿ`; German umlauts/ß and common AltGr characters are available from relevant keys too.

## Build

The GitHub Actions workflow builds the debug APK on an Ubuntu runner. Push this branch to your own GitHub fork, then open **Actions → Build tablet keyboard APK → Run workflow**. Download `HeliBoard-German-Tablet-Keyboard` from the completed run's **Artifacts** section.

To build locally from the repository root:

```sh
./gradlew :app:assembleDebugNoMinify
```

The APK is written under `app/build/outputs/apk/debugNoMinify/`. It is a complete, standalone keyboard app; the official HeliBoard app is not required. Gradle packages the supported ABIs into one APK. The `.debug` package suffix only allows this fork to coexist with upstream HeliBoard if desired.
