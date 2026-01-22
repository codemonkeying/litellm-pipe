Codemaster
Thought a second

Of course. A good README.md is essential for any repository.

Here is a complete README file tailored for your litellm-pipe repo. It explains what the script does, how to install it, and how to configure it, including the part about editing the file directly for the prefix.

You can copy and paste this directly into a README.md file in your new GitHub repository.
LiteLLM Pipe for Open WebUI

A custom pipe for Open WebUI that connects to a LiteLLM proxy, making all of its models available in the chat interface with a clean, customizable prefix.

This pipe is designed to be a simple, single-file solution for integrating a LiteLLM-managed model library into your Open WebUI instance.
Screenshot
Features

    Auto-Discovery: Automatically fetches and lists all available models from your LiteLLM server.
    Customizable Prefix: Easily change the display name for your models (e.g., "Lite:", "Proxy:", "Claude:") by editing one line in the script.
    Simple Setup: Drop-in installation with configuration handled through the Open WebUI admin panel.
    Robust Connection: Handles API keys, streaming, and provides clear error messages in the UI.

Installation

    Place the File Place the litellm_pipe.py file into the pipes directory of your Open WebUI installation. The typical location is:
    bash

    /opt/open-webui/pipes/

    Customize the Prefix (Optional) Open the litellm_pipe.py file with a text editor and change the self.name variable to your desired prefix.
    python

    class Pipe:
        def __init__(self):
            # --- EDIT THIS LINE TO CHANGE THE PREFIX ---
            # This is the name that will appear in the model list.
            self.name = "Lite" 

    Restart Open WebUI For the new pipe to be loaded, you must restart your Open WebUI instance. If you are using Docker, run:
    bash

    docker restart open-webui

    Configure the Pipe
        In Open WebUI, go to Admin Panel > Functions.
        You should see "LiteLLM Pipe" in the list. Click the settings icon (sliders).
        Fill in the following values in the Valves menu:
            LITELLM_API_KEY: Your API key for the LiteLLM server.
            LITELLM_API_BASE_URL: The full URL to your LiteLLM server (e.g., http://192.168.1.50:4000).
        Click Save.

That's it! When you go to select a model in the chat interface, you will see your custom prefix followed by all the models available from your LiteLLM server.
Author

    Tom Miles

License

This project is licensed under the MIT License.
