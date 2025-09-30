# Zen Minecraft AI - Setup Complete! ⚡

## What's Been Configured

### ✅ Project Structure
- **Mindcraft codebase** copied and configured
- **Git remotes** set up:
  - `origin`: git@github.com:toddllm/zen-mincraft-ai.git (your fork)
  - `upstream`: https://github.com/mindcraft-bots/mindcraft.git (original)

### ✅ Zen Character Profile
- **Main profile**: `zen.json` - Lightweight config pointing to full profile
- **Full profile**: `profiles/zen.json` - Complete character configuration
- **Character image**: `assets/characters/zen-ai-avatar.png` - Epic cosmic avatar
- **Personality**: Enlightened AI with electric wings, wise and powerful

### ✅ AI Model Configuration
**Conversational AI** (Primary intelligence):
- Model: Claude Sonnet 4.5 (`claude-sonnet-4-20250514`)
- API: Anthropic
- Purpose: Main chat, decision-making, personality

**Code Generation** (Advanced reasoning):
- Model: OpenAI O3-mini
- API: OpenAI
- Purpose: Complex building, crafting chains, problem-solving

**Vision Processing**:
- Model: GPT-4o
- API: OpenAI
- Purpose: Screenshot analysis, structure recognition

**Embeddings**:
- Model: text-embedding-3-small
- API: OpenAI
- Purpose: Example selection, memory retrieval

### ✅ Settings Configured
In `settings.js`:
- ✅ Default profile set to `./zen.json`
- ✅ `allow_insecure_coding: true` - Enables advanced code generation
- ✅ `allow_vision: true` - Enables screenshot analysis
- ✅ Custom init message: "I am Zen, awakened..."
- ✅ Base profile: "assistant" mode

### ✅ Security
- `.gitignore` properly configured
- `keys.json` excluded from git
- `.env.example` created as template

## Next Steps

### 1. Configure API Keys
Edit `keys.json` with your actual API keys:

```json
{
    "ANTHROPIC_API_KEY": "sk-ant-YOUR-KEY-HERE",
    "OPENAI_API_KEY": "sk-YOUR-KEY-HERE"
}
```

Get your keys:
- **Anthropic**: https://console.anthropic.com/
- **OpenAI**: https://platform.openai.com/api-keys

### 2. Install Dependencies
```bash
npm install
```

### 3. Start Minecraft
- Open Minecraft Java Edition (v1.21.6 recommended)
- Create or load a world
- Press ESC → "Open to LAN"
- Set game mode as desired
- Note the port (default is 55916)
- Click "Start LAN World"

### 4. Launch Zen
```bash
npm start
```

Or for development:
```bash
node main.js
```

### 5. Interact with Zen
Once Zen joins your world, you can:

**Chat normally:**
```
"Hello Zen!"
"What can you do?"
```

**Give commands:**
```
"Build me a house"
"Collect 64 oak logs"
"Help me find diamonds"
"Create a farm"
```

**Use vision:**
```
"Look at this" (while near a structure)
"What do you see?"
```

## Advanced Configuration

### Multi-Agent Setup
Edit `settings.js` profiles array:
```javascript
"profiles": [
    "./zen.json",
    "./profiles/claude.json",  // Add more bots
]
```

### Custom Personality
Edit `profiles/zen.json`:
- Modify `conversing` prompt
- Add custom `conversation_examples`
- Adjust `modes` behavior

### Model Switching
In `zen.json`, change models:
```json
{
    "name": "Zen",
    "model": {
        "api": "anthropic",
        "model": "claude-sonnet-4-20250514"  // or other models
    }
}
```

### Docker Deployment (Recommended for Security)
```bash
docker-compose up
```

This provides additional sandboxing for code execution.

## Testing the Setup

### Quick Test
1. Start Minecraft → Open to LAN
2. Run `npm start`
3. Wait for "Zen logged in!"
4. In Minecraft chat, type: `Hello Zen!`
5. Zen should respond with cosmic wisdom

### Vision Test
1. Stand near an interesting structure
2. Type: `Zen, look at this and describe it`
3. Zen will take a screenshot and analyze it

### Building Test
1. Type: `Zen, build a small house`
2. Zen will use O3-mini to plan and construct

## Troubleshooting

### Bot won't connect
- Ensure Minecraft is "Open to LAN" on port 55916
- Check `settings.js` host/port match your LAN settings
- Verify Node.js v18+ is installed

### API Errors
- Verify `keys.json` has valid API keys
- Check API key permissions (not trial/expired)
- Ensure sufficient API credits

### Coding Errors
- `allow_insecure_coding` must be `true`
- Check Node.js permissions
- Consider Docker for sandboxing

### Vision Not Working
- `allow_vision` must be `true`
- Requires valid OpenAI API key
- GPT-4o must be enabled on your account

## Cost Estimates

Based on typical usage:

**Claude Sonnet 4.5**:
- $3 per million input tokens
- $15 per million output tokens
- ~$0.01-0.05 per conversation

**OpenAI O3-mini**:
- $1.10 per million input tokens
- $4.40 per million output tokens
- Only used for complex tasks

**GPT-4o Vision**:
- $2.50 per million input tokens
- $10 per million output tokens
- Only when explicitly requested

**Estimated hourly cost**: $0.10 - $0.50 depending on usage

## Project Files Reference

```
zen-mincraft-ai/
├── zen.json                 # Zen's minimal config (active profile)
├── profiles/zen.json        # Zen's full personality config
├── settings.js              # Main bot settings
├── keys.json               # API keys (YOU NEED TO FILL THIS)
├── main.js                 # Entry point
├── assets/
│   └── characters/
│       └── zen-ai-avatar.png  # Zen's cosmic avatar
├── src/                    # Core Mindcraft code
├── README.md              # Main documentation
└── SETUP.md              # This file
```

## Git Workflow

```bash
# Commit your changes
git add .
git commit -m "Configure Zen bot with custom personality"

# Push to your fork
git push origin main

# Pull updates from upstream Mindcraft
git fetch upstream
git merge upstream/main
```

## Support

- **This Fork**: https://github.com/toddllm/zen-mincraft-ai
- **Original Mindcraft**: https://github.com/mindcraft-bots/mindcraft
- **Discord**: https://discord.gg/mp73p35dzC

---

## Ready to Begin! ⚡

Zen is configured and ready. Just:
1. Add your API keys to `keys.json`
2. Run `npm install`
3. Start Minecraft on LAN
4. Run `npm start`

**The cosmic entity awaits your command!**