# Enshrouded Server Configuration

This document includes:

- General server settings
- Gameplay settings (ordered as in the config file)
- User group permissions
- [Example enshrouded_server.json](https://github.com/bonsaibauer/enshrouded_server_ubuntu/blob/main/enshrouded_server.json)

---

## General Server Settings

| Setting            | Description                                | Example / Default Value | Options / Notes          |
|--------------------|--------------------------------------------|--------------------------|---------------------------|
| **name**           | Name of the server                         | "Enshrouded Server"      | Any string                |
| **saveDirectory**  | Directory where savegames are stored       | "./savegame"             | File path                 |
| **logDirectory**   | Directory for log files                    | "./logs"                 | File path                 |
| **ip**             | Server IP binding                          | "0.0.0.0"                | Server ip adress          |
| **queryPort**      | Port used for server queries               | 15637                    | Integer                   |
| **slotCount**      | Max number of players                      | 16                       | Integer                   |
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

| Setting                          | Description                                              | Default Value        | Min        | Max        | Options / Notes                                              |
|----------------------------------|----------------------------------------------------------|----------------------|------------|------------|--------------------------------------------------------------|
| **playerHealthFactor**           | Player health scale                                      | 1                    | 0.25       | 4          |                                                              |
| **playerManaFactor**             | Player mana scale                                        | 1                    | 0.25       | 4          |                                                              |
| **playerStaminaFactor**          | Player stamina scale                                     | 1                    | 0.25       | 4          |                                                              |
| **playerBodyHeatFactor**         | Cold resistance scale                                    | 1                    | 0.5        | 2          |                                                              |
| **enableDurability**             | Weapon/tool durability enabled                           | true                 | –          | –          | true / false                                                 |
| **enableStarvingDebuff**         | Starving debuff enabled                                  | false                | –          | –          | true / false                                                 |
| **foodBuffDurationFactor**       | Food buff duration scale                                 | 1                    | 0.5        | 2          |                                                              |
| **fromHungerToStarving**         | Time until starving (ns)                                 | 600000000000         | 300B       | 1200B      | e.g., 10 mins                                                |
| **shroudTimeFactor**             | Time in shroud scale                                     | 1                    | 0.5        | 2          |                                                              |
| **tombstoneMode**                | Loot drop on death                                       | AddBackpackMaterials | –          | –          | AddBackpackMaterials / Everything / NoTombstone              |
| **enableGliderTurbulences**      | Glider turbulence enabled                                | true                 | –          | –          | true / false                                                 |
| **weatherFrequency**             | Weather frequency                                        | Normal               | –          | –          | Disabled / Rare / Normal / Often                             |
| **miningDamageFactor**           | Mining yield scale                                       | 1                    | 0.5        | 2          |                                                              |
| **plantGrowthSpeedFactor**       | Plant growth speed scale                                 | 1                    | 0.25       | 2          |                                                              |
| **resourceDropStackAmountFactor**| Resource stack size scale                                | 1                    | 0.25       | 2          |                                                              |
| **factoryProductionSpeedFactor** | Factory production speed scale                           | 1                    | 0.25       | 2          |                                                              |
| **perkUpgradeRecyclingFactor**   | Rune refund factor from recycling                        | 0.5                  | 0          | 1          |                                                              |
| **perkCostFactor**               | Rune upgrade cost factor                                 | 1                    | 0.25       | 2          |                                                              |
| **experienceCombatFactor**       | XP gain from combat                                      | 1                    | 0.25       | 2          |                                                              |
| **experienceMiningFactor**       | XP gain from mining                                      | 1                    | 0          | 2          |                                                              |
| **experienceExplorationQuestsFactor** | XP gain from quests/exploration                     | 1                    | 0.25       | 2          |                                                              |
| **randomSpawnerAmount**          | Enemy spawn amount                                       | Normal               | –          | –          | Few / Normal / Many / Extreme                                |
| **aggroPoolAmount**              | Number of enemies that can aggro                         | Normal               | –          | –          | Few / Normal / Many / Extreme                                |
| **enemyDamageFactor**            | Enemy (non-boss) damage scale                            | 1                    | 0.25       | 5          |                                                              |
| **enemyHealthFactor**            | Enemy (non-boss) health scale                            | 1                    | 0.25       | 4          |                                                              |
| **enemyStaminaFactor**           | Enemy (non-boss) stamina resistance                      | 1                    | 0.5        | 2          |                                                              |
| **enemyPerceptionRangeFactor**   | Enemy (non-boss) perception range                        | 1                    | 0.5        | 2          |                                                              |
| **bossDamageFactor**             | Boss damage scale                                        | 1                    | 0.2        | 5          |                                                              |
| **bossHealthFactor**             | Boss health scale                                        | 1                    | 0.2        | 5          |                                                              |
| **threatBonus**                  | Frequency of enemy attacks                               | 1                    | 0.25       | 4          |                                                              |
| **pacifyAllEnemies**             | Enemies only attack when provoked (except bosses)        | false                | –          | –          | true / false                                                 |
| **tamingStartleRepercussion**    | Reaction when taming animal is startled                  | LoseSomeProgress     | –          | –          | KeepProgress / LoseSomeProgress / LoseAllProgress            |
| **dayTimeDuration**              | Length of day (ns)                                       | 1800000000000        | 120B       | 3600B      | e.g., 30 mins                                                |
| **nightTimeDuration**            | Length of night (ns)                                     | 720000000000         | 120B       | 3600B      | e.g., 12 mins                                                |

*Note:* Time values are in nanoseconds. Divide by 60,000,000,000 to convert to minutes.

---

## User Groups & Permissions

### User Group Fields

| Field                | Description                                                           | Type    | Example Value     | Options / Notes                      |
|----------------------|-----------------------------------------------------------------------|---------|--------------------|--------------------------------------|
| **name**             | Name of the user group                                                | String  | "Admin"            | Arbitrary group name                 |
| **password**         | Password required to join the group                                   | String  | "AdminXXXXXXXX"    | Keep secure                          |
| **canKickBan**       | Permission to kick/ban players                                        | Boolean | true               | true / false                         |
| **canAccessInventories** | Permission to access other players' inventories                 | Boolean | true               | true / false                         |
| **canEditBase**      | Permission to edit any base                                           | Boolean | true               | true / false                         |
| **canExtendBase**    | Permission to extend base territory                                   | Boolean | true               | true / false                         |
| **reservedSlots**    | Reserved player slots for that group                                  | Int     | 0                  | Number of reserved slots             |

---

### Defined User Groups
Enshrouded supports three predefined user groups: **Admin**, **Friend**, and **Guest**. Each group has distinct permissions, and hosts can assign passwords to control access.

| Group Name | Password          | Can Kick/Ban | Access Inventories | Edit Base | Extend Base | Reserved Slots |
|------------|-------------------|--------------|--------------------|-----------|-------------|----------------|
| **Admin**  | AdminXXXXXXXX     | ✅           | ✅                 | ✅        | ✅          | 0              |
| **Friend** | FriendXXXXXXXX    | ❌           | ✅                 | ✅        | ❌          | 0              |
| **Guest**  | GuestXXXXXXXX     | ❌           | ❌                 | ❌        | ❌          | 0              |

### Role Descriptions

- **Admin**: Full administrative privileges, including the ability to kick or ban players, access all inventories, and modify or extend the base.
- **Friend**: Trusted players who can access inventories and edit the base but cannot kick/ban players or extend the base.
- **Guest**: Limited access; cannot kick/ban players, access inventories, or modify the base.


---

For official documentation, see: [Enshrouded Server Gameplay Settings](https://enshrouded.zendesk.com/hc/en-us/articles/20453241249821-Server-Gameplay-Settings)
