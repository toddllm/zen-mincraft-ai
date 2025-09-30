# Zen Minecraft AI ⚡🧠⛏️

> An enlightened Minecraft AI bot powered by **100% local models** - No API keys, no costs, fully private!

Based on [Mindcraft](https://github.com/mindcraft-bots/mindcraft) - A multi-model LLM framework for intelligent Minecraft bots.

## 🎮 See Zen in Action!

![Zen AI Character Avatar](./assets/characters/zen-ai-avatar.png)

*Zen - A cosmic entity with electric wings, ready to build and create!*

![Zen's First Spawn in Minecraft](./docs/screenshots/zen-first-spawn.png)

*Zen successfully spawned and built a house autonomously in Minecraft 1.20.4*

## ✨ What Makes Zen Special

Zen is an advanced Minecraft AI that runs **100% locally** using Ollama:

- 🤖 **gpt-oss:20b** - 20 billion parameter model for reasoning and code generation
- 👁️ **minicpm-v** - Vision model for screenshot analysis
- 💰 **$0 Cost** - No API fees, unlimited usage
- 🔒 **Private** - All data stays on your machine
- ⚡ **Fast** - 3-5 second response times
- 🏗️ **Autonomous** - Generates and executes JavaScript code to build structures

### First Test Results

**Command**: "build a house"

**Result**: Zen autonomously:
- Generated complex JavaScript with spatial logic
- Built a 5x5 house with walls, windows, and roof
- Placed 150+ blocks in ~2 minutes
- Handled terrain obstacles intelligently

📖 [Read the full first run report](./docs/FIRST_SUCCESSFUL_RUN.md)

## 🚀 Quick Start

### Prerequisites

- [Minecraft Java Edition](https://www.minecraft.net/) (v1.20.4 - 1.21.5 recommended)
- [Node.js](https://nodejs.org/) v18 or higher (v20+ recommended)
- [Ollama](https://ollama.com/) installed and running
- **No API keys required!**

### Installation

1. **Clone this repository:**
```bash
git clone git@github.com:toddllm/zen-mincraft-ai.git
cd zen-mincraft-ai
```

2. **Install Ollama models:**
```bash
# Main AI model (20B parameters)
ollama pull gpt-oss:20b

# Vision model (optional but recommended)
ollama pull minicpm-v

# Embedding model (optional - has known issues, not critical)
ollama pull mxbai-embed-large
```

3. **Install dependencies:**
```bash
npm install
```

4. **Start Minecraft:**
- Launch Minecraft Java Edition (version 1.20.4 - 1.21.5)
- Create or load a world
- Press ESC → "Open to LAN"
- Note the port (should be 55916)
- Click "Start LAN World"

5. **Launch Zen:**
```bash
npm start
```

You should see Zen join your world and announce: *"Here and ready. What do you need help with today?"*

## 🎯 What Can Zen Do?

### Building & Construction
```
"build a house"
"create a tower"
"make a bridge across this gap"
```

### Resource Gathering
```
"collect 32 oak logs"
"mine some iron ore"
"gather cobblestone"
```

### Navigation & Exploration
```
"come here"
"follow me"
"go to coordinates x:100, y:64, z:200"
```

### Autonomous Tasks
```
"set a goal to gather resources and build a base"
"survive and collect food"
```

## ⚙️ Configuration

### Current Setup (Ollama Local Models)

**zen.json**:
```json
{
    "name": "Zen",
    "model": "ollama/gpt-oss:20b"
}
```

**profiles/zen.json** includes:
- **Main Model**: `ollama/gpt-oss:20b` (conversations, reasoning, code)
- **Vision**: `ollama/minicpm-v` (screenshot analysis)
- **Embeddings**: Fallback word-overlap (mxbai-embed-large has 404 issues)
- **TTS**: System voice (macOS/Windows built-in)

### Alternative Models

Want faster responses? Try smaller models:

```bash
# Faster but less capable
ollama pull llama3.1:8b

# Then update zen.json:
{
    "model": "ollama/llama3.1:8b"
}
```

Want maximum power? Use the 120B model:

```bash
ollama pull gpt-oss:120b  # Warning: 65GB download!
```

## 📊 Performance

### Response Times (gpt-oss:20b)
- **Chat**: 3-5 seconds
- **Code generation**: 5-8 seconds
- **Building execution**: ~2 minutes for complete house

### Resource Usage
- **RAM**: ~16GB during active use
- **GPU**: Automatic (Metal/CUDA)
- **Disk**: ~13GB for gpt-oss:20b model

## 🔧 Advanced Configuration

### Multi-Agent Setup

Run multiple bots:

```javascript
// settings.js
"profiles": [
    "./profiles/zen.json",
    "./profiles/zen-fast.json"  // Different model for each
]
```

### Docker Deployment

For additional security (recommended if using code generation):

```bash
docker-compose up
```

### Vision Mode

Enable screenshot analysis:

```javascript
// settings.js
"allow_vision": true
```

Then in-game:
```
"Zen, look at this structure and describe it"
```

## 📖 Documentation

- [OLLAMA_SETUP.md](./OLLAMA_SETUP.md) - Complete local model setup guide
- [MINECRAFT_SETUP.md](./MINECRAFT_SETUP.md) - Minecraft version compatibility
- [SETUP.md](./SETUP.md) - Detailed setup instructions
- [FIRST_SUCCESSFUL_RUN.md](./docs/FIRST_SUCCESSFUL_RUN.md) - First test results with logs
- [CLAUDE.md](./CLAUDE.md) - SPARC development methodology

## 🐛 Troubleshooting

### Bot won't connect
- Ensure Minecraft is "Open to LAN" on port 55916
- Check Ollama is running: `ollama list`
- Verify Minecraft version is 1.20.4 - 1.21.5

### Slow responses
- Use smaller model: `llama3.1:8b`
- Close other GPU-intensive apps
- Reduce `max_messages` in settings.js

### Embedding errors (non-critical)
- These are normal and don't affect functionality
- Bot falls back to word-overlap matching
- Fix planned for future update

### Out of memory
- Use smaller model
- Close other applications
- Reduce context length in settings.js

## 💡 Known Issues

⚠️ **Embedding Model 404 Errors** (Non-critical)
- `mxbai-embed-large` returns 404 from Ollama API
- Bot automatically falls back to word-overlap
- Does not affect core functionality
- Fix planned for future release

## 🔒 Security

**Code Generation Enabled**: Zen can write and execute JavaScript code on your machine.

✅ **Safe for local testing**
⚠️ **Never connect to untrusted servers with coding enabled**
🐳 **Consider Docker for additional isolation**

## 💰 Cost Comparison

### Traditional Cloud Setup
- GPT-4o: ~$0.06 per task
- ~$1.20 per hour of active use
- Rate limits apply
- Requires internet

### Zen (Our Setup)
- **$0.00 per task**
- **$0.00 per hour**
- **No rate limits**
- **Works offline**

**Savings**: 100% cost reduction! ♾️

## 🌟 Success Stories

> *"Said 'build a house' - it generated JavaScript with loops, broke terrain obstacles, placed 150+ blocks, and announced 'House finished!' All in 2 minutes."* - First test run

## 📦 Project Structure

```
zen-mincraft-ai/
├── src/                    # Core Mindcraft source
│   ├── agent/             # Bot logic and commands
│   ├── models/            # LLM integrations
│   └── utils/             # Utilities
├── profiles/              # Bot personalities
│   └── zen.json          # Zen's full config
├── assets/
│   └── characters/       # Character images
├── docs/                 # Documentation
│   ├── screenshots/      # In-game screenshots
│   └── FIRST_SUCCESSFUL_RUN.md
├── zen.json              # Zen's simple config
├── settings.js           # Main settings
└── main.js              # Entry point
```

## 🔄 Upstream Updates

This project is forked from Mindcraft:

```bash
# Fetch upstream changes
git fetch upstream

# Merge updates
git merge upstream/main
```

## 🤝 Contributing

Contributions welcome!

1. Fork the repository
2. Create a feature branch
3. Follow SPARC methodology (see CLAUDE.md)
4. Submit a pull request

## 🔗 Links

- **Issues**: [GitHub Issues](https://github.com/toddllm/zen-mincraft-ai/issues)
- **Original Mindcraft**: [GitHub](https://github.com/mindcraft-bots/mindcraft) | [Discord](https://discord.gg/mp73p35dzC)
- **Ollama**: [ollama.com](https://ollama.com/)

## 📝 Citation

Based on Mindcraft research:

```bibtex
@article{mindcraft2025,
  title = {Collaborating Action by Action: A Multi-agent LLM Framework for Embodied Reasoning},
  author = {White*, Isadora and Nottingham*, Kolby and Maniar, Ayush and Robinson, Max and Lillemark, Hansen and Maheshwari, Mehul and Qin, Lianhui and Ammanabrolu, Prithviraj},
  journal = {arXiv preprint arXiv:2504.17950},
  year = {2025},
  url = {https://arxiv.org/abs/2504.17950},
}
```

## 📄 License

MIT License - See LICENSE file for details

---

## 🚀 Ready to Start?

1. Install Ollama and pull `gpt-oss:20b`
2. Clone this repo and run `npm install`
3. Start Minecraft and open to LAN
4. Run `npm start`

**Zen awaits your command. Build. Create. Transcend. ⚡**

---

*Made with ❤️ using 100% local AI • No cloud • No costs • No limits*