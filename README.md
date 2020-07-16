# mccs

This is to keep track of changes in the Octocrew Public Minecraft Community Server.

View [CHANGELOG.md](https://github.com/octocrew/mccs/blob/master/CHANGELOG.md) to view a history of all changes.

Anything with a `#` is a comment that usually indicates the default setting.

---

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
