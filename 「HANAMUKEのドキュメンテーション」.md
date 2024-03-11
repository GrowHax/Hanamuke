---

<h1 align="center"> +Hanamuke+
    <br> 
</p>

## 📝 Functions [Documentation]
+ [Drop](#Drop)
+ [FindPath](#FindPath)
+ [GetTileData](#GetTileData)
+ [IsTileReady](#IsTileReady)
+ [Log](#Log)
+ [place](#place)
+ [punch](#punch)
+ [SendPacket](#SendPacket)
+ [SendPacketRaw](#SendPacketRaw)  
+ [SendWebhook](#SendWebhook)
+ [Sleep](#Sleep)
+ [warp](#warp)

  (coming up)
+ [GetTile](#GetTile)
+ [GetTiles](#GetTiles)
+ [AddCallback](#AddCallback)
+ [RemoveCallbacks](#RemoveCallbacks)
+ Support for objects
---

## SendPacket
```lua
SendPacket(int type, string action)
```
Sends a direct packet.
```lua
-- Example Usage:
SendPacket(2, "action|input\n|text|HELLO)
```
---

## SendPacketRaw
```lua
SendPacketRaw(pkt)
```
Send Raw Packet to the server
```lua
-- Example Usage:
function punch(x, y)
    local pkt = GameUpdatePacket()
    pkt.type = 3
    pkt.int_data = 18
    pkt.pos_x = GetPos().x
    pkt.pos_y = GetPos().y
    pkt.int_x = x
    pkt.int_y = y
    pkt.packet_flags = 2560
    SendPacketRaw(pkt)
end

punch((GetPos().x // 32) + 1, (GetPos().y // 32))
```

---

## warp
```lua
warp("WORLD")
```

warp with DoorID is as follow.
```lua
-- Example usage:
warp("WORLD|DOORID")
```

---

## punch
```lua
punch(int x, int y)
```
A shortcut (using GetPos) for punch
```lua
-- Example usage:
punch(1, 0)
```

---

## place
```lua
place(int x, int y, int int_data)
```
A shortcut (using GetPos) for place
```lua
-- Example usage:
place(1, 0, 2)
```

---

## Log
```lua
-- Example usage:
Log("Hello There")
```
This will print "Hello There" on to the game's console.

---

## Drop
```lua
Drop(itemid, amount)
```
Dropping 10 blocks of dirt.
```lua
-- Example usage:
Drop(2, 10)
```

---

## FindPath
```lua
FindPath(int x, int y)
```
Teleports to the best path to the destination.
```lua
-- Example usage:
FindPath(23,50)
```

---

## IsTileReady
```lua
IsTileReady(int tilepos.x, int tilepos.y)
```
Checks if tree is ready to harvest or not. 
```lua
-- Example usage:
xx = GetPos().x // 32
yy = GetPos().y // 32

IsTileReady(xx, yy)
```

---

## SendWebhook
```lua
SendWebhook(string message, string webhookurl)
```
Sends a message on Discord using Webhook.
```lua
-- Example Usage:
SendWebHook("Hello", "https://discord.com/api/webhooks/YOURWEBHOOK")
```

---

## GetTile
```lua
GetTile(int x, int y)
```
Returns world tile
```lua
-- Example Usage:
local block = GetTile(52,60)
Log(block.id)
```

---

## GetTiles
```lua
GetTiles()
```
Logs all blocks in the world
```lua
-- Example Usage:
local tiles = GetTiles()
Log(tiles.bg)
```

---

## GetTileData
```lua
GetTileData(int x, int y)
```
Gives extra information about a Tile
```lua
-- Example Usage:
local xx = GetPos().x // 32
local yy = GetPos().y // 32
local tile = GetTileData(xx,yy)
print("Foreground:", tile.fg)
print("Background:", tile.bg)
```

---

## Sleep
```lua
Sleep(int millisecond)
```
Delays with Sleep
```lua
-- Example Usage:
Log("Start script")
Sleep(2000) -- delay 2 seconds
Log("2 seconds later")
```

---

## **NetAvatar**
| Type      | Description |
| --------- | ----------- |
| `name`| current Player name |
| `world`| current world name |
| `netid`| Player's NetID |
| `uid`     | Player's UsernameID |
| `GetPos().x`| Tile X Position |     
| `GetPos().y`| Tile Y Position |

## **Tile**
| Type      | Description |
| --------- | ----------- |
| `id`| Tile itemid |
| `x`| Tile's X position |
| `y`| Tile's Y position |
| `fg`| Tile foreground |
| `bg`| Tile background |

(coming soon)

| `obj`| objects on tile |
