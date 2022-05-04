# Ordered Table
The order of elements when traversing the table (pairs) in lua is unpredictable. In OrderedTable, the traversal order always corresponds to the order in which keys are added.
## Example
```lua
local tbl = OrderedTable()
tbl.a = 5
tbl.b = 6
tbl.c = 8
tbl.d = 9
print(#tbl) --> 4

for k, v in pairs(tbl) do print(k,v) end --> a 5, b 6, c 8, d 9

tbl.b = nil
print(#tbl) --> 3

for k, v in pairs(tbl) do print(k,v) end --> a 5, c 8, d 9

local tbl_2 = OrderedTable()
print(getmetatable(tbl) == getmetatable(tbl_2)) --> true
```