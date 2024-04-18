# UE5-RPD-Project
## FPS-Style Game based on RE2 inside the RPD using Unreal Engine 5.3.2 and ALS

This is a project that I'm doing in my **free time** to try out the possibilities of Unreal Engine 5 for the first time, it's not certain that the project will be 100% finished, but over time I'll make changes to progress the development.

# Some Features That i already have implemented/modified:

## ALS Fully Retargeted to Leon's Mesh
![Sequence 01](https://github.com/DUDUKorte/UE5-RPD-Project/assets/40546705/0d674464-db0e-4b47-aa7d-21247838c611)

## ALS States and Features Fully Configured to the desired project
![Sequence 01](https://github.com/DUDUKorte/UE5-RPD-Project/assets/40546705/d5ef116c-ab63-48fa-9f3f-a7e7ac9e3c98)
* Always in FPP
* You can only walk or run, not spint
* The maximum Mantle height is 1M
* You cant jump manually
* Always with 2H Pistol

## 2 States with the pistol and a new one: 2H Pistol and injured + 2H pistol
![Sequence 01](https://github.com/DUDUKorte/UE5-RPD-Project/assets/40546705/4d9168ae-fce5-427a-8701-46dd0c3797c3)
* Default Overlay State is 2H Pistol
* Created new overlay state with 2H Pistol + Injured
* You can aim with 2H even if you are injured
> OBS: Is in TPP just to show the states

## Pickup with prximity icon (i will remake this feature with a new inventory system to both work together)
![Sequence 01](https://github.com/DUDUKorte/UE5-RPD-Project/assets/40546705/f0009604-515e-44ef-91d1-4b1d7befb276)
* Using Line Trace by Channel inside player's BP
> OBS: I will remake this feature with the inventory component, will be better

## Inventory System (Still WIP)
![Sequence 01](https://github.com/DUDUKorte/UE5-RPD-Project/assets/40546705/93f62c90-c682-4069-93ac-412ae24d2e94)
* Add the items to the inventory up to the maximum size
> WIP: Drag and drop Widget

> WIP: Use the items

> WIP: Ammo works with the weapon

> WIP: More Actions with the items (Inspect, Discard, Equip...)

## Enemy AI That follow the player when he's close and stop when exit the area
![Sequence 01](https://github.com/DUDUKorte/UE5-RPD-Project/assets/40546705/eeb5a277-1f09-4ada-b04e-d7308ef45c1d)
* The Line Trace Red check the distance between the enemy and the player, when he is close it turns purple
* If the player Run away from the distance limit, the enemy will stop following him
* If the player leave the AI Navigation Area, thw enemy will stop following as well

> For a better optimization, the line trace check is through the tick event inside the AI controller

> When Get True, the AI Controller Broadcasts an event to change the behaviour tree

> Same logic when get False

## Enemy Desmemberment System in Head/Arms/Legs
![Sequence 01](https://github.com/DUDUKorte/UE5-RPD-Project/assets/40546705/df1187d4-e47b-4d5f-8d02-745cc23dd01a)
* Pre-Selected bones to break when the player hits X times that bone
* Also have "Lethal Bones" wich have more resistence, but, when it breaks, the enemy die (Head is not included, but it could be)
> Each Bone have a life in a Float number, when the player hit that bone the game pick a random number between 1-3 to damage it

> If the Bone's life is 0 or less, it break

> Also, every time the player hit any bone in upperbody, it enables ragdoll for some time only in that bone and its childrens to create a "impact illusion"
