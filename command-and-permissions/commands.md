---
description: >-
  SayanEggwars plugin has a variety of commands to help you set up and manage
  your Eggwars arena
---

# 📜 Commands

**Setup Arena**

* Start a new setup session for your arena with `/ew setup <arena>`.
* Use the `/ew setup <arena> position1/2` command to set the first and second positions of the arena.
* Set the waiting position with `/ew setup <arena> waiting`, and the spectator position with `/ew setup <arena> spectator`.
* Choose the arena mode with `/ew setup <arena> mode <mode>`, and set the team size with `/ew setup <arena> team size <size>`.
* Add new generators with `/ew setup <arena> generator add <material> <level> [--broken]`.
* Add new teams with `/ew setup <arena> team add <name> [--displayname <displayname>] [--color <color>]`.
* Set the team egg location with `/ew setup <arena> team egg set <team>`, or remove the team egg you are looking at with `/ew setup <arena> team egg remove`.
* Set the team spawn location with `/ew setup <arena> team spawn <team>`, and the team villager location with `/ew setup <arena> team villager <team>`.
* Finish setup by typing `/ew setup <arena> finish`.

**Edit Arena**

* Edit an existing arena with `/ew edit <arena>`.
* Use the setup commands mentioned above to edit the arena properties.

**Edit Mode**

* Enter edit mode to edit the map and bypass plugin protections with `/ew editmode`.

**Help**

* View all available commands with `/ew help`.

**Inventory**

* Modify a player's inventory with `/ew inventory add/remove <player> <type> <item>`.

**Basic Usages**

* Join an arena with `/ew join <arena>`.
* Leave an arena with `/ew leave <arena>`.
* End an arena with `/ew end <arena> [--terminate]`.
* Start an arena with `/ew start <arena> [--force]`.

**Other Things**

* Modify a player's treasures with `/ew treasures add/remove <treasure>`.
* If you want to cancel the setup session, type `/ew setup <arena> cancel`.

{% hint style="info" %}
**Hint:** You don't have to type the commands - you can use chat components to run them.
{% endhint %}
