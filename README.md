LiteLLM Pipe for Open WebUI

A simple and robust pipe to connect Open WebUI with a LiteLLM proxy, featuring a clean, customizable prefix for all your models.

This pipe acts as a bridge, allowing you to leverage LiteLLM's powerful model management and routing capabilities directly within the Open WebUI chat interface.

✨ Key Features

    🔄 Auto-Discovery: Automatically fetches and lists all models available through your LiteLLM instance.
    🖋️ Custom Prefix: Easily set a clean, professional prefix for your models (e.g., "Lite:", "Proxy:") by editing a single line in the script file.
    ⚡ Smart Caching: Uses a 60-minute cache for the model list to ensure fast UI performance.
    🛡️ Clear Error Reporting: Displays understandable errors in the model list if the connection to LiteLLM fails.
    🧩 Simple Configuration: Requires only your LiteLLM API key and base URL to get started.

🚀 Supported Provider

    LiteLLM Proxy: Connects to any LiteLLM instance, giving you access to the 100+ LLMs it supports.

📦 Installation

    Place the File Copy the litellm_pipe.py file into the pipes directory of your Open WebUI installation (e.g., /opt/open-webui/pipes/).
    Set Your Prefix This is the most important step for branding. Open litellm_pipe.py and edit the self.name variable to your desired prefix.
    python

    # --- EDIT THIS LINE TO CHANGE THE PREFIX ---
    self.name = "Lite" 

    Restart Open WebUI For the pipe and your prefix to be loaded, you must restart your Open WebUI instance.
    bash

    # If using Docker
    docker restart open-webui

    Configure API Access
        In Open WebUI, go to Admin Panel > Functions.
        Click the settings icon on the LiteLLM_Pipe.
        Enter your LiteLLM API Key and Base URL in the valves.
        Click Save.

Enjoy your unified model library!

⚙️ Configuration The following settings are available in the pipe's Valves menu in the Open WebUI admin panel.
Setting	Default	Description
CACHE_DURATION_MINUTES	60	How long (in minutes) to cache the discovered model list.
LITELLM_API_KEY	(None)	Required. Your API key for the LiteLLM server.
LITELLM_API_BASE_URL	http://localhost:4000	Required. The full URL to your LiteLLM server.

🎯 Why Use This Pipe?

    Unified Access: Bring all models managed by LiteLLM into a single, clean interface.
    Zero Maintenance: Let LiteLLM handle model updates; the pipe will discover them automatically.
    Simplify Your Setup: Avoids the need for multiple, provider-specific pipes.
    Clean & Professional: A custom prefix keeps your model list organized and easy to navigate.

🔧 Requirementspydantic>=2.0.0 requests>=2.0.0

🌟 RepositoryFind the latest version and contribute at: https://github.com/tom-miles/litellm-pipe

📝 LicenseMIT License - Feel free to modify and distribute!

Built by Tom Miles | Version 1.5.0
