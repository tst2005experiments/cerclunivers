```lua
max=10 -- la position 10 deviendra 0
me=2

function move(who, offset)
	return (who + offset) % max
end

me = move(me, 1) --> 3
me = move(me, 7) --> 0 (car 10 -> 0)
me = move(me, -2) --> 8
```
