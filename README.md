# Obzue OS

Browser desktop for ObzueAI product work. Not a native operating system. Not a device-control agent. Not the Corta membrane and not the SI MemBrain site.

## Run

Open `desktop/index.html` in a current browser, or serve the folder:

```bash
python3 -m http.server 8080 --directory desktop
```

## What was rebuilt

The WebSim paste mixed HTML, CSS, and JavaScript and pointed at missing PNGs. This tree splits those files, uses CSS/SVG chrome, implements Start / context / Control Panel / Trash, and gives each video window its own player id.

## Skill

`skills/obzue-product-forge/` is the agent skill that routes hardware, manufacturing, business, and further OS work. Load it from `/home/workdir/.grok/skills/obzue-product-forge` in Grok.

## Limits

- iframes cannot display most third-party sites
- no silent control of Windows, macOS, Android, or iOS
- no claim of sentience
