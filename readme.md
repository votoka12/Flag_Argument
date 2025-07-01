# JVM Performance Flags for Minecraft & Java Applications



**⚠️ Warning / Cảnh Báo**
>**⚠️ Some of the flags listed may be deprecated in older JVM versions, unavailable in newer ones, or specific to custom/internal builds.
Please research and test each flag carefully to ensure compatibility with your system and Java distribution.**

>**⚠️ Một số flag trong danh sách có thể đã bị loại bỏ ở các phiên bản JVM cũ, không còn tồn tại ở các phiên bản JVM mới, hoặc chỉ có trong các bản JVM tùy chỉnh/nội bộ.
Bạn nên tự nghiên cứu và kiểm tra từng flag để đảm bảo phù hợp với hệ thống và bản Java mà bạn đang sử dụng.**
This repository provides a comprehensive list of **JVM optimization flags**, tailored for:

- 🧠 **High-performance Java applications**
- 🧩 **Minecraft modpacks & large-scale modded servers**
- 💪 **SIMD, AVX, FMA3, and vectorized code optimizations**
- 🗂️ **Memory and GC tuning (ZGC, Shenandoah, G1)**

The list has been compiled and tested on:

- Java 17 to 21 (Zulu & OpenJDK)
- Machines with high core counts and NUMA configurations
- Use cases with **virtual threads**, **large heap sizes**, and **real-time terrain generation/rendering**

---

## 📄 Files

- `Arg English.md`: Bilingual (English + Vietnamese) list of JVM flags grouped by category, with technical notes
- `Arg Tiếng Việt.txt` *(optional)*: Original Vietnamese version

---

## 📌 Features

- Organized into categories: GC, SIMD, AVX, NUMA, Memory, Debug, Minecraft-specific
- Each flag includes technical annotations and comments
- Performance-focused: Reduces latency, improves thread scalability, speeds up memory access and vector operations
- Suitable for real-time applications like Minecraft terrain, mesh rendering, and simulation

---

## 💡 Example Use Case

For a Minecraft modded server with ZGC and AVX2 optimization:

```bash
-Xmx128G \
-XX:+UseZGC -XX:+ZProactive -XX:+UseStringDeduplication \
-XX:+UnlockExperimentalVMOptions --add-modules jdk.incubator.vector \
-XX:+UseVectorCmov -XX:+EnableVectorSupport -XX:+UseAES \
-Djdk.virtualThreadScheduler.parallelism=64
```

---

## 📢 Contributions

- Feel free to suggest flags, test cases, or benchmark results via Pull Request or Issue.
- If you're a Minecraft mod developer, JVM enthusiast, or tuning expert – we'd love your input!

---

## 📬 Contact

Created by a performance tuning enthusiast passionate about Minecraft modding, native acceleration, and bytecode/JVM internals.

> 🇻🇳 Bản song ngữ giúp người dùng Việt dễ dàng tối ưu hiệu năng. English/Vietnamese bilingual flags list for global JVM tuning enthusiasts.

---

Enjoy smoother performance and more FPS 🚀

> Inspired by real testing on multi-CPU Xeon systems with AVX2, ZGC and native JNI agents.


##**🎮 How to Add JVM Flags to Minecraft Launcher**
##**🧩 Cách thêm đối số JVM vào Minecraft**
>⚙️ This guide works for official Minecraft Launcher, Prism Launcher, GDLauncher, or most custom launchers.
>⚙️ Hướng dẫn này áp dụng cho Minecraft Launcher chính thức, Prism Launcher, GDLauncher hoặc các launcher tuỳ chỉnh khác.

##**🔧 Step-by-step (English)**
Open your Minecraft Launcher.

Go to "Installations" tab.

Click "Edit" on the installation you want to modify.

Click "More Options" (or "Show More").

In the "JVM Arguments" box, paste the flags you want (replace the default).

Save and launch the game.

💡 Example:
-Xmx8G -XX:+UseZGC -XX:+UnlockExperimentalVMOptions ...



##**🔧 Các bước thực hiện (Tiếng Việt)**

Mở Minecraft Launcher.

Vào tab "Installations" (Cài đặt).

Bấm vào "Edit" (Chỉnh sửa) bản cài đặt bạn muốn tối ưu.

Chọn "More Options" (Tuỳ chọn nâng cao).

Trong phần "JVM Arguments", dán các dòng flag tối ưu (thay thế dòng mặc định).

Lưu lại và chạy game.

💡 Ví dụ:
-Xmx8G -XX:+UseZGC -XX:+UnlockExperimentalVMOptions ...

##**🧠 Notes / Ghi chú**
>**💡 English**
Don't use too many flags at once if you're unsure. Try small groups first.
Use at least Java 17 to enable modern features like ZGC, jdk.incubator.vector, etc.
If you're playing modded Minecraft, make sure your launcher is using the correct Java version (e.g. Zulu, OpenJDK, etc).

>**💡 Tiếng Việt**
Không nên dùng quá nhiều flag nếu bạn không chắc. Hãy thử từng nhóm nhỏ.
Dùng ít nhất Java 17 để các flag như ZGC, jdk.incubator.vector hoạt động.
Nếu chơi bản modded, hãy chắc chắn launcher dùng đúng phiên bản Java (Zulu, OpenJDK, v.v.)



