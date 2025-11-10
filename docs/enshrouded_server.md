# Enshrouded Server Configuration



This document includes:



- General server settings
- Gameplay settings (ordered as in the config file)
- User group permissions
- [Example enshrouded_server.json](../ressources/enshrouded_server.json)


---



## General Server Settings



| Setting            | Description                                | Example / Default Value | Options / Notes          |
|--------------------|--------------------------------------------|--------------------------|---------------------------|
| **name**           | Name of the server                         | "Enshrouded Server"      | Any string                |
| **saveDirectory**  | Directory where savegames are stored       | "./savegame"             | File path                 |
| **logDirectory**   | Directory for log files                    | "./logs"                 | File path                 |
| **ip**             | Server IP binding                          | "0.0.0.0"                | Server IP address         |
| **queryPort**      | Port used for server queries               | 15637                    | Integer                   |
| **slotCount**      | Max number of players                      | 16                       | Integer                   |
| **tags**           | Optional server browser tags               | []                       | e.g., "LookingForPlayers", "Roleplay", language codes |
| **voiceChatMode**  | Voice chat type                            | Proximity                | Proximity / Global        |
| **enableVoiceChat**| Enable/disable voice chat                  | false                    | true / false              |
| **enableTextChat** | Enable/disable text chat                   | false                    | true / false              |
| **gameSettingsPreset** | Preset for gameplay settings           | Default                  | Default / Relaxed / Hard / Survival / Custom |

### Difficulty Presets Explanation



- **Default** – This is the standard difficulty, matching Enshrouded’s settings prior to update 0.7.3.0. Recommended for new players.
- **Relaxed** – Fewer enemies, more resources and loot. Ideal for builders and casual adventurers.
- **Hard** – Increased enemy count and aggression. Offers a greater combat challenge.
- **Survival** – For players wanting a punishing experience. Adds survival mechanics and aggressive enemies.
- **Custom** – Allows full control over all individual gameplay settings.



---



## Gameplay Settings (Ordered by Config)



| Setting                          | Description                                              | Default Value          | Min                  | Max                  | Options / Notes                                              |
|----------------------------------|----------------------------------------------------------|------------------------|----------------------|----------------------|--------------------------------------------------------------|
| **playerHealthFactor**           | Scales player max health                                 | 1                      | 0.25                 | 4                    | Percentage factor shown in-game                              |
| **playerManaFactor**             | Scales player max mana                                   | 1                      | 0.25                 | 4                    |                                                              |
| **playerStaminaFactor**          | Scales player max stamina                                | 1                      | 0.25                 | 4                    |                                                              |
| **playerBodyHeatFactor**         | Adjusts cold resistance/body heat pool                   | 1                      | 0.5                  | 2                    | Allowed values: 0.5 / 1 / 1.5 / 2                            |
| **playerDivingTimeFactor**       | Sets starting oxygen for swimming and diving             | 1                      | 0.5                  | 2                    | Higher values provide more underwater time                   |
| **enableDurability**             | Weapon/tool durability enabled                           | true                   | -                    | -                    | true / false                                                 |
| **enableStarvingDebuff**         | Enables hunger / starvation damage                       | false                  | -                    | -                    | true / false                                                 |
| **foodBuffDurationFactor**       | Multiplies food buff durations                           | 1                      | 0.5                  | 2                    |                                                              |
| **fromHungerToStarving**         | Hungry-state length before starvation (ns)               | 600000000000 (10 min)  | 300000000000 (5 min) | 1200000000000 (20 min) | Nanoseconds; convert to minutes for readability              |
| **shroudTimeFactor**             | Time permitted within the Shroud                         | 1                      | 0.5                  | 2                    |                                                              |
| **tombstoneMode**                | Items lost on death                                      | AddBackpackMaterials   | -                    | -                    | AddBackpackMaterials / Everything / NoTombstone              |
| **enableGliderTurbulences**      | Enables glider turbulence                                | true                   | -                    | -                    | true / false                                                 |
| **weatherFrequency**             | Frequency of dynamic weather events                      | Normal                 | -                    | -                    | Disabled / Rare / Normal / Often                             |
| **fishingDifficulty**            | Strength of fish during the mini-game                    | Normal                 | -                    | -                    | VeryEasy / Easy / Normal / Hard / VeryHard                   |
| **miningDamageFactor**           | Mining damage and terraforming speed                     | 1                      | 0.5                  | 2                    |                                                              |
| **plantGrowthSpeedFactor**       | Growth speed for crops                                   | 1                      | 0.25                 | 2                    |                                                              |
| **resourceDropStackAmountFactor**| Materials per loot stack                                 | 1                      | 0.25                 | 2                    |                                                              |
| **factoryProductionSpeedFactor** | Workstation production times                             | 1                      | 0.25                 | 2                    | Higher values reduce crafting duration                       |
| **perkUpgradeRecyclingFactor**   | Rune refund when salvaging upgraded weapons              | 0.5                    | 0                    | 1                    |                                                              |
| **perkCostFactor**               | Rune cost multiplier for weapon upgrades                 | 1                      | 0.25                 | 2                    |                                                              |
| **experienceCombatFactor**       | XP gained from combat                                    | 1                      | 0.25                 | 2                    |                                                              |
| **experienceMiningFactor**       | XP gained from mining                                    | 1                      | 0                    | 2                    |                                                              |
| **experienceExplorationQuestsFactor** | XP gained from exploration and quests             | 1                      | 0.25                 | 2                    |                                                              |
| **randomSpawnerAmount**          | Ambient enemy density                                    | Normal                 | -                    | -                    | Few / Normal / Many / Extreme                                |
| **aggroPoolAmount**              | Simultaneous attackers allowed                           | Normal                 | -                    | -                    | Few / Normal / Many / Extreme                                |
| **enemyDamageFactor**            | Non-boss enemy damage                                    | 1                      | 0.25                 | 5                    |                                                              |
| **enemyHealthFactor**            | Non-boss enemy health                                    | 1                      | 0.25                 | 4                    |                                                              |
| **enemyStaminaFactor**           | Non-boss stamina / stagger resistance                    | 1                      | 0.5                  | 2                    | Higher values make enemies harder to stagger                 |
| **enemyPerceptionRangeFactor**   | Non-boss perception range                                | 1                      | 0.5                  | 2                    |                                                              |
| **bossDamageFactor**             | Boss damage                                              | 1                      | 0.2                  | 5                    |                                                              |
| **bossHealthFactor**             | Boss health                                              | 1                      | 0.2                  | 5                    |                                                              |
| **threatBonus**                  | Frequency of enemy attacks                               | 1                      | 0.25                 | 4                    |                                                              |
| **pacifyAllEnemies**             | Enemies attack only when provoked (excl. bosses)         | false                  | -                    | -                    | true / false                                                 |
| **tamingStartleRepercussion**    | Progress lost when startling wildlife during taming      | LoseSomeProgress       | -                    | -                    | KeepProgress / LoseSomeProgress / LoseAllProgress            |
| **dayTimeDuration**              | Daytime length (ns)                                      | 1800000000000 (30 min) | 120000000000 (2 min) | 3600000000000 (60 min) | Smaller values shorten daytime                               |
| **nightTimeDuration**            | Nighttime length (ns)                                    | 720000000000 (12 min)  | 120000000000 (2 min) | 3600000000000 (60 min) | Smaller values shorten nighttime                             |
| **curseModifier**                | Shroud curse chance                                      | Normal                 | -                    | -                    | Easy (off) / Normal / Hard (double chance)                   |

*Time-based values (e.g., `fromHungerToStarving`, `dayTimeDuration`, `nightTimeDuration`) are stored in nanoseconds. Divide by 60,000,000,000 to convert to minutes.*



---



## User Groups & Permissions



### User Group Fields



| Field                | Description                                                           | Type    | Example Value     | Options / Notes                      |
|----------------------|-----------------------------------------------------------------------|---------|--------------------|--------------------------------------|
| **name**             | Name of the user group                                                | String  | "Admin"            | Arbitrary group name                 |
| **password**         | Password required to join the group                                   | String  | "AdminXXXXXXXX"    | Keep secure                          |
| **canKickBan**       | Permission to kick/ban players                                        | Boolean | true               | true / false                         |
| **canAccessInventories** | Permission to access other players' inventories                 | Boolean | true               | true / false                         |
| **canEditWorld**     | Allow terraforming / interactions outside bases                       | Boolean | true               | true / false                         |
| **canEditBase**      | Permission to edit any base                                           | Boolean | true               | true / false                         |
| **canExtendBase**    | Permission to extend base territory                                   | Boolean | true               | true / false                         |
| **reservedSlots**    | Reserved player slots for that group                                  | Int     | 0                  | Number of reserved slots             |

---



### Defined User Groups



Enshrouded ships with four predefined user groups—**Admin**, **Friend**, **Guest**, and **Visitor**—each with distinct permissions that you can fine-tune with custom passwords.



| Group Name | Password          | Can Kick/Ban | Access Inventories | Can Edit World | Edit Base | Extend Base | Reserved Slots |
|------------|-------------------|--------------|--------------------|----------------|-----------|-------------|----------------|
| **Admin**  | AdminXXXXXXXX     | ✅           | ✅                 | ✅             | ✅        | ✅          | 0              |
| **Friend** | FriendXXXXXXXX    | ❌           | ✅                 | ✅             | ✅        | ❌          | 0              |
| **Guest**  | GuestXXXXXXXX     | ❌           | ❌                 | ✅             | ❌        | ❌          | 0              |
| **Visitor**| VisitorXXXXXXXX   | ❌           | ❌                 | ❌             | ❌        | ❌          | 0              |

### Role Descriptions



- **Admin**: Full administrative privileges, including kick/ban powers, inventory access, world terraforming, and unrestricted base edits or extensions.
- **Friend**: Trusted players who may terraform the world and build inside the base but cannot kick/ban other players or extend the base claim.
- **Guest**: Adventurers who can explore and interact with the world while keeping inventories and bases protected from accidental edits.
- **Visitor**: A safe default role that cannot terraform outside the base, edit builds, or access other inventories—ideal for open community servers.



### Ban List



The `bans` array stores permanently banned player IDs. Leave it empty for open servers; entries are added automatically when you ban someone via the admin tools.



For official documentation, see: [Enshrouded Server Gameplay Settings](https://enshrouded.zendesk.com/hc/en-us/articles/20453241249821-Server-Gameplay-Settings)


