This repo has [reference assemblies](https://learn.microsoft.com/en-us/dotnet/standard/assembly/reference-assemblies)
used to build [SMAPI](https://github.com/Pathoschild/SMAPI) and Stardew Valley mods without a game
install (e.g. for automated CI pipelines).

The current assemblies are based on:
- Stardew Valley 1.6.15
- SMAPI 4.4.0

## For maintainers
To update the repo:
1. Install [Refasmer](https://github.com/JetBrains/Refasmer).
2. Open a terminal in [your game folder](https://stardewvalleywiki.com/Modding:Game_folder).
3. Run these commands:
   ```sh
   refasmer -O ref-assemblies/ -c --all `
      BmFont.dll `
      CPExtBmFont.dll `
      GalaxyCSharp.dll `
      Lidgren.Network.dll `
      MonoGame.Framework.dll `
      SkiaSharp.dll `
      StardewModdingAPI.dll `
      "Stardew Valley.dll" `
      StardewValley.GameData.dll `
      xTile.dll
   refasmer -O ref-assemblies/smapi-internal/ -c --all `
      smapi-internal/0Harmony.dll `
      smapi-internal/Newtonsoft.Json.dll `
      smapi-internal/SMAPI.Toolkit.dll `
      smapi-internal/SMAPI.Toolkit.CoreInterfaces.dll `
      smapi-internal/TMXTile.dll
   ```
4. Move the files from the `ref-assemblies` folder into the repo.
