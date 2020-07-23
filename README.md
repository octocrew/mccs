# mccs

This is to keep track of changes in the Octocrew Public Minecraft Community Server.

View [CHANGELOG.md](https://github.com/octocrew/mccs/blob/master/CHANGELOG.md) to view a history of all changes.

View [Trello](https://trello.com/b/ZgXfkbsV/octocrew-public-minecraft-community-server) to see the current progress of changes.

- Anything with a `#` is a comment that usually indicates the default setting.
- Settings for Plugins, Datapacks, and other things are listed under "Currently Modified Settings or State".

---

## Plugins

- [Grief Prevention](https://www.spigotmc.org/resources/griefprevention.1884/)
  - Allows users to create claims to protect their builds.
  - Everything inside the claim can not be destroyed by players without `/trust`.
  - Claim owner can give varying levels of claim access/trust.
- [Core Protect](https://www.spigotmc.org/resources/coreprotect.8631/)
  - Logs actions in game (blocks, chests, etc.) and allows rollback/recovery to varying degrees.
  - Currently used for:
    - Rollback on blocks due to cheaters but not due to griefing, as long as it doesn't rollback other users' progress.
    - Identifying who may have cheated due to x-ray or other cheats. 
- [LuckPerms](https://www.spigotmc.org/resources/luckperms.28140/)
  - Allows admins to manage command permissions.
- [HomeSpawn](https://www.spigotmc.org/resources/homespawn.14108/)
  - Allows a user to teleport to their home using the `/home [name]` command.
  - Allows a user to teleport to spawn using the `/spawn` command.

## Datapacks

- [Craftable Shulker Shells: "Shulker Shell Shuffle"](https://www.curseforge.com/minecraft/customization/shulker-shell-shuffle)
  - Makes endermen drop chorus fruit
  - Adds recipe for shulker shells by using popped chorus fruit in a helmet pattern
  - Adds recipe for one ender pearl from a one chorus fruit
  - Recipes are added to the recipe book
- [Multiplayer Precentage Sleeping System](https://github.com/Plagiatus/datapacks/tree/master/multiplayer_sleep)
  - Allows a percentage of users to sleep instead of all players.
  - Rounds down (for example: 5 players online with 50% sleep only requires 2 to sleep).
  - Clear the weather for 999,999 seconds every time night is skipped (Not normal behavior. Can be changed back to normal behavior.).
  - Does **not** interfere with the phatnom timer.
  - Only considers players in the overworld for sleep.
  - Adds to time instead of resetting it to help with in-game days/time played.
- [Dragon Drops](https://vanillatweaks.net/picker/datapacks/)
  - Makes the ender dragon drop a dragon egg and elytra on every death.
- [Double Shulker Shells](https://vanillatweaks.net/picker/datapacks/)
  - Makes all shulkers drop two shells.

## Currently Modified Settings or State

General World State
```yml
World Spawn: -37, 74, -510
World Border: -12500, -12500 to 12500, 12500
```

### Minecraft

server.properties
```yml
sync-chunk-writes: false
player-idle-timeout: 30 # 15
difficulty: hard # normal
pvp: true
max-players: 100 # 10
max-world-size: 12500 # 29999984
function-permission-level: 3 # 4
view-distance: 10 # 10
motd: Octorew Community Server
```

### Grief Prevention

config.yml
```yml
GriefPrevention:
  Claims:
    Claim Tool: WOODEN_SHOVEL # GOLDEN_SHOVEL
    InitialBlocks: 2304 # 100
    Claim Blocks Accrued Per Hour: 10 # 100
    Max Accrued Claim Blocks: 4608 # 2000
    AutomaticNewPlayerClaimsRadius: 7 # 4
    ModificationTool: WOODEN_SHOVEL # GOLDEN_SHOVEL
  FireSpreads: true
  FireDestroys: true
  MaxPlayersPerIpAddress: 5 # 3
  EndermenMoveBlocks: true
  SilverfishBreakBlocks: true
  CreaturesTrampleCrops: true
  HardModeZombiesBreakDoors: true
  Administrative Activity: true
  Muted Chat Messages: true
  AdminsGetSignNotifications: false
```

messages.yml
```yml
Messages:
  UnprotectedChestWarning:
    Text: This chest is NOT protected.  Consider using a wooden shovel to expand an
      existing claim or to create a new one. # Default: "golden shovel"
  MustHoldModificationToolForThat:
    Text: You must be holding a wooden shovel to do that. # Default: "golden shovel"
  RadiusRequiresGoldenShovel:
    Text: You must be holding a wooden shovel when specifying a radius. # Default: "golden shovel"
```

### HomeSpawn

config.yml
```yml
Permissions:
  homespawn,player:
    Homes: 2 # 1
  homespawn,vip:
    Homes: 2 # 5
    TeleportDelay: 10 # 5
  homespawn,admin:
    Homes: 2 # 10
    TeleportDelay: 10 # 0
```
