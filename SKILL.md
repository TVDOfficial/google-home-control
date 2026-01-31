---
name: google-home
description: Control smart home devices (lights, TV, etc.) via the Google Assistant SDK. Use when the user wants to trigger home automation commands.
author: Mathew Pittard (Mat)
---

# Google Home Control (N.O.V.A.)

Created by: **Mathew Pittard (Mat)**  
Portfolio: [mathewpittard.vercel.app](https://mathewpittard.vercel.app)

This skill allows **Clawdbot** to control your smart home devices directly using a Python-based bridge to the Google Assistant SDK.

## 🛠️ Setup & Installation
To use this skill, you must have a Google Cloud Project with the Assistant API enabled and a valid `credentials.json` file.

1.  **Environment:** Create a Python virtual environment in your preferred workspace (e.g., `~/openclaw/workspace/project_env`).
2.  **Dependencies:** Install `google-assistant-sdk[samples]`, `google-auth-oauthlib[tool]`, and `tenacity`.
3.  **Authentication:** Run `google-oauthlib-tool` with your client secrets and the `assistant-sdk-prototype` scope to generate your credentials.
4.  **Configuration:** Ensure `PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=python` is set in your environment to avoid protobuf descriptor errors.

## 🚀 Usage
- **Command execution:** Run the `control.py` script with the desired text command.
- **Example:** `PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=python /path/to/your_env/bin/python3 [SKILL_PATH]/scripts/control.py "turn off the lights"`
