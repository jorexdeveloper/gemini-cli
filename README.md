# Gemini Command-Line 🤖

**gem-cli** is a command-line AI assistant powered by Google Gemini.

## Demo

![Demo Image](./demo.png)

## 🚀 Installation

Follow these steps to install **gem-cli** on your system.

1. **Download** the script:
   ```bash
   curl -LO https://raw.githubusercontent.com/jorexdeveloper/gemini-cli/main/gem-cli
   ```
2. **Make it executable**:
   ```bash
   chmod +x gem-cli
   ```
3. **Move** it into your `PATH`:
   ```bash
   sudo mv gem-cli /usr/local/bin/
   ```

### 📋 Requirements

- Bash 4+
- curl
- jq
- fmt
- bat (for pretty output)
- xclip or xsel (for clipboard support)

## 🔧 Configuration

Configure **gem-cli** to work with your Google Gemini API key and preferences.

### 🔑 API Key

Set your Gemini API key via environment variable or file.

- **Get free API key [here](https://aistudio.google.com/app/api-keys)**

- **Environment Variable**:
  ```bash
  export GEMINI_API_KEY="your_api_key_here"
  ```
- **Key File** (`~/.gemini.key`):
  ```bash
  echo "your_api_key_here" > ~/.gemini.key
  ```

### ⚙️ Preferences

- **Chat History**
  Stored at `~/.local/share/gem-cli/history/chat.json` by default.
- **Response Saving**
  Saved at `~/.local/share/gem-cli/responses/` when enabled.
- **Log Level**
  Adjust verbosity with `-L` (0–5).

## 💡 Usage

Invoke **gem-cli** with options and an optional prompt.

```bash
gem-cli [OPTIONS] [PROMPT]
```

### 🌐 Global Options

| Flag      | Description                                       |
| --------- | ------------------------------------------------- |
| `-m NAME` | Set the API model (e.g., `gemini-2.5-flash`).     |
| `-i`      | Force interactive mode.                           |
| `-c`      | Print current chat history.                       |
| `-n`      | Backup and start a new chat.                      |
| `-N`      | Start new chat without backup.                    |
| `-p`      | Private chat (disable history & response saving). |
| `-d`      | Disable chat history.                             |
| `-s`      | Show separator between messages.                  |
| `-r`      | Prefer raw output (no pretty printing).           |
| `-R`      | Prefer raw input (disable slash commands).        |
| `-j`      | JSON output (implies raw output).                 |
| `-q`      | Quiet mode (suppress startup messages).           |
| `-Q`      | Quiet + raw output.                               |
| `-l`      | List supported API models.                        |
| `-L INT`  | Set log level (0=NONE to 5=DEBUG).                |
| `-v`      | Print version and exit.                           |
| `-h`      | Print help and exit.                              |

### 🖥️ Interactive Mode

Launch a REPL chat session. Omit a prompt or use `-i` to force interactive mode.

```bash
gem-cli
```

Key commands in session:

- `/help` – Show available commands.
- `/model NAME` – Switch API model.
- `/raw` – Toggle raw output mode.
- `/clear` – Clear current chat.
- `/list` – List supported models.
- `/exit` – End the session.

### 📨 Non-Interactive Mode

Send a single prompt and exit.

```bash
gem-cli "Explain quantum computing in simple terms."
```

Combine with flags:

```bash
gem-cli -j -m gemini-2.5-flash "Generate a meal plan for a vegetarian."
```

## 📂 Chat History & Responses

Manage conversation logs and responses with ease.

- **View History**
  ```bash
  gem-cli -c
  ```
- **New Chat with Backup**
  ```bash
  gem-cli -n
  ```
- **New Chat without Backup**
  ```bash
  gem-cli -N
  ```

## 🔄 Listing Supported Models

Fetch and display models supported for generation.

```bash
gem-cli -l
```

Add `-j` for a JSON list or use `-ll` to print simple model list.

## 🗒️ Common Use Cases

- Quick fact queries
- Multi-turn AI conversations
- Scripted API calls in shell pipelines
- Generating formatted reports or code snippets

## 📜 License

**gem-cli** is licensed under **GPL v3+**.
© 2025 Jore – [GitHub/jorexdeveloper/gemini-cli](https://github.com/jorexdeveloper/gemini-cli)
