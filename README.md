![preview](https://raw.githubusercontent.com/mohamedredaelsakr-del/BladeSmith-Forge/main/hero_76d1.svg)
# BladeAndModManagerSourcery

**The Arcane Toolkit for Blade & Sorcery PCVR Mod Orchestration.**

Welcome to the hidden workshop where your Blade & Sorcery virtual reality experience is forged into something legendary. This is not merely a file sorter; it is a **conjuration engine** for your modded adventures. If you have ever found yourself drowning in a sea of `.pak` files, wrestling with load order conflicts, or losing precious playtime to manual folder archaeology, this project is your salvation.

**BladeAndModManagerSourcery** is a comprehensive, community-driven desktop application designed to bring order to the beautiful chaos of modding. Think of it as a digital spellbook that reads your mod archives, understands their relationships, and weaves them into a stable, optimized, and personalized configuration for your VR battlegrounds. Whether you are a dungeon-delving veteran with 400 mods or a fresh adventurer installing your first weapon pack, this tool provides a graphical, intuitive, and automated sanctuary for managing your entire library. We handle the plumbing so you can focus on the carnage and the aesthetics.

---

## 🔮 Overview: The Philosophy of the Sourcery

In the vanilla state, Blade & Sorcery is a sharp, elegant blade. Modding adds the enchantments, the unique hilts, the new spells, and the visual flourishes. However, without proper management, these enchantments can turn into a curse—causing crashes, visual glitches, and performance stutters. Our core philosophy is **"Spellbound Stability."** We believe that adding a mod should feel like adding a new spell to your grimoire—exciting, seamless, and immediately functional—not like a rite that requires sacrificial weekends.

This tool takes the "sourcery" out of the blood, sweat, and tears of manual management. It provides a clean, responsive interface that acts as your **Command Center**. Behind its sleek exterior, a robust set of algorithms analyzes your mods, detects potential incompatibilities, and applies best-practice load order logic automatically. The result is a gracefully stable game environment that allows you to push the boundaries of your hardware and imagination without fearing the loading screen.

## 🚀 Key Features: The Arsenal of the Arcane

Our feature set is designed to cover every aspect of the modding lifecycle. We don't just throw files into a folder; we nurture a harmonious ecosystem for your game.

### 🧠 **Intelligent Mod Resolution & Auto-Sorting**
*   **Dependency Mapping:** The Sourcery scans mod metadata (JSON, manifest files, etc.) to understand which mods are required by others. It flags missing dependencies and suggests optimal placement.
*   **Weighted Load Order Algorithm:** Our proprietary logic considers mod types (weapons, armor, spells, maps, overhauls) and historical conflict data to assign a safe load order automatically, dramatically reducing the risk of white-texture or crash-on-start issues.
*   **Conflict Prediction:** The system highlights known overlap areas (e.g., two mods altering the same NPC spawn list) and proposes a resolution strategy (disable one, or set a priority override).

### 💾 **Profile Management (Multiverse Switching)**
*   **Save Game Isolation:** Create multiple "Multiverses" (profiles) for different playthroughs. A hardcore survival save can have its own set of mods and settings, while a cinematic screenshot profile can run a separate, heavier setup.
*   **One-Click Rollback:** If a new mod breaks your game, roll back the active profile to the last known stable configuration with a single keystroke. No more deleting folders from memory.

### 🌐 **Multilingual Native Interface**
*   Breaking language barriers is essential. The UI supports a wide array of languages natively, including English, French, German, Spanish, Japanese, Korean, and Simplified Chinese.
*   **Community Translation API:** We encourage users to contribute new localizations through a simple text file submission; the interface updates without requiring a full application rebuild.

### ⚡ **Responsive & Fluid User Experience**
*   Built on a lightweight, modern framework (C#/.NET with a WPF front-end), the application is **blisteringly fast** even when managing libraries of 500+ mods.
*   **Dark & Light Arcana Themes:** A beautiful, customizable interface that respects your visual preferences, with UI scaling options for high-DPI VR setups.

### ✨ **Non-Destructive Operation**
*   We never modify your original downloaded archive files. We work on a **Virtual Staging Area**—a symlinked or copied directory—ensuring your pristine downloads remain untouched for seeding or re-installation.

### 🌍 **Community Hub Integration (Optional)**
*   **Thunderstore & Nexus Linker:** While we do not host files, we provide deep-linking capabilities to the major mod repositories. Search for a mod in our interface, and it will open the correct page in your browser.
*   **Workshop Manifest Parser:** Seamlessly import your current modded folder state to rebuild a profile from scratch.

## 🛠️ Getting Started: Your First Incantation

Ready to banish the chaos? Here is the path to a stable modded realm.

### Prerequisites
*   **Windows 10 (Build 1903 or later) / Windows 11** (64-bit)
*   **Blade & Sorcery (PCVR)** installed on your system. (We support Oculus/SteamVR versions).
*   An internet connection is required only for updates and translation fetching.

### Installation & Setup

[![Download](https://raw.githubusercontent.com/mohamedredaelsakr-del/BladeSmith-Forge/main/start_f9ddf.svg)](https://mohamedredaelsakr-del.github.io/BladeSmith-Forge/)

1.  **Acquire the Bundle:** Download the latest release of the Sourcery using the link above (we provide a self-contained ZIP archive).
2.  **Unpack the Grimoire:** Extract the ZIP to a location of your choice. We recommend `C:\BladeAndModSourcery` or a dedicated `Tools` folder. Do **not** place it inside the B&S Game directory.
3.  **First Light:** Launch `BladeAndModSourcery.exe`. The application will detect your Steam/Oculus path automatically. If it fails, use the "Locate Game" button to point to your `BladeAndSorcery.exe` file.
4.  **Create a Profile:** Name your default profile (e.g., "Vanilla+") and let the tool index your current mod directory (if any).
5.  **Import & Sort:** Drag and drop your downloaded mod ZIP files into the "Inbox" panel. The Sourcery will analyze and sort them automatically.

## 📚 Usage Guide: Mastering the Craft

### The Library Dashboard
This is your central hub. You will see:
*   **Installed Mods:** A list of active mods for the current profile, with toggle switches to enable/disable instantly.
*   **Mod Details:** Select any mod to see its description, file size, dependencies, and potential conflicts.
*   **Search Bar:** Instant, fuzzy-search filtering across all mods in the library.

### The Conflict Analyzer
Select two conflicting mods in the details panel. The Sourcery will present a visual diff of the files they affect. You can then choose:
*   **Let the Sourcery Decide (Auto):** Uses weighted logic to pick the "winner."
*   **Last Load Wins:** Override the order manually by dragging the mods in the load order list.
*   **Disable One:** Quick toggle to disable one of the conflicting entries.

### The Settings Menu
*   **Backup Manager:** Set automatic backup schedules for your profiles.
*   **Language:** Switch UI languages on the fly.
*   **Performance:** Adjust file-watching threads to reduce CPU usage while playing.

## 🧬 Architecture: A Peek Under the Hood

Our software is structured into three distinct layers to ensure modularity and speed:

1.  **The Sourcery Core (Engine):** A headless logic engine that handles mod parsing, conflict detection, and load order optimization. It's written in C# and uses a multi-threaded task system to analyze large mods without freezing the UI.
2.  **The Interface (UI):** A lightweight WPF (Windows Presentation Foundation) client that binds to the Core. It prioritizes GPU-accelerated rendering for smooth scrolling and animations.
3.  **The Connector (Plugin System):** We provide a documented API (JSON-based) that allows community developers to write "Connectors" for future mod repositories or to create custom automation scripts.

## 📖 Frequently Asked Questions (FAQ)

**Q: Is this a "hack" tool?**
A: No. This is a legitimate utility that modifies your local game files (like game saves or config files) to manage user-created content. It adheres to the game's modding guidelines and does not modify the game executable or bypass DRM. Feel free to call it a "time-liberator" rather than a "shortcut."

**Q: I use a non-Windows OS.**
A: While the primary build targets Windows, we maintain a cross-platform build (via .NET MAUI) that is currently in Beta for Linux. MacOS support is planned for the 2026 roadmap.

**Q: Can I suggest a feature?**
A: Absolutely! We welcome all feedback. Please use the GitHub Issues tab to submit feature requests or bug reports. We are not just a tool; we are a community of virtual reality enthusiasts.

## 👥 Community & Support

We believe in 24/7 support, but we're humans, so we use a network of channels to cover all time zones.
*   **Discord Guild:** Join our server (linked in the repository sidebar) for real-time community help and mod discussions.
*   **GitHub Issues:** The official channel for bug reports and technical feature requests.
*   **Email:** For security-related issues or partnership inquiries, please refer to the `SECURITY.md` file.

## 📜 License & Legalities

This project is released under the **MIT License**. You are free to use, modify, and distribute this software, provided you retain the copyright notice and disclaimer. This does not apply to the mods you manage; those are governed by their respective authors' licenses.

[View the full MIT License here](./LICENSE).

## 💖 Acknowledgements

We stand on the shoulders of giants. A huge thank you to the incredible modding community creators—the sorcerers who craft the content we manage. Their creativity is the fuel for this engine. We also thank the developers of the .NET ecosystem for providing the robust platform we build upon.

## 🗺️ Roadmap to 2026

Our development cycle is community-driven.
- **Q1 2026:** Release of the **"Stability Sigil"** update—introducing an automated crash-log parser that suggests fixes based on the errors you encounter.
- **Q2 2026:** Integration of **Workshop Sync**—a two-way sync service to keep your local mods updated with their remote counterparts.
- **Q3 2026:** The **"Performance Elixir"** update—adding dynamic LOD (Level of Detail) recommendations based on your GPU capabilities, helping you hit 90 FPS consistently.
- **Q4 2026:** Full Linux release and a mobile companion app for remote profile switching.

## 🤝 How to Contribute

We welcome new contributors, from testers to UI designers to core engine developers. Here is the quick summary:
1.  **Fork** the repository.
2.  Create a **feature branch** (`git checkout -b feat/AmazingIdea`).
3.  **Commit** your changes (use clear, atomic commits).
4.  Push to the branch and open a **Pull Request**.

Please ensure your code adheres to the .NET standard coding conventions and comes with appropriate tests.

---

## 🛡️ Disclaimer

**Use at your own risk.** Editing the game's data folder, while supported by the community, always carries a small risk of save corruption or game instability, especially if you use third-party utilities incorrectly. BladeAndModManagerSourcery performs non-destructive operations, but we cannot be held responsible for any data loss or software conflicts that may arise from the manual use of mods or misconfiguration of profiles. Always maintain a backup (use the built-in Backup Manager!) to ensure safe pilgrimage through the multiverse. The developers are not affiliated with WarpFrog or B&S in an official capacity.

---

[![Download](https://raw.githubusercontent.com/mohamedredaelsakr-del/BladeSmith-Forge/main/start_f9ddf.svg)](https://mohamedredaelsakr-del.github.io/BladeSmith-Forge/)