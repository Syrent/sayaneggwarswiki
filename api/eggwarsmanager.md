# EggwarsManager

**Properties:**

`players: MutableMap<UUID, EWPlayer>`: A mutable map containing all the currently connected players in the Eggwars game, indexed by their UUID.

`ewWorlds: MutableMap<String, EWWorld>`: A mutable map containing all the Eggwars worlds, indexed by their name.

`arenas: MutableList<EWArena.Template>`: A mutable list containing all the templates of the Eggwars arenas.

`shopkeepers: MutableMap<String, ShopkeeperGUI.Companion.Template>`: A mutable map containing all the templates for the shopkeepers.

`generators: MutableMap<String, List<SerializedGenerator>>`: A mutable map containing all the serialized generators in the Eggwars game, indexed by their name.

`treasures: MutableMap<String, TreasureBox>`: A mutable map containing all the treasure boxes in the Eggwars game, indexed by their name.

`sessions: HashMap<String, ArenaSetupSession>`: A hash map containing all the active arena setup sessions, indexed by the name of the arena.

`shop: MutableList<ShopItem>`: A mutable list containing all the items available in the shop.

`particleEffects: MutableList<ShopItem>`: A mutable list containing all the particle effects available in the shop.

`lobbyLocation: Location`: The location of the Eggwars lobby.

**Methods:**

`fun getEWPlayer(player: Player): EWPlayer?`: Returns the `EWPlayer` object for the given player, or `null` if the player is not currently connected to the Eggwars game.

`fun getEWPlayer(uuid: UUID): EWPlayer?`: Returns the `EWPlayer` object for the player with the given UUID, or `null` if the player is not currently connected to the Eggwars game.

`fun getArenaInstances(): List<EWArena>`: Returns a list containing all the instances of the Eggwars arenas currently in use.

`fun getArenaTemplate(name: String): EWArena.Template?`: Returns the `EWArena.Template` object for the arena with the given name, or `null` if no arena with that name exists.

`fun getArena(name: String): EWArena?`: Returns the `EWArena` object for the arena with the given name, or `null` if no arena with that name exists.
