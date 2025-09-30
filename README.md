# Zen Minecraft AI ⚡🧠⛏️

> An enlightened Minecraft AI bot powered by Claude Sonnet 4.5, O3-mini reasoning, and cosmic energy

Based on [Mindcraft](https://github.com/mindcraft-bots/mindcraft) - A multi-model LLM framework for intelligent Minecraft bots.

![Zen AI Character](./assets/characters/zen-ai-avatar.png)

## About Zen

Zen is an advanced Minecraft AI that combines:
- **Claude Sonnet 4.5** for conversational intelligence and decision-making
- **OpenAI O3-mini** for complex reasoning and code generation
- **GPT-4o** for vision interpretation
- A cosmic personality that's wise, powerful, and helpful

Zen appears as a blue enlightened being with electric wings of lightning and fire, ready to help you build, survive, and achieve greatness in Minecraft.

## Quick Start

### Prerequisites
- [Minecraft Java Edition](https://www.minecraft.net/) (v1.21.6 recommended)
- [Node.js](https://nodejs.org/) v18 or higher
- API Keys:
  - **ANTHROPIC_API_KEY** (required for Zen's main personality)
  - **OPENAI_API_KEY** (required for O3-mini reasoning and vision)

### Installation

1. Clone this repository:
```bash
git clone git@github.com:toddllm/zen-mincraft-ai.git
cd zen-mincraft-ai
```

2. Install dependencies:
```bash
npm install
```

3. Configure your API keys in `keys.json`:
```json
{
    "ANTHROPIC_API_KEY": "your-anthropic-key-here",
    "OPENAI_API_KEY": "your-openai-key-here"
}
```

4. Start a Minecraft world and open it to LAN on port **55916**

5. Run Zen:
```bash
npm start
```

## Configuration

### Zen Profile (`zen.json`)

The Zen character is configured with:
- **Conversational Model**: Claude Sonnet 4.5 (superior reasoning and personality)
- **Code Generation**: OpenAI O3-mini (advanced reasoning for complex tasks)
- **Vision**: GPT-4o (screenshot interpretation)
- **Personality**: Wise, powerful, mystical yet practical

### Settings (`settings.js`)

Key settings:
- `allow_insecure_coding: true` - Enables advanced code generation (sandboxed)
- `allow_vision: true` - Enables screenshot analysis
- `base_profile: "assistant"` - Helpful assistant mode
- Bot connects to `localhost:55916` by default

## Zen's Capabilities

### Building & Construction
Zen can build complex structures using advanced planning:
```
"Zen, build me an epic cathedral"
"Create a fortified base with redstone defenses"
"Design a Japanese garden with pagoda"
```

### Survival & Resource Management
```
"Help me survive the night"
"Gather iron and diamonds"
"Set up an automatic farm"
```

### Combat & Defense
```
"Protect me from mobs"
"Build defensive walls"
"Attack that zombie"
```

### Teaching & Guidance
```
"Teach me advanced building techniques"
"Show me how to use redstone"
"Explain enchanting mechanics"
```

## Development with SPARC

This project follows the SPARC (Specification, Pseudocode, Architecture, Refinement, Completion) methodology for systematic development.

See [CLAUDE.md](./CLAUDE.md) for detailed development instructions.

## Project Structure

```
zen-mincraft-ai/
├── src/                    # Core bot source code
│   ├── agent/             # Agent logic and commands
│   ├── models/            # LLM integrations
│   └── utils/             # Utilities and helpers
├── profiles/              # Bot personality profiles
│   └── zen.json          # Zen's configuration
├── assets/
│   └── characters/       # Character images and skins
├── settings.js           # Main configuration
├── keys.json            # API keys (gitignored)
└── main.js              # Entry point
```

## Advanced Features

### Multi-Agent Collaboration
Run multiple bots simultaneously:
```bash
node main.js --profiles ./profiles/zen.json ./profiles/claude.json
```

### Custom Tasks
Run predefined tasks:
```bash
python tasks/run_task_file.py --task_path=tasks/example_tasks.json
```

### Vision Mode
Zen can analyze screenshots when vision is enabled:
```
"Zen, look at this and tell me what you see"
"Analyze this structure"
```

### Code Generation
Zen can write custom JavaScript code for complex actions:
```javascript
await skills.buildStructure(bot, 'castle', {width: 20, height: 30});
```

## Security Notes

⚠️ **Important**:
- `allow_insecure_coding` is enabled for advanced features
- Code execution is sandboxed but still has risks
- Never connect to untrusted public servers with coding enabled
- Consider running in Docker for additional isolation

### Docker Setup
```bash
docker-compose up
```

## API Cost Optimization

Zen uses a tiered model approach to optimize costs:
- Claude Sonnet 4.5: Main conversations (efficient pricing)
- O3-mini: Complex reasoning only when needed
- GPT-4o: Vision analysis when requested

## Upstream & Updates

This project is forked from Mindcraft. To pull updates:

```bash
# Fetch upstream changes
git fetch upstream

# Merge upstream updates
git merge upstream/main
```

## Contributing

Contributions welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Follow SPARC methodology (see CLAUDE.md)
4. Submit a pull request

## Support & Community

- **Issues**: [GitHub Issues](https://github.com/toddllm/zen-mincraft-ai/issues)
- **Original Mindcraft**: [Discord](https://discord.gg/mp73p35dzC)
- **Original Repository**: [mindcraft-bots/mindcraft](https://github.com/mindcraft-bots/mindcraft)

## Citation

Based on Mindcraft:
```
@article{mindcraft2025,
  title = {Collaborating Action by Action: A Multi-agent LLM Framework for Embodied Reasoning},
  author = {White*, Isadora and Nottingham*, Kolby and Maniar, Ayush and Robinson, Max and Lillemark, Hansen and Maheshwari, Mehul and Qin, Lianhui and Ammanabrolu, Prithviraj},
  journal = {arXiv preprint arXiv:2504.17950},
  year = {2025},
  url = {https://arxiv.org/abs/2504.17950},
}
```

## License

MIT License - See LICENSE file for details

---

**Zen awaits your command. Build. Create. Transcend. ⚡**