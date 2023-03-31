---
description: >-
  This class represents an Eggwars arena. It contains various methods and
  properties that can be used to manage an arena.
---

# EWArena

**Properties:**

* `name: String`: The name of the arena.
* `world: World`: The world in which the arena is located.
* `mode: String`: The game mode of the arena.
* `teams: List<Team>`: The teams in the arena.
* `teamSize: Int`: The maximum number of players allowed on each team.
* `generators: List<Generator>`: The generators in the arena.
* `waitingPosition: Location`: The location where players are teleported when they join the arena.
* `spectatorPosition: Location`: The location where spectators are teleported when they die or join the arena as spectators.
* `displayName: String`: The display name of the arena.
* `maxPlayers: Int`: The maximum number of players allowed in the arena.
* `state: ArenaState`: The current state of the arena. Can be `ArenaState.WAITING` or `ArenaState.PLAYING`.
* `lonelyNerds: MutableList<EWPlayer>`: A list of players who have joined the arena but have not yet been assigned to a team.
* `placedBlocks: MutableSet<Block>`: A set of blocks that have been placed in the arena.
* `shopkeeperGuiTemplate: ShopkeeperGUI?`: The shopkeeper GUI template for the arena.
* `shopkeeperGuis: MutableMap<Player, ShopkeeperGUI>`: A map of shopkeeper GUIs for each player in the arena.
* `playerKills: MutableMap<String, Int>`: A map of player kills for each player in the arena.

**Methods:**

* `fun canJoinArena(): Boolean`: Returns `true` if a player can join the arena, `false` otherwise.
* `fun canJoinTeam(team: Team): Boolean`: Returns `true` if a player can join the specified team, `false` otherwise.
* `fun joinTeam(player: EWPlayer, team: Team): Boolean`: Attempts to assign the specified player to the specified team. Returns `true` if successful, `false` otherwise.
* `fun joinRandomTeam()`: Assigns any players who have joined the arena but not yet been assigned to a team to a random team.
* `fun joinRandomTeam(ewPlayer: EWPlayer)`: Assigns the specified player to a random team.
* `fun getCurrentPlayersCount(): Int`: Returns the number of players currently in the arena.
* `fun removePlayer(ewPlayer: EWPlayer)`: Removes the specified player from their team or from the list of lonely nerds.
* `fun canStart(): Boolean`: Returns `true` if the arena can be started, `false` otherwise.
* `fun start()`: Starts the arena.
* `fun stop(winner: Team?)`: Stops the arena and announces the winner, if one exists.
* `fun terminate()`: Terminates the arena.
* `fun broadcastMessage(message: net.kyori.adventure.text.Component)`: Sends a message to all players in the arena.

**Example Usage:**

1. Create a new Eggwars arena:

```kotlin
arena = EWArena(
    "example_arena",
    world,
    "default",
    teams,
    2,
    generators,
    waitingPosition,
    spectatorPosition
)
```

This creates a new Eggwars arena named "example\_arena" in the "world" Minecraft world, with a team mode, four teams, each consisting of two players, one iron ore generator, a waiting area at location (0, 64, 0), and a spectator area at location (0, 100, 0).

2. Join a team in an arena:

```kotlin
player = EggwarsManager.instance.getEWPlayer(player)
if (arena.canJoinArena() && arena.canJoinTeam(team)) {
    arena.joinTeam(player, team)
    player.sendMessage("You joined ${team.name} team!")
} else {
    player.sendMessage("You cannot join the arena or the team right now.")
}
```

This joins a player named "player1" to a team in the arena, if the arena is in the waiting state, there is space in the arena and the team has not reached its capacity.

3. Start the game in an arena:

```kotlin
if (arena.canStart()) {
    arena.start()
    Bukkit.broadcastMessage("The Eggwars game has started in the ${arena.displayName} arena!")
} else {
    Bukkit.broadcastMessage("Cannot start the game in the ${arena.displayName} arena!")
}
```

This starts the game in the arena if the arena has players, and broadcasts a message to all players.

4. Stop the game in an arena:

```kotlin
arena.stop(winner = team)
```

This stops the game in the arena and declares the given team as the winner. If the given team is null, it means there is no winner, and the game finishes without declaring a winner.

5. Terminate the arena:

```kotlin
arena.terminate()
```

This terminates the arena forcefully, without declaring a winner, and all players are removed from the arena.
