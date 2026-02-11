# Google Home Control

Control your smart home devices (lights, TV, etc.) via the Google Assistant SDK. This project provides a Python-based bridge that allows you to trigger home automation commands from the command line or through an agent like Clawdbot.

Created by: **Mathew Pittard (Mat)**
Portfolio: [mathewpittard.vercel.app](https://mathewpittard.vercel.app)

---

## 🚀 Features

- **Voice-less Control**: Send text commands to Google Assistant to control your smart home.
- **Python Integration**: Easy-to-use script for integration into larger projects or agents.
- **Secure**: Uses OAuth 2.0 for secure access to your Google Assistant.

## 🛠️ Step-by-Step Setup

To get this skill working, you'll need to link it to your own Google account. Follow these steps:

### 1. Create a Google Cloud Project
1.  Go to the [Google Cloud Console](https://console.developers.google.com/).
2.  Create a new project (e.g., "My Smart Home").
3.  Enable the **Google Assistant API**.

### 2. Configure OAuth
1.  Go to **APIs & Services > Credentials**.
2.  Configure your **OAuth Consent Screen** (set User Type to "External" and add yourself as a test user).
3.  Create an **OAuth 2.0 Client ID** with the type **Desktop app**.
4.  Download the JSON file and rename it to `client_secret.json`.

### 3. Prepare the Python Environment
This skill requires a Python virtual environment with specific dependencies:

```bash
# Create and activate environment
python3 -m venv google_home_env
source google_home_env/bin/activate

# Install requirements
pip install google-assistant-sdk[samples] google-auth-oauthlib[tool] tenacity
```

### 4. Authorize and Generate Credentials
Run the following command in your terminal to authorize the SDK:

```bash
google-oauthlib-tool --client-secrets /path/to/your/client_secret.json --scope https://www.googleapis.com/auth/assistant-sdk-prototype --save
```

*   This will open a browser window. Log in and grant permissions.
*   It will save a `credentials.json` file to `~/.config/google-oauthlib-tool/credentials.json`.

### 5. Final Configuration
The `control.py` script looks for credentials in the following order:
1.  Environment variable `GOG_HOME_CREDS`.
2.  Standard local config path: `~/.config/google-oauthlib-tool/credentials.json`.

Ensure your credentials are in one of these locations before running the script.

---

## 🚀 Usage

You can run the control script directly from the terminal:

```bash
python scripts/control.py "Your command here"
```

### Example Commands:
- "Turn off the office lights."
- "Set the TV volume to 20."
- "Is the front door locked?"

---

## 📁 Project Structure

- `scripts/control.py`: The main Python script that interacts with the Google Assistant SDK.
- `SKILL.md`: Metadata and instructions for the Clawdbot agent.
- `README.md`: Project documentation (this file).

---

## 🔧 Troubleshooting

If you encounter issues with Protocol Buffers, the script automatically sets `PROTOCOL_BUFFERS_PYTHON_IMPLEMENTATION=python` to ensure compatibility.

If credentials are not found, ensure you have followed the authorization step correctly or set the `GOG_HOME_CREDS` environment variable to the path of your `credentials.json`.
