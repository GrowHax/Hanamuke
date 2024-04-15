---

<h1 align="center">HANAMUKE INTERNAL</h1>
<p align="center">This internal will be published for testing soon.</p>

## Functions [Documentation]
+ [Log](#Log)
+ [Punch](#pPunch)
+ [Place](#Place)
+ [SendPacket](#SendPacket)
+ [SendPacketRaw](#SendPacketRaw)  
+ [sleep](#sleep)
+ [warp](#warp)
+ [GetTile](#GetTile)

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
  local pkt = {
      type = 3,
      int_data = 18,
      pos_x = GetLocal() .pixel_pos.x,
      pos_y = GetLocal() .pixel_pos.y,
      int_x = GetLocal() .tile_pos.x + x,
      int_y = GetLocal() .tile_pos.y + y,
      flags = 2560
  }
  SendPacketRaw(pkt)
end

punch(1,0)
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

## Punch
```lua
Punch(int x, int y)
```
A shortcut (using GetLocal()) for punch
```lua
-- Example usage:
Punch(1, 0)
```

---

## Place
```lua
Place(int x, int y, int int_data)
```
A shortcut (using GetPos) for place
```lua
-- Example usage:
Place(1, 0, 2)
```

---

## Log
```lua
-- Example usage:
Log("Hello There")
```
This will print "Hello There" on the game's console.

---

## sleep
```lua
sleep(int millisecond)
```
Delays with Sleep
```lua
-- Example Usage:
Log("Start script")
sleep(2000) -- delay 2 seconds
Log("2 seconds later")
```

---

## GetTile
```lua
GetTile(int x, int y)
```
Retrieve (additional) information from a specific tile.
```lua
-- Example Usage (In the way of debugging on current player pos):
local player = GetLocal()
if player ~= nil then
    local tile = GetTile(player.pixel_pos.x, player.pixel_pos.y)
    if tile ~= nil then
        print("Foreground:", tile.fg) -- retrives itemid for the foreground
        print("Background:", tile.bg) -- retrieves itemid for the background
    else
        print("Tile not found at position (" .. player.tile_pos.x .. ", " .. player.tile_pos.y .. ")")
    end
end
```

---

## **NetAvatar**
| Type      | Description |
| --------- | ----------- |
| `name`| current Player name |
| `world`| current world name |
| `netid`| Player's NetID |
| `uid`     | Player's UsernameID |
| `tile_pos.x`| Tile X Position |     
| `tile_pos.y`| Tile Y Position |
| `pixel_pos.x`| Pixel X Position |
| `pixel_pos.y`| Pixel Y Position |


## **Tile**
| Type      | Description |
| --------- | ----------- |
| `fg`| Foreground |
| `bg`| Background |
