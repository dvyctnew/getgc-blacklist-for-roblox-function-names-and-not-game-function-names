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
