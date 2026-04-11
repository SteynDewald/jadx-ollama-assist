# Jadx Ollama Assist Plugin

A Jadx GUI plugin that connects decompiled code with a local Ollama model for assisted reverse engineering, code analysis, and Kotlin integration guidance.

## Features

- Right-click decompiled code in Jadx and choose `Analyze with Ollama`
- Interactive assistant panel for custom prompts and mode-based analysis
- Built-in guidance for code review, deobfuscation, and Kotlin integration
- Configurable Ollama endpoint, model, and temperature
- Project-wide analysis support for broader architectural insights

## Installation

1. Build the plugin JAR from the project root:

```powershell
./gradlew jar
```

2. Copy the generated JAR file from `build/libs/` into the Jadx `plugins` directory.

3. Run Jadx GUI using Java 11 or newer. The plugin depends on Jadx Core and requires a Java 11 runtime.

4. After installation, open Jadx GUI and use the `Ollama Settings` menu entry to configure the plugin.
   The configuration screen lets you set the Ollama endpoint, model name, and temperature.

## Usage

1. Open Jadx GUI and load an APK or DEX bundle.
2. Right-click a decompiled class or method node.
3. Select `Analyze with Ollama`.
4. Use the panel to choose a mode and enter a custom question.

### Prompt examples

- `How can I use this in a Kotlin Android app?`
- `Generate a Kotlin example for this API flow.`
- `Explain what this class does and call out any security risks.`
- `Suggest integration points for this code in a larger Android project.`

## Supported modes

- `Custom Prompt Only (No preset focus)` — your text is the primary instruction.
- `Advanced AI De-obfuscation` — rewrite decompiled code into readable form.
- `General RE & Malware check` — identify suspicious behavior and logic.
- `Project-wide review / Kotlin example` — produce broader architecture and Kotlin guidance.
- `Data Exfiltration`, `Permission Abuse`, `Suspicious API Flows` — focus on security risks.

## Configuration

After installing the plugin, open Jadx GUI and select the `Ollama Settings` menu item.
This brings up the plugin configuration screen so you can set the local Ollama endpoint, choose a model, and adjust response temperature.

- `Endpoint URL` — usually `http://localhost:11434`
- `Model Name` — e.g. `deepseek-coder:6.7b`
- `Temperature` — lower values are more deterministic

If the `Ollama Settings` menu item does not appear immediately, restart Jadx after copying the JAR into the `plugins` directory.

Configuration is saved in `~/.ollama/ollama.toml`.

## Development

- Build: `./gradlew jar`
- Tests: `./gradlew test`

## Release

This repository includes a `v1.0` release tag for the initial production-quality plugin artifact.

## Authors

- Dewald Steyn <djsteyn@gmail.com>

> If you have a GitHub handle, add it here as `@your-handle` for author attribution.

## License

This project is published under the MIT License. See `LICENSE` for full terms.

## GitHub publishing guidance

- Create a public repository on GitHub and push the current branches.
- Use repository topics such as: `jadx`, `jadx-gui`, `plugin`, `ollama`, `ai`, `reverse-engineering`, `deobfuscation`, `kotlin`, `android`.
- Link to the Ollama project at https://ollama.ai for setup and model guidance.
- Enable Discussions in repository settings if you want blog-like conversations and community discussion.
- Use Issues for bug reports and feature requests; the repository includes issue templates in `.github/ISSUE_TEMPLATE/`.
- Forking is allowed by default for public repositories.
- Create a release `v1.0.0` and publish release notes from `RELEASE_NOTES.md`.

## Legal disclaimer

- This project is not affiliated with or endorsed by Jadx or Jadx GUI. Jadx and Jadx GUI are independent open-source projects.
- Use this plugin only for lawful reverse engineering, security research, and developer productivity.
- Do not use this tool to enable piracy, unauthorized access, or illegal distribution of software.
- No warranty is provided; see the MIT License for details.

## Notes

- The plugin requires Java 11 at runtime because of the Jadx core dependency.
- Use explicit Kotlin or Android prompts for the best assistant output.
- Keep the local Ollama service running while using the plugin.
