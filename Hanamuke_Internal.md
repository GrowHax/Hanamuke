---

<h1 align="center"> HANAMUKE INTERNAL
    <br> 
</p>

## 📝 Functions [Documentation]
+ [Log](#Log)
+ [punch](#punch)
+ [SendPacket](#SendPacket)
+ [SendPacketRaw](#SendPacketRaw)  
+ [Sleep](#Sleep)
+ [warp](#warp)

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
      pos_x = player.pixel_pos.x,
      pos_y = player.pixel_pos.y,
      int_x = player.tile_pos.x + 1,
      int_y = player.tile_pos.y - 0,
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

## punch
```lua
punch(int x, int y)
```
A shortcut (using GetLocal()) for punch
```lua
-- Example usage:
Punch(1, 0)
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
| `x`| Tile's X position |
| `y`| Tile's Y position |
