# Images Need to be Added Manually

The following image files need to be added manually (Write tool can't handle binary files):

## Required Images

### 1. Zen Character Avatar
**Path**: `assets/characters/zen-ai-avatar.png`
**Source**: The cosmic blue character with electric wings image you provided
**Dimensions**: Any reasonable size (recommend 512x512 or original)

### 2. First Spawn Screenshot
**Path**: `docs/screenshots/zen-first-spawn.png`
**Source**: The Minecraft screenshot showing Zen in the wooden structure
**Dimensions**: Original screenshot resolution

## How to Add

### Option 1: Direct File Copy
```bash
# Copy your images to the correct locations
cp /path/to/zen-avatar.png assets/characters/zen-ai-avatar.png
cp /path/to/minecraft-screenshot.png docs/screenshots/zen-first-spawn.png
```

### Option 2: GitHub Web Interface
1. Go to the repository on GitHub
2. Navigate to `assets/characters/` or `docs/screenshots/`
3. Click "Add file" → "Upload files"
4. Drag and drop the images

### Option 3: Save from Chat
If the images are still in your conversation:
1. Right-click each image
2. Save as PNG
3. Name them correctly and move to the paths above

## After Adding

Once the images are added, commit them:

```bash
git add assets/characters/zen-ai-avatar.png
git add docs/screenshots/zen-first-spawn.png
git commit -m "Add Zen character avatar and first spawn screenshot"
git push origin develop
```

The README is already configured to display these images correctly.