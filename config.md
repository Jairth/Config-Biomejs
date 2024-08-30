# **Setup BiomeJS**

### **Install BiomeJS**

To install BiomeJS using `bun`, run:
```
bun add --dev --exact @biomejs/biome
```

### **Integrate Biome with your VCS/biome.json**
{
  "vcs": {
    "enabled": true,
    "clientKind": "git"
  }
}

### **Configuration Biomejs**

```
Initialize and Configure BiomeJS
bunx biome init

VSCode Configuration
{
  "[typescript]": {
    "editor.defaultFormatter": "biomejs.biome",
    "editor.formatOnSave": true
  },
  "[javascript]": {
    "editor.defaultFormatter": "biomejs.biome",
    "editor.formatOnSave": true
  },
  "[json]": {
    "editor.defaultFormatter": "biomejs.biome"
  },
  "[jsonc]": {
    "editor.defaultFormatter": "biomejs.biome"
  },
  "[css]": {
    "editor.defaultFormatter": "biomejs.biome",
    "editor.formatOnSave": true
  },
  "editor.quickSuggestions": {
    "strings": true
  },
}
```

### **biome.json**
```
Option 1: Basic Setup
{
  "organizeImports": { "enabled": true },
  "linter": {
    "enabled": true,
    "rules": { "recommended": true },
    "ignore": ["test"]
  }
   "formatter": {
    "enabled": true,
    "lineWidth": 120
  }
}

Option 2: Disable Linting and Formatting
{
  "$schema": "https://biomejs.dev/schemas/1.8.3/schema.json",
  "formatter": {
    "enabled": false
  },
  "linter": {
    "enabled": false,
    "ignore": ["test"]
  },
  "organizeImports": {
    "enabled": false
  }
}

Option 3: Advanced Formatting Setup
{
  "formatter": {
    "indentStyle": "space", // default is `tab`
    "lineWidth": 100 // default is `80`
  },
  "javascript": {
    "formatter": {
      "quoteStyle": "single", // default is `double`
      "lineWidth": 120 // override `formatter.lineWidth`
    }
  },
  "json": {
    "formatter": {
      "enabled": false
    }
  }
}
```


### **BiomeJS CLI Commands**
```
  You can format files and directories using the format command with the --write option:
  bunx biome format --write <files>


  You can lint and apply safe fixes to files and directories using the lint command with the --write option:
  bunx biome lint --write <files>

  The check command runs multiple tools at once. It formats, lints, and organizes imports.
  bunx biome check --write <files>
```


### **Script en tu frontend/package.json**

```
{
  "name": "frontend-project",
  "scripts": {
    "format": "biome format --write ./src",
    "check": "biome check --write ./src"
  }
}
```

### **First-party plugins**
(https://biomejs.dev/guides/editors/first-party-plugins/)
