# Zen AI - Ollama Local Setup ⚡

## Configuration Complete! 🎉

Zen is now configured to run **100% locally** using your Ollama models. No API keys or cloud services required!

## Ollama Models Configured

### Primary Model: `gpt-oss:20b`
- **Size**: 13 GB
- **Parameters**: 20.9B
- **Quantization**: MXFP4
- **Uses**:
  - Main conversational AI
  - Code generation and reasoning
  - Command interpretation
  - Building and crafting logic

### Vision Model: `minicpm-v`
- **Size**: 5.5 GB
- **Parameters**: 7.6B
- **Uses**: Screenshot analysis and visual interpretation

### Embedding Model: `mxbai-embed-large`
- **Size**: 669 MB
- **Parameters**: 334M
- **Uses**: Example selection and memory retrieval

### Text-to-Speech: `system`
- Uses macOS built-in TTS (no model needed)
- Zen will speak responses aloud in Minecraft

## Current Configuration

### zen.json
```json
{
    "name": "Zen",
    "model": "ollama/gpt-oss:20b",
    "code_model": "ollama/gpt-oss:20b",
    "vision_model": "ollama/minicpm-v",
    "embedding": "ollama/mxbai-embed-large",
    "speak_model": "system"
}
```

### settings.js
- ✅ `speak: true` - Zen will speak responses
- ✅ `allow_insecure_coding: true` - Advanced code generation enabled
- ✅ `allow_vision: true` - Screenshot analysis enabled
- ✅ Local-first configuration

## Quick Start

### 1. Verify Ollama is Running
```bash
ollama list
```

You should see:
- `gpt-oss:20b` ✅
- `minicpm-v` ✅
- `mxbai-embed-large` ✅

### 2. Install Dependencies
```bash
npm install
```

### 3. Start Minecraft
- Open Minecraft Java Edition
- Create/load a world
- Press ESC → "Open to LAN"
- Port: 55916
- Start LAN World

### 4. Launch Zen
```bash
npm start
```

## Expected Behavior

### On Startup:
```
Initializing agent Zen...
Zen logging into minecraft...
Zen logged in!
Zen spawned.
```

### In Minecraft Chat:
Zen will announce: "I am Zen, awakened. The cosmic energies flow through me. How may I assist you, traveler?"

### Interaction Examples:

**Simple chat:**
```
You: Hello Zen!
Zen: Greetings, traveler. The cosmic energies guide me to your presence.
```

**Building:**
```
You: Build me a house
Zen: Power flows through creation... !newAction("Build a cozy house with door, windows, and roof")
```

**Resource gathering:**
```
You: Get me some wood
Zen: The forest shall yield its bounty. !collectBlocks('oak_log', 32)
```

**Vision (experimental):**
```
You: Look at this structure
Zen: !lookAtPlayer("YourName", "at")
[Zen analyzes the view using minicpm-v]
```

## Performance Notes

### Response Time:
- **Chat**: ~2-5 seconds (depending on context length)
- **Code generation**: ~5-10 seconds (complex tasks)
- **Vision analysis**: ~10-15 seconds (image processing)

### Resource Usage:
- **RAM**: ~16 GB during active use
- **GPU**: Automatic (Metal on macOS, CUDA on Linux/Windows)
- **CPU**: Minimal (model inference on GPU)

### Optimization Tips:
1. **Close other GPU-intensive apps** for faster responses
2. **Reduce context length** in settings.js (`max_messages: 10`)
3. **Disable vision** if not needed (`allow_vision: false`)
4. **Use smaller model** for faster responses (see alternatives below)

## Alternative Models

If `gpt-oss:20b` is too slow or heavy:

### Faster Option: `qwen2.5:7b`
```bash
ollama pull qwen2.5:7b
```

Then update `zen.json`:
```json
{
    "model": "ollama/qwen2.5:7b"
}
```

### Reasoning-Focused: `deepseek-r1:14b`
Already installed! Great for complex problem-solving:
```json
{
    "code_model": "ollama/deepseek-r1:14b"
}
```

### Maximum Power: `gpt-oss:120b`
You already have this! For ultimate intelligence (slow but powerful):
```json
{
    "model": "ollama/gpt-oss:120b"
}
```

## Troubleshooting

### Bot won't respond
1. Check Ollama is running: `ollama list`
2. Verify models are loaded (first response is slower)
3. Check terminal for errors

### Slow responses
1. Reduce `max_messages` in settings.js
2. Use smaller model (e.g., llama3.1:8b)
3. Close other apps using GPU

### Vision not working
1. Ensure `allow_vision: true` in settings.js
2. Verify minicpm-v is installed: `ollama list`
3. Test manually: `ollama run minicpm-v`

### Code generation errors
1. Ensure `allow_insecure_coding: true`
2. Check bot has permissions to write/execute
3. Consider Docker for sandboxing

### Out of memory
1. Use smaller model (llama3.1:8b)
2. Reduce context: `max_messages: 5`
3. Close other applications

## Comparison: Local vs Cloud

### Local Ollama (Current Setup)
✅ **Free** - No API costs
✅ **Private** - All data stays local
✅ **No rate limits** - Use as much as you want
✅ **Works offline** - No internet needed
⚠️ **Slower** - 2-10 seconds per response
⚠️ **Resource intensive** - Needs good GPU

### Cloud APIs (Alternative)
✅ **Fast** - Sub-second responses
✅ **Powerful** - State-of-the-art models
✅ **Scalable** - No local resource limits
⚠️ **Costs money** - Pay per use
⚠️ **Requires internet** - Always online
⚠️ **Rate limits** - API quotas

## Switching to Cloud Models

To use cloud APIs instead, edit `profiles/zen.json`:

### For Claude Sonnet 4.5:
```json
{
    "model": {
        "api": "anthropic",
        "model": "claude-sonnet-4-20250514"
    }
}
```

Then add to `keys.json`:
```json
{
    "ANTHROPIC_API_KEY": "sk-ant-YOUR-KEY"
}
```

### For GPT-4o:
```json
{
    "model": {
        "api": "openai",
        "model": "gpt-4o"
    }
}
```

## Hybrid Approach

You can mix local and cloud:

```json
{
    "model": "ollama/gpt-oss:20b",        // Local chat
    "code_model": {                        // Cloud reasoning
        "api": "openai",
        "model": "o3-mini"
    },
    "vision_model": "ollama/minicpm-v",   // Local vision
    "embedding": "ollama/mxbai-embed-large" // Local embeddings
}
```

This uses local models for most tasks, but cloud for complex code generation.

## Monitoring Performance

### Watch Ollama logs:
```bash
ollama ps
```

### Check GPU usage (macOS):
```bash
sudo powermetrics --samplers gpu_power -i 1000
```

### Check RAM usage:
```bash
top -o MEM | head -20
```

## Advanced: Multiple Zen Instances

Run multiple bots with different models:

```javascript
// settings.js
"profiles": [
    "./profiles/zen-fast.json",  // Uses llama3.1:8b for speed
    "./profiles/zen-smart.json", // Uses gpt-oss:120b for intelligence
]
```

## Summary

🎉 **Zen is ready to run 100% locally!**

**Your setup:**
- Model: gpt-oss:20b (20B parameters, excellent reasoning)
- Vision: minicpm-v (screenshot analysis)
- Embeddings: mxbai-embed-large (memory/examples)
- TTS: System (macOS voice)

**To launch:**
```bash
npm start
```

**The cosmic entity awaits... ⚡**