---

<p align="center"> +Hanamuke+
    <br> 
</p>

## 📝 Functions [Documentation]
+ [warp](#warp)
+ [Log](#Log)
+ [Drop](#Drop)
+ [FindPath](#FindPath)
+ [IsTileReady](#IsTileReady)
  
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


