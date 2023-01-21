---
layout: default
title: Config
nav_order: 3
---

# Configuring qb-burglary (config.lua)

Open the main config file (config.lua) and make sure the required resource names are the same as the resources on your server

![image](https://user-images.githubusercontent.com/123037761/213881742-2261f909-2291-47af-b9dc-8b0d14d0561d.png)

{: .note }
If you have not renamed your server resources, you do not need to change the resource names shown in the image above

## Changing the minigame

You can change the minigame for breaking in, disabling the security and cracking safes in the main config

```
-- Minigame for breaking in

- circle
- ps-circle
- square
- lockpick

Config.DoorSkillcheck = "lockpick"

-- Minigame for disabling the security
Config.SecuritySkillcheck = "square"

-- Minigame for cracking the safe
Config.SafeSkillcheck = "square"
```

