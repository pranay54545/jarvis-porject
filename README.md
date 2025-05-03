## Jarvis-PC Assistant

A free, offline, modular PC assistant inspired by J.A.R.V.I.S. It uses voice recognition, a local language model, and automation scripts to respond to voice commands and perform tasks on your computer—all without internet or any subscription fees.

---

### Features

* **Offline Speech I/O**: Capture voice commands using voice2json or Rhasspy (offline STT/NLP/TTS).
* **Local Language Model**: Run open-source LLMs on your PC with AMD GAIA or HuggingFace models for natural-language understanding.
* **Desktop Automation**: Control applications, simulate mouse/keyboard, and manage files with AutoHotkey or Node-RED flows.
* **Modular Skills**: Add new capabilities by creating simple Python modules in the `skills/` folder.
* **Plugin Architecture**: Easily extend Jarvis to control smart-home devices via Home Assistant.
* **Optional UI**: Chat window via Electron or web dashboard via Streamlit.

---

### Quick Start

1. **Clone this repository**

   ```bash
   git clone https://github.com/pranay54545/jarvis-project.git
   cd jarvis-project
   ```

2. **Set up Python environment**

   ```bash
   python -m venv jarvis-env
   source jarvis-env/bin/activate   # Linux/macOS
   .\\jarvis-env\\Scripts\\activate  # Windows PowerShell
   pip install -r requirements.txt
   ```

3. **Install Voice Stack**

   * **voice2json** (Linux): `sudo apt install voice2json`
   * **Rhasspy** (cross-platform): `docker run -d -p 12101:12101 rhasspy/rhasspy`

4. **Configure Local LLM**

   * **GAIA**: Follow [GAIA setup instructions](https://github.com/Gaia-Project/gaia) to load your model.
   * **HuggingFace**: Install transformers and choose a small model: `pip install transformers`.

5. **Set up Automation**

   * **AutoHotkey** (Windows): Install from [https://www.autohotkey.com/](https://www.autohotkey.com/) and verify scripts in `autohotkey/`.
   * **Node-RED**: `npm install -g node-red`, then `node-red` and import `flows.json`.

6. **Run Jarvis**

   ```bash
   python main.py
   ```

   Speak a command like "Open YouTube" or "What's the weather?" and watch Jarvis act!

---

### Adding New Skills

1. Create a new file in `skills/`, e.g., `weather.py`.
2. Define a function `handle(intent, slots)` that performs the task.
3. Register the skill in `config/skills.json` with its intent name.
4. Restart Jarvis to load your new skill.

---

### Contributing

Contributions are welcome! Feel free to open issues or submit pull requests to add new skills, improve documentation, or enhance integration.

---

### License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
