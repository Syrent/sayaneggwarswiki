---
description: >-
  The Event API page is where you can learn about the different events that are
  available for developers to use when creating plugins for SayanEggwars
---

# Events

### ArenaDeleteEvent

This event is fired whenever an arena is deleted. It contains information about the arena that was deleted. This event is useful for plugins that need to perform cleanup operations when an arena is deleted.

### ArenaGenerateEvent

This event is fired whenever a new arena is generated. It contains information about the newly generated arena. This event is useful for plugins that need to perform additional setup operations when a new arena is generated.

### ArenaTemplateDeleteEvent

This event is fired whenever an arena template is deleted. It contains information about the template that was deleted. This event is useful for plugins that need to perform cleanup operations when an arena template is deleted.

### ArenaTemplateGenerateEvent

This event is fired whenever a new arena template is generated. It contains information about the newly generated template. This event is useful for plugins that need to perform additional setup operations when a new arena template is generated.

### EWPlayerDeathEvent

This event is fired whenever a player dies in an Eggwars game. It contains information about the player that died. This event is useful for plugins that need to perform additional operations when a player dies, such as awarding points to the player's opponents.

## PlayerJoinTeamEvent

PlayerJoinTeamEvent This event is fired whenever a player joins a team in an Eggwars game. It contains information about the arena, player, and team involved in the event. This event is useful for plugins that need to perform additional operations when a player joins a team.

To use these events in your plugin, you will need to register a listener for each event. Listeners can be registered using the `registerEvents` method provided by the Bukkit API. When an event is fired, any registered listeners will be called in the order they were registered. In your listener, you can perform any additional operations that are necessary based on the event that was fired.
