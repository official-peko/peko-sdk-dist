# peko-sdk-dist

Compressed SDK distributions for Peko. `peko setup` downloads the assets
attached to the latest release and unpacks them into `~/.Peko`.

| Asset | Contents |
|---|---|
| `Compiler.tar.zst` | The compiler tree: LLVM 18, the bundled JDK, bundling tools, headers |
| `linux-x86_64.tar.zst`, `linux-arm.tar.zst` | Linux sysroots and the GTK/WebKit runtime stack |
| `linux-gtk.tar.zst` | GTK development headers |
| `android.tar.zst` | Android NDK and build tools |
| `apple-support.tar.zst` | Apple build support files |

## Third-party software

These archives redistribute third-party software in binary form. Each component
keeps its own license; nothing here relicenses any of it. A summary ships inside
`Compiler.tar.zst` as `THIRD-PARTY-NOTICES.txt`, and each component's own
license file is preserved in place.

The significant components:

| Component | License | Where the text lives |
|---|---|---|
| LLVM 18.1.8 (clang, lld, libLLVM) | Apache-2.0 WITH LLVM-exception | `llvm18/LICENSE.TXT` |
| BellSoft Liberica JDK 25 | GPL-2.0 WITH Classpath Exception | `java/<platform>/LICENSE`, `java/<platform>/legal/` |
| GTK, WebKitGTK, GLib, GStreamer and the Linux desktop stack | predominantly LGPL-2.1-or-later, with MIT, BSD, and Unicode components | preserved in the toolchain tree |
| Android NDK | Apache-2.0 | preserved in the NDK tree |
| Android SDK build tools | [Android SDK License Agreement](https://developer.android.com/studio/terms) | as shipped by Google |

Not redistributed here: the Apple SDKs (supplied by your Xcode install) and the
Microsoft Windows SDK and CRT (downloaded by `peko setup --windows` from
Microsoft after you accept the Microsoft license).

### Source availability

The JDK is GPL-2.0 with the Classpath Exception, and much of the Linux stack is
LGPL-2.1. Both require that complete corresponding source be available.

- JDK source is published by BellSoft at <https://bell-sw.com/pages/downloads/>
  and mirrored at <https://github.com/bell-sw/Liberica>.
- Linux stack source is available from the distribution the binaries were built
  from.

For the exact source corresponding to any binary in these archives, contact
contact@pekoui.com.

The LGPL components are redistributed unmodified and linked dynamically, so they
can be replaced with your own builds.

## License

This repository contains no Peko-authored source. Peko's own toolchain is
licensed under the MIT License and lives at
[official-peko/peko-tools](https://github.com/official-peko/peko-tools).
