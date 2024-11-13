---
title: Bypass Transparency Filter
published: 2024-11-13
description: ''
image: ''
tags: [Zenless Zone Zero, Mod]
category: 'ZZZ Mod'
draft: false 
lang: ''
---

You may notice a warning about the file being "Executable" because there is a .bin file inside the zip. I want to assure you that it does not contain any viruses, and the bin file was included to resolve the freezing issue.

I recommend using RabbitFX(https://gamebanana.com/mods/531649) instead, as it includes a feature to bypass transparency. Maintaining my mod has become challenging, so it may eventually become obsolete.

This mod removes the character becoming transparent and fading away when you get close to them.

Prerequisite tools needed to use the mod: Zenless Zone Zero 3dmigoto (ZZMI, XXMI, etc).

Installation: Move all "...-ps_replace.txt" and "...-ps_replace.bin" files inside the ShaderFixes folder to your ShaderFixes folder. Then restart the game.

To uninstall:  Manually remove all files that you put in when installing the mod from your ShaderFixes folder.

You can remove the mod using a PowerShell script.

Open PowerShell, navigate to the ShaderFixes folder, and paste the following command:
# Loop through all .txt files in the current directory

```powershell
Get-ChildItem *.txt | ForEach-Object {
    # Check if the file contains the phrase "Bypass Transparency Filter"
    if (Select-String -Path $_.FullName -Pattern "Bypass Transparency Filter") {
        # Delete the .txt file
        Remove-Item -Path $_.FullName -Force
        # Delete the corresponding .bin file with the same name (without extension)
        $binFile = $_.FullName.Replace('.txt', '.bin')
        Remove-Item -Path $binFile -Force -ErrorAction SilentlyContinue
    }
}
```

Please let me know if there are any situations where this mod does not work correctly.