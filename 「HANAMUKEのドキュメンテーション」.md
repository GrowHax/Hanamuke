---

<p align="center"> +Hanamuke+
    <br> 
</p>

## 📝 Functions
+ [warp](#warp)
+ [Log](#Log)
+ [Drop](#Drop)
  
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
This will print "Hello There" on to the console.

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

## FindPath
```lua
FindPath(int x, int y)
```
Teleports to the best path to the destination.
```lua
-- Example usage:
FindPath(23,50)
```