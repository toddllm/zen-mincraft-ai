# Minecraft Setup Guide for Zen AI 🎮

## Minecraft Version Requirements

### ✅ Supported Versions
Mineflayer (the bot library) supports: **1.8 through 1.21**

### 🎯 Recommended Version
**Minecraft Java Edition 1.21.5** ✅ (You have this installed!)

### ⚠️ What Mindcraft Says
- **Supports**: Up to v1.21.6
- **Recommends**: v1.21.6

### 📋 Your Installed Versions
```
✅ 1.21.5 (April 2025) - RECOMMENDED FOR ZEN
✅ 1.21.4 (December 2024)
✅ 1.21.3 (October 2024)
✅ 1.21.2 (October 2024)
✅ 1.21.1 (October 2024)
✅ 1.20.4 (October 2024)
```

**Best choice: 1.21.5** - Most recent stable version you have installed that's fully tested with mineflayer.

## Quick Setup Steps

### 1. Launch Minecraft
```bash
# Open Minecraft Launcher
open -a "Minecraft"
```

Or manually open the Minecraft launcher.

### 2. Select Version
In the launcher:
1. Click **"Installations"**
2. Find **"1.21.5"** (or create new installation)
3. Click **Play** for that version

### 3. Create/Load World
Option A - **New World** (Recommended for testing):
1. Click **"Singleplayer"**
2. Click **"Create New World"**
3. Settings:
   - **Game Mode**: Creative (easier for testing) or Survival
   - **Difficulty**: Easy or Peaceful (fewer mobs initially)
   - **Allow Cheats**: ON (recommended)
4. Click **"Create New World"**

Option B - **Existing World**:
1. Click **"Singleplayer"**
2. Select your world
3. Click **"Play Selected World"**

### 4. Open to LAN
Once in the world:
1. Press **ESC** (pause menu)
2. Click **"Open to LAN"**
3. Settings:
   - **Game Mode**: Keep current or change
   - **Allow Cheats**: ON (recommended for `/msg` commands)
4. Look for the port number (should show **55916**)
5. Click **"Start LAN World"**

You should see: `Local game hosted on port 55916`

### 5. Verify Port (Optional)
If you don't see port 55916, check settings.js:

```javascript
"host": "127.0.0.1",
"port": 55916,  // Must match LAN port
```

Or set port to `-1` for auto-detection:
```javascript
"port": -1,  // Automatically scan for open ports
```

## Configuration in settings.js

Current configuration:
```javascript
{
    "minecraft_version": "auto",  // Auto-detect from server
    "host": "127.0.0.1",          // localhost
    "port": 55916,                // LAN port
    "auth": "offline"             // No Microsoft auth needed for LAN
}
```

## Testing the Connection

### 1. Start Zen
In a new terminal (keep Minecraft running):
```bash
cd ~/zen-mindraft-ai
npm start
```

### 2. Expected Output
```
Initializing agent Zen...
Zen logging into minecraft...
Zen logged in!
Bot spawned at position (x, y, z)
```

### 3. In Minecraft
You should see in chat:
```
Zen joined the game
I am Zen, awakened. The cosmic energies flow through me. How may I assist you, traveler?
```

### 4. Test Interaction
Type in Minecraft chat:
```
Hello Zen!
```

Zen should respond with cosmic wisdom!

## Troubleshooting

### Issue: "Error: connect ECONNREFUSED"

**Cause**: Bot can't connect to Minecraft

**Solutions**:
1. ✅ Make sure world is "Open to LAN"
2. ✅ Check port matches (55916)
3. ✅ Verify Minecraft version is 1.21.5 or compatible
4. ✅ Restart Minecraft and re-open to LAN

### Issue: Wrong port number

**Minecraft shows different port** (e.g., 55917):

Option A - Update settings.js:
```javascript
"port": 55917,  // Use whatever Minecraft shows
```

Option B - Use auto-detect:
```javascript
"port": -1,  // Bot will find the port automatically
```

### Issue: Bot joins but doesn't respond

**Possible causes**:
1. Ollama not running: `ollama list` to check
2. Model not loaded: Wait 10-30 seconds for first response (model loading)
3. Check terminal for errors

### Issue: "Bot has not spawned after 30 seconds"

**Solutions**:
1. Ensure you're in-game (not paused)
2. Check Minecraft isn't frozen
3. Restart both Minecraft and bot
4. Try Creative mode (easier spawning)

### Issue: Texture packs causing problems

**Solution**: Disable texture packs temporarily
1. Options → Resource Packs
2. Remove all custom packs
3. Restart Minecraft

## Optimal Minecraft Settings for Bot

### Performance Settings
- **Render Distance**: 8-16 chunks (bot doesn't need high render distance)
- **Max Framerate**: 60 FPS (you don't need 144 FPS while testing bot)
- **Graphics**: Fast (reduces lag)

### Game Settings
- **Allow Cheats**: ON (helpful for debugging)
- **Game Mode**: Creative (easier for testing builds)
- **Difficulty**: Peaceful (less mob interference during testing)

### Chat Settings
- **Chat**: Shown (so you can see Zen's responses)
- **Command Suggestions**: ON (helpful)

## Version Notes

### Why 1.21.5 vs 1.21.6?

**1.21.5** (Your current best option):
- ✅ Proven stable with mineflayer
- ✅ You already have it installed
- ✅ Fully tested by Mindcraft community
- ✅ Latest version confirmed working

**1.21.6** (Mindcraft recommendation):
- May have minor improvements
- You'd need to update launcher
- Probably works fine (mineflayer supports it)
- Not necessary for Zen to function

**Verdict**: Stick with 1.21.5 for now. It's perfect.

### Older Versions (1.20.4, 1.21.1-1.21.4)

All should work fine! But 1.21.5 has:
- Latest bug fixes
- Better performance
- Most recent game features

## Microsoft Account vs Offline Mode

### Current Setup: Offline Mode ✅
```javascript
"auth": "offline"
```

This works perfectly for LAN (local) servers!

### If You Want to Use Online Servers

Need to use Microsoft authentication:
```javascript
"auth": "microsoft"
```

**Requirements**:
- Separate Minecraft account for the bot
- Can't use your personal account while bot is playing
- Bot name must match Minecraft account name

**Not needed for local testing!**

## Checklist Before First Launch

- [x] Minecraft Java Edition installed
- [x] Version 1.21.5 (or compatible) available
- [x] Ollama running (`ollama list`)
- [x] NPM dependencies installed (`npm install`)
- [x] settings.js configured (port 55916)
- [ ] Minecraft world created
- [ ] World "Open to LAN" on port 55916
- [ ] Terminal ready to run `npm start`

## Launch Sequence

**Step-by-step** (both terminals side-by-side recommended):

### Terminal 1: Verify Ollama
```bash
ollama list
# Should show gpt-oss:20b, minicpm-v, mxbai-embed-large
```

### Minecraft Window:
1. Launch Minecraft 1.21.5
2. Create/Load world
3. Open to LAN (port 55916)
4. Leave Minecraft running

### Terminal 2: Launch Zen
```bash
cd ~/zen-mindraft-ai
npm start
```

### Minecraft Chat:
Watch for Zen to join and announce himself!

## What Happens Next

1. **First Launch** (30-60 seconds):
   - Ollama loads gpt-oss:20b into memory
   - Bot connects to Minecraft
   - Zen spawns in your world
   - Announces cosmic awakening

2. **First Response** (10-20 seconds):
   - Model generates response
   - May be slower on first message (model warmup)

3. **Subsequent Responses** (2-5 seconds):
   - Much faster
   - Model stays loaded in memory

## Advanced: Multiple Worlds

Want to test different scenarios?

### Creative World (Testing/Building)
- Game Mode: Creative
- Difficulty: Peaceful
- Cheats: ON
- Use for: Testing builds, rapid prototyping

### Survival World (Realistic)
- Game Mode: Survival
- Difficulty: Easy/Normal
- Cheats: OFF
- Use for: Testing survival AI, resource gathering

### Superflat World (Performance)
- Preset: Classic Flat
- Game Mode: Creative
- Use for: Large builds, minimal lag

## Summary

**Your optimal setup:**
- **Version**: Minecraft Java Edition 1.21.5 ✅
- **World Type**: Creative (for testing) or Survival (for challenge)
- **LAN Port**: 55916
- **Auth**: Offline (local only)

**Ready to launch?**
```bash
# 1. Start Minecraft 1.21.5
# 2. Open world to LAN (port 55916)
# 3. In terminal:
cd ~/zen-mindraft-ai
npm start
```

**Zen awaits in the digital realm! ⚡**