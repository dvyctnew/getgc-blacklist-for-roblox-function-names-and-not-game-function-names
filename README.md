# getgc-blacklist-for-roblox-function-names-and-not-game-function-names

# Example Usage
```lua
local blacklist = {
-- all the ones in the script provided above
}
local functionnames = {}
for _, v in getgc(true) do
	if typeof(v) == 'function' then
		local funcname = debug.info(v, "n")
		if funcname ~= nil and funcname ~= "" and not table.find(blacklist, funcname) then
			table.insert(functionnames, funcname) -- only inserts local functions and functions that the GAME not roblox but the GAME uses
		end
	end
end
```
This is just if you want to find a game function like if they have a Raycast for a local function etc,
you still might want to hook roblox functions for specific games this is just for people like me
who hate the mess you have to go through.
