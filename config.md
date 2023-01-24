---
layout: default
title: Config
nav_order: 3
---

# Configuring qb-burglary (config.lua)

Open the main config file (config.lua) and make sure the required resource names are the same as the resources on your server

```
-- If you have renamed your QBCore object replace "QBCore" with the name of your core
Config.CoreObjectName = "QBCore"

-- exports[Config.CoreResourceName]:GetCoreObject()
Config.CoreResourceName = "qb-core"

-- exports[TargetResourceName]:AddZone
Config.TargetResourceName = "qb-target"

-- exports[Config.MenuResourceName]:openMenu
Config.MenuResourceName = "qb-menu"

-- TriggerEvent(Config.LockpickResourceName..':client:openLockpick')
Config.LockpickResourceName = "qb-lockpick"
```

{: .note }
If you have not renamed your server resources, you do not need to change the resource names shown in the code block above.

## Changing the minigame

You can change the minigame for breaking in, disabling the security and cracking safes in the main config

```
-- Set the skill check minigame for lockpicking a door
Config.DoorSkillcheck = "lockpick"

-- Set the skill check minigame for disabling the security
Config.SecuritySkillcheck = "square"

-- Set the skill check minigame for cracking the safe
Config.SafeSkillcheck = "square"
```

### Current minigames for Config.DoorSkillcheck
- "circle" - https://github.com/Nathan-FiveM/qb-lock
- "ps-circle" - https://github.com/Project-Sloth/ps-ui
- "square" - https://github.com/qbcore-framework/qb-skillbar
- "lockpick" - https://github.com/qbcore-framework/qb-lockpick

### Current minigames for Config.SecuritySkillcheck
- "circle" - https://github.com/Nathan-FiveM/qb-lock
- "ps-circle" - https://github.com/Project-Sloth/ps-ui
- "ps-scrambler" - https://github.com/Project-Sloth/ps-ui
- "square" - https://github.com/qbcore-framework/qb-skillbar

### Current minigames for Config.SafeSkillcheck
- "circle" - https://github.com/Nathan-FiveM/qb-lock
- "ps-circle" - https://github.com/Project-Sloth/ps-ui
- "square" - https://github.com/qbcore-framework/qb-skillbar

## Adding a minigame

The events for these minigames can be found cl_public.lua. You can modify these events or add a new event for your own minigame.

![image](https://user-images.githubusercontent.com/123037761/213883117-18dff52b-6b01-4669-8166-c3e59cf83161.png)

The minigame events shown above are handled by these functions, also in cl_public.lua.

![image](https://user-images.githubusercontent.com/123037761/213883202-219972bd-1690-4a09-9c74-766907438ced.png)

## Breaking in time

You can change the time period for robbing houses in the main config. You will not be able to start the break in minigame if it is too early.

```
-- Example: if the time is 5AM or later you cannot break in
Config.MinTime = 5

-- Example: if the time is 11PM or later you can break in
Config.MaxTime = 23
```

You can completely remove the time check from the minigame events in cl_public.lua. Look for the events shown in the adding a minigame section above.

## Queue and finish time

You can set how long it takes to receive a job offer (seconds) in the main config

```
-- Set how long it takes for the player to receive a job (seconds)
Config.JobWaitTime = { 285, 345 } -- [1] = min seconds, [2] = max seconds
```

You can set how long the player has to complete the job (seconds)

```
-- Set how long the player has to complete the job after entry (seconds)
Config.JobTime = { 325, 385 } -- [1] = min seconds, [2] = max seconds

```

If you leave the house after it has expired the job will end

## Using phone mail

If enabled you will receive job offers and information via the phone mail app.

```
-- If true the player will be emailed a job offer using qb-phone, the offer must be accepted
-- If false the player will be notified via QB.Notify or the notify resource you are using
Config.QbPhoneMail = true
```

You can change the phone events used for sending mail in cl_public.lua.

```
--- Send job offer via mail qb-phone
--- @param tier integer
function SendJobMail(tier)
    TriggerServerEvent("qb-phone:server:sendNewMail", {
        sender = "Bossman",
        subject = "T"..tier.." ".."job offer",
        message = Config.Prompts["requested3"],
        button = 
        {                    
            enabled = true,
            buttonEvent = "burglary:client:AcceptHouse",
            buttonData = tier
        }
    })
end

--- Send job info via mail qb-phone
--- @param message string
--- @param subject string
function SendMail(message, subject)
    TriggerServerEvent("qb-phone:server:sendNewMail", {
        sender = "Bossman",
        subject = subject,
        message = message,
        button = {}
    })
end
```

