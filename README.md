---

<h1 align="center">HANAMUKE INTERNAL</h1>
<p align="center">This internal will be published for release/testing soon.</p>
<p align="center">Will most likely give a release date on my Discord server <a href="https://discord.gg/SES9tgHEHE" target="_blank">Join here</a></p>

## 📝 Functions [Documentation]
+ [FindPath](#FindPath)
+ [GetTile](#GetTile)
+ [log](#log)
+ [SendPacket](#SendPacket)
+ [SendPacketRaw](#SendPacketRaw)  
+ [Sleep](#Sleep)
+ [SendVarlist](#SendVarlist)
+ [GetTile](#GetTile)
+ [GetTiles](#GetTiles)
+ [GetObjects](#GetObjects)
+ [GetInventory](#GetInventory)
+ [AddCallback](#AddCallback)
+ [RemoveCallbacks](#RemoveCallbacks)
+ [CollectItems](#CollectItems)
+ [CollectItem](#CollectItem)
+ [GetItemCount](#GetItemCount)
+ [GetPing](#GetPing)
+ [SendWebhook](#SendWebhook)
+ [Timer](#Timer)
+ [IsSolid](#IsSolid)
---


## SendPacket
```lua
SendPacket(int type, string action)
```
Sends a direct packet.
```lua
-- Example Usage:
SendPacket(2, "action|input\n|text| `#Hi from yuhkil")
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
    local pkt = {}
    pkt.type = 3
    pkt.int_data = 18
    pkt.pos_x = GetLocal().pos_x // 32
    pkt.pos_y = GetLocal().pos_y // 32
    pkt.int_x = x
    pkt.int_y = y
    pkt.flags = 2560
    SendPacketRaw(pkt)
end

punch(1, 0)
```

---

## log
```lua
-- Example usage:
log("Hello There")
```
Prints on to the game's console.

---

## GetInventory
```lua
GetInventory()
```
Returns information from inventory using the `Inventory` table.
```lua
-- Example usage:
for _,item in pairs(GetInventory()) do
	print(item.id)
end
```

---

## FindPath
```lua
FindPath(int x, int y)
```
Teleports with the best path to the destination.
```lua
-- Example usage:
FindPath(23,50)
```

---

## SendWebhook
```lua
SendWebhook(string webhook, string json)
```
Sends a webhook message (json).
```lua
-- Example Usage:
local payload = [[
{
    "content": "",
    "embeds": [{
        "title": "watehel",
        "description": "okay www.",
        "url": "https://github.com/GrowHax/Hanamuke",
        "color": 16777215,
        "fields": [{
            "name": "whatever",
            "value": "hey..."
        }],
        "author": {
            "name": "Yuhkil",
            "url": "https://example.com",
            "icon_url": "https://i.imgur.com/UvYjKOY.png"
        },
        "footer": {
            "text": "Sent from Hanamuke",
            "icon_url": "https://i.imgur.com/dDq7U7m.png"
        },
        "image": {
            "url": "https://i.imgur.com/WUlqAxg.png"
        },
        "thumbnail": {
            "url": "https://i.imgur.com/Wp6TaZi.png"
        },
        "timestamp": "2023-02-15T17:00:00.000Z"
    }]
}
]]
local webhook = "your webhook url"
SendWebhook(webhook, payload)
```

---

## GetTile
```lua
GetTile(int x, int y)
```
Gives information about a Tile
```lua
-- Example Usage:
local xx = GetLocal().x // 32
local yy = GetLocal().y // 32
local tile = GetTile(xx,yy)
print("Foreground:", tile.fg)
print("Background:", tile.bg)
```

---

## GetTiles
```lua
GetTiles()
```
logs all tiles in the world.
```lua
-- Example Usage:
local tiles = GetTiles()
log(tiles.bg)
```

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

## SendVarlist
```lua
local vartable = {}
SendVarlist(vartable)
```
Sends varlist to the client
```lua
-- Example Usage:
if GetLocal().name ~= nil then
    
    local me = GetLocal()
    local var = {}
    var[0] = "OnAddNotification"
    var[1] = "interface/atomic_button.rttex"
    var[2] = "Warning from `4System`0: You've been `4BANNED`0 from Growtopia for 730 days"
    var[3] = "audio/hub_open.wav"
    var.netid = -1 -- must be set otherwise it won't work
    SendVarlist(var)
end
```

---

## AddCallback
Adds a Lua function to be called when a specific event occurs in the game.
```lua
AddCallback("Hook", "OnPacket", function(type, packet)
  print("OnPacket callback was called")
  log(packet)
end)
```

## RemoveCallbacks
```lua
RemoveCallbacks()
```
Removes all Lua functions that were added with `AddCallback`.

---

## GetObjects
Returns objects from the `Object` table

---

## CollectItems
```lua
CollectItems(int tile_range)
```
Auto Collects Objects within specified tile range.
```lua
-- Example usage:
CollectItems(2)
```

---

## CollectItem
```lua
CollectItem(int tile_range, int obj_id)
```
Collects a specific obj_id within specified range. 
```lua
-- Example usage:
CollectItem(5, any object id) -- got no example for the object id currently
```

---

## GetItemCount
```lua
GetItemCount(int item_id)
```
Returns count of given item id.
```lua
-- Example usage:
log(GetItemCount(2))
```

---

## GetPing
```lua
GetPing()
```
Returns game ping.
```lua
-- Example usage:
log(GetPing())
```

---

## Timer
Timer, you can find the documentation here -> [Timer Library](https://wiki.facepunch.com/gmod/timer)
```lua
AddCallback("timer", "OnUpdate", function(deltatime)
    timer.Update(deltatime)
end)

-- second arg is delay (2 seconds in this case)
-- third arg is repeat amount (0 = infinite, 1 or more = repeat to certain amount) 
timer.Create("timer_example", 2, 0, function()
    print("LinusTouchTips") -- prints on the console every 2 seconds
end)

timer.Destroy("timer_example") -- this will delete the timer when present
```

---

## IsSolid
```lua
IsSolid(int x, int y)
```
Returns true if tile is solid - Returns false if tile is not solid.
```lua
-- Example usage:
local x = GetLocal().pos_x // 32
local y = GetLocal().pos_y // 32
log(IsSolid(x, y + 1)) -- if solid block it will return true
---

## **NetAvatar**
| Key      | Type   | Description                 |
|----------|--------|-----------------------------|
| `name`   | string | Player name (Local) |
| `world`  | string | World name (Local) |
| `netid`  | number | Player NetID |
| `uid`    | number | Player UsernameID |
| `pos_x`  | number | X Position |
| `pos_y`  | number | Y Position |
| `facing_left` | boolean | Return true if facing left |
| `country`| number  | country id |

## **Tile**
| Key      | Type     | Description |
| --------- | -------- | ----------- |
| `id`      | number   | Tile itemid |
| `pos_x`   | number   | Tile's X position |
| `pos_y`   | number   | Tile's Y position |
| `fg`      | string   | Tile foreground |
| `bg`      | string   | Tile background |

## **Object**
| Key   | Type   | Description                 |
|-------|--------|-----------------------------|
| `pos_x`   | number | X position of the object |
| `pos_y`   | number | Y position of the object |
| `id`  | number | Item ID of the object |
| `object_id` | number  | Returns object id |
| `flags` | number  | flags of object |
| `count` | number  | object count (amount) |

## **VarTable**
| Key      | Type     | Description |
| --------- | -------- | ----------- |
| `netid`   | number   | NetID |
| `delay`   | number   | Delay |
| `[0]`     | string   | Var case/function |
| `[1]`     | Any      | Param 1 |
| `[2]`     | Any      | Param 2 |
| `[3]`     | Any      | Param 3 |
| `[4]`     | Any      | Param 4 |
| `[5]`     | Any      | Param 5 |
