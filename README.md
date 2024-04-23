---

<h1 align="center">HANAMUKE INTERNAL</h1>
<p align="center">This internal will be published for testing soon.</p>

## Functions [Documentation]
+ [log](#log)
+ [Punch](#pPunch)
+ [Place](#Place)
+ [SendPacket](#SendPacket)
+ [SendPacketRaw](#SendPacketRaw)  
+ [Sleep](#Sleep)
+ [warp](#warp)
+ [GetTile](#GetTile)
+ [getObjects](#getObjects)
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
      pos_x = GetLocal() .pos_x,
      pos_y = GetLocal() .pos_y,
      int_x = GetLocal() .pos_x // 32 + x,
      int_y = GetLocal() .pos_y // 32 + y,
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

## log
```lua
-- Example usage:
log("Hello There")
```
This will print "Hello There" on the game's console.

---

## Sleep
```lua
Sleep(int millisecond)
```
Delays with Sleep
```lua
-- Example Usage:
log("Start script")
Sleep(2000) -- delay 2 seconds
log("2 seconds later")
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
    local tile = GetTile(player.pos_x // 32, player.pos_y // 32)
    if tile ~= nil then
        print("Foreground:", tile.fg) -- retrives itemid for the foreground
        print("Background:", tile.bg) -- retrieves itemid for the background
    else
        print("Tile not found at position (" .. player.pos_x .. ", " .. player.pos_y .. ")")
    end
end
```

---

## getObjects
```lua
getObjects()
```
Returns information about the objects in the world.
```lua
-- Example Usage:
local obj = getObjects()

if obj then
    for i, obj in ipairs(obj) do
        print("  Position X: " .. obj.pos_x // 32)
        print("  Position Y: " .. obj.pos_y // 32)
        print("  Item ID: " .. obj.id)
        print("  Count: " .. obj.count)
        print("---------------")
    end
else
    print("No world objects found.")
end
```

---

## **NetAvatar**
| Type      | Description |
| --------- | ----------- |
| `name`| Player name |
| `country`| Country name |
| `netid`| Player's NetID |
| `uid`| Player's UsernameID |
| `pos_x`| Pixel X Position |     
| `pos_y`| Pixel Y Position |
| `facing_left`| Returns true when player is facing left |

## **Tile**
| Type      | Description |
| --------- | ----------- |
| `fg`| Foreground |
| `bg`| Background |

## **Objects**
| Type      | Description |
| --------- | ----------- |
| `id`| ItemID |
| `count`| Amount (stacked) |
| `pos_x`| Pixel X Position |     
| `pos_y`| Pixel Y Position |
| `flags`| Flags |
| `obj_id`| (This is just a indicator for objects) |

