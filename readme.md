# JVM Performance Flags for Minecraft & Java Applications

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

- `Zgc Flags English.md`: Bilingual (English + Vietnamese) list of JVM flags grouped by category, with technical notes
- `ZGC.txt` *(optional)*: Original Vietnamese version

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

