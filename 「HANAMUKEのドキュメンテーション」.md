---

<h1 align="center"> +Hanamuke+
    <br> 
</p>

## 📝 Functions [Documentation]
+ [SendPacket](#SendPacket)
+ [SendPacketRaw](#SendPacketRaw)  
+ [warp](#warp)
+ [Log](#Log)
+ [Drop](#Drop)
+ [FindPath](#FindPath)
+ [IsTileReady](#IsTileReady)
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
## **NetAvatar**
| Type      | Description |
| --------- | ----------- |
| `name`| current Player name |
| `world`| current world name |
| `uid`     | Player's UsernameID |
| `GetPos().x`| Tile X Position |              
| `GetPos().y`| Tile Y Position |

