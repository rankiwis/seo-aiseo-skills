# Start here

This folder has **26 `.skill` files**. Each one is a complete skill, ready to add to Claude.

Do not rename them. Do not unzip them. Claude wants the `.skill` file as it is.

---

## Add a skill to Claude

1. Open Claude.
2. In the sidebar, open **Customize**, then **Skills**.
   *(On some versions this is **Settings → Capabilities → Skills**.)*
3. Click **Add skill**, then **Upload a skill**.
4. Pick one of the `.skill` files in this folder.
5. Turn it on.
6. Repeat for any others you want.

You do not need all 26. Four good ones to start with:

- `seo-technical-audit.skill`
- `seo-google.skill`
- `aiseo-share-of-voice.skill`
- `seo-content-brief.skill`

Add the rest whenever you need them.

---

## Claude Code or Cowork

Claude Code reads folders, not `.skill` files. A `.skill` file is just a zip, so you can unzip it straight in.

**Mac or Linux:**

```bash
mkdir -p ~/.claude/skills
for f in *.skill; do unzip -o -q "$f" -d ~/.claude/skills/; done
```

**Windows PowerShell:**

```powershell
New-Item -ItemType Directory -Force -Path "$HOME\.claude\skills"
Get-ChildItem *.skill | ForEach-Object {
  Copy-Item $_.FullName "$($_.FullName).zip"
  Expand-Archive "$($_.FullName).zip" -DestinationPath "$HOME\.claude\skills" -Force
  Remove-Item "$($_.FullName).zip"
}
```

Use `.claude/skills` instead of `~/.claude/skills` if you only want them in one project.

Restart Claude Code. Type `/skills` to check.

---

## Check it worked

Ask Claude:

```
Which SEO skills do you have available?
```

You should get the list back.

---

## Then just ask

You never type a skill name. Ask in normal words and Claude picks the right one.

```
Run a technical audit on example.com
```
```
Am I showing up in ChatGPT for project management questions?
```
```
Build me a brief for "best crm for small business"
```

---

## Want to edit one?

A `.skill` file is a zip with one folder inside it.

1. Rename `seo-technical-audit.skill` to `seo-technical-audit.zip`
2. Unzip it
3. Open `SKILL.md` and change whatever you want
4. Zip the **folder** back up
5. Rename the zip back to `.skill`
6. Upload it again

The folder has to sit at the top of the zip, like this:

```
seo-technical-audit.skill
  └── seo-technical-audit/
        └── SKILL.md
```

If you zip `SKILL.md` on its own, it will not load.

---

See `SKILLS-LIST.md` for what all 26 do.
