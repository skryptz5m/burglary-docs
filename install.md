---
layout: default
title: Installing
nav_order: 2
---

# Installing qb-burglary

## Add qb-burglary to your resource folder
It is recommended that you add qb-burglary to the [qb] folder

## Add the inventory images
These images can be found in the images folder qb-burglary

Take the provided images and add them to your qb-inventory images folder, qb-inventory -> html -> images

## Required items
> TV prop item
```
['bigtv'] 				 	     = {['name'] = 'bigtv', 			  	  		['label'] = 'TV', 						['weight'] = 70000, 	['type'] = 'item', 		['image'] = 'stolentv.png', 			['unique'] = true, 		['useable'] = true, 	['shouldClose'] = true,	   ['combinable'] = nil,   ['description'] = 'Definitely not stolen'},
```
> PC prop item
```
['computer'] 				 	 = {['name'] = 'computer', 			  	  		['label'] = 'Computer', 				['weight'] = 70000, 	['type'] = 'item', 		['image'] = 'stolencomputer.png', 		['unique'] = true, 		['useable'] = true, 	['shouldClose'] = true,	   ['combinable'] = nil,   ['description'] = 'Definitely not stolen'},
```
> Microwave prop item
```
['microwave'] 				 	 = {['name'] = 'microwave', 			  	  	['label'] = 'Microwave', 				['weight'] = 70000, 	['type'] = 'item', 		['image'] = 'stolenmicro.png', 			['unique'] = true, 		['useable'] = true, 	['shouldClose'] = true,	   ['combinable'] = nil,   ['description'] = 'Definitely not stolen'},
```
> Stereo prop item
```
['stereo'] 				 	     = {['name'] = 'stereo', 			  	  		['label'] = 'HIFI', 					['weight'] = 70000, 	['type'] = 'item', 		['image'] = 'stolenstereo.png', 		['unique'] = true, 		['useable'] = true, 	['shouldClose'] = true,	   ['combinable'] = nil,   ['description'] = 'Definitely not stolen'},
```

> T1 safe key item
```
['t1_safe_key'] 			 	 = {['name'] = 't1_safe_key', 			 		['label'] = 'Key', 		['weight'] = 500, 		['type'] = 'item', 		['image'] = 'safe_key.png', 			['unique'] = true, 		['useable'] = false, 	['shouldClose'] = true,	   ['combinable'] = nil,   ['description'] = 'Probably unlocks something'},
```
> T2 safe key item
```
['t2_safe_key'] 			 	 = {['name'] = 't2_safe_key', 			 		['label'] = 'Key', 		['weight'] = 500, 		['type'] = 'item', 		['image'] = 'safe_key.png', 			['unique'] = true, 		['useable'] = false, 	['shouldClose'] = true,	   ['combinable'] = nil,   ['description'] = 'Probably unlocks something'},
```
> T3 safe key item
```
['t3_safe_key'] 			 	 = {['name'] = 't3_safe_key', 			 		['label'] = 'Key', 		['weight'] = 500, 		['type'] = 'item', 		['image'] = 'safe_key.png', 			['unique'] = true, 		['useable'] = false, 	['shouldClose'] = true,	   ['combinable'] = nil,   ['description'] = 'Probably unlocks something'},
```

You must add all of the items above to your item list, qb-core -> shared -> items.lua or shared.lua

## Enabling XP/Levels
You can find the boss_reputation.sql file in the qb-burglary folder

You must add the boss_reputation table to your database, you can do this by importing the "boss_reputation.sql" file


