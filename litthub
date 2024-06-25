local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

print("Loading LittHub")
local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - Exploiting Utilities | ScriptHub",
   LoadingTitle = "LittHub🔥 - Exploiting Utilities",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, 
      FileName = "LittHub"
   },
   Discord = {
      Enabled = false, --https://link-target.net/1182452/litthub-keysystem
      Invite = "noinvitelink",
      RememberJoins = true 
   },
   KeySystem = false, 
   KeySettings = {
      Title = "LittHub🔥 - Exploiting Utilities ScriptHub | Key System",
      Subtitle = "Key Link Copied To Clipboard",
      Note = "Link: https://link-target.net/1182452/litthub-keysystem",
      FileName = "Key", 
      SaveKey = true, 
      GrabKeyFromSite = true, 
      Key = {"https://pastebin.com/raw/KBvfpj38"} 
   }
})

Rayfield:Notify({
   Title = "Follow Littmsn On Roblox",
   Content = "Welcome, ".. game.Players.LocalPlayer.Name,
   Duration = 6.5,
   Image = 4483362458,
   Actions = { -- Notification Buttons
      Ignore = {
         Name = "Okay!",
         Callback = function()
         print("")
      end
   },
},
})

print("Loaded Successfully")
    
local MiscTab = Window:CreateTab("Misc", nil) -- Title, Image

local MiscSection = MiscTab:CreateSection("Player Humanoid")

local Button = MiscTab:CreateButton({
   Name = "Infinite Jump",
   Callback = function()
  local InfiniteJumpEnabled = true
game:GetService("UserInputService").JumpRequest:connect(function()
	if InfiniteJumpEnabled then
		game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
	end
end)
local InfiniteJump = CreateButton("Infinite Jump: On", StuffFrame)
InfiniteJump.Position = UDim2.new(0,10,0,130)
InfiniteJump.Size = UDim2.new(0,150,0,30)
InfiniteJump.MouseButton1Click:connect(function()
	local state = InfiniteJump.Text:sub(string.len("Infinite Jump: ") + 1) --too lazy to count lol
	local new = state == "Off" and "On" or state == "On" and "Off"
	InfiniteJumpEnabled = new == "On"
	InfiniteJump.Text = "Infinite Jump: " .. new
end)
   end,
})

local Slider = MiscTab:CreateSlider({
   Name = "WalkSpeed",
   Range = {0, 300},
   Increment = 1,
   Suffix = "Speed",
   CurrentValue = 16,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
           game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = (Value)
   end,
})

local Slider = MiscTab:CreateSlider({
   Name = "JumpPower",
   Range = {0, 300},
   Increment = 1,
   Suffix = "JumpPower",
   CurrentValue = 50,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
           game.Players.LocalPlayer.Character.Humanoid.JumpPower = (Value)
   end,
})

local Section = MiscTab:CreateSection("Other")


local Button = MiscTab:CreateButton({
   Name = "UNC Test (Working:🟢)",
   Callback = function()
        local passes, fails, undefined = 0, 0, 0
local running = 0

local function getGlobal(path)
	return getgenv()[path]
end

local function test(name, aliases, callback)
	running = running + 1

	task.spawn(function()
		if not callback then
			print("⏺️ " .. name)
		elseif not getGlobal(name) then
			fails = fails + 1
			warn("⛔ " .. name)
		else
			local success, message = pcall(callback)
	        name = tostring(name)
			message = tostring(message)
			if success then
				passes = passes + 1
				print("✅ " .. tostring(name) .. (tostring(message) and " • " .. tostring(message) or ""))
			else
				fails = fails + 1
				warn("⛔ " .. name .. " failed: " .. message)
			end
		end
	
		local undefinedAliases = {}
	
		for _, alias in ipairs(aliases) do
			if getGlobal(alias) == nil then
				table.insert(undefinedAliases, alias)
			end
		end
	
		if #undefinedAliases > 0 then
			undefined = undefined + 1
			warn("⚠️ " .. table.concat(undefinedAliases, ", "))
		end

		running = running - 1
	end)
end

-- Header and summary

print("\n")

print("UNC Environment Check")
print("✅ - Pass, ⛔ - Fail, ⏺️ - No test, ⚠️ - Missing aliases\n")

task.defer(function()
	repeat task.wait() until running == 0

	local rate = math.round(passes / (passes + fails) * 100)
	local outOf = passes .. " out of " .. (passes + fails)

	print("\n")

	print("UNC Summary")
	print("✅ Tested with a " .. rate .. "% success rate (" .. outOf .. ")")
	print("⛔ " .. fails .. " tests failed")
	print("⚠️ " .. undefined .. " globals are missing aliases")
end)

-- Cache

test("cache.invalidate", {}, function()
	local container = Instance.new("Folder")
	local part = Instance.new("Part", container)
	cache.invalidate(container:FindFirstChild("Part"))
	assert(part ~= container:FindFirstChild("Part"), "Reference `part` could not be invalidated")
end)

test("cache.iscached", {}, function()
	local part = Instance.new("Part")
	assert(cache.iscached(part), "Part should be cached")
	cache.invalidate(part)
	assert(not cache.iscached(part), "Part should not be cached")
end)

test("cache.replace", {}, function()
	local part = Instance.new("Part")
	local fire = Instance.new("Fire")
	cache.replace(part, fire)
	assert(part ~= fire, "Part was not replaced with Fire")
end)

test("cloneref", {}, function()
	local part = Instance.new("Part")
	local clone = cloneref(part)
	assert(part ~= clone, "Clone should not be equal to original")
	clone.Name = "Test"
	assert(part.Name == "Test", "Clone should have updated the original")
end)

test("compareinstances", {}, function()
	local part = Instance.new("Part")
	local clone = cloneref(part)
	assert(part ~= clone, "Clone should not be equal to original")
	assert(compareinstances(part, clone), "Clone should be equal to original when using compareinstances()")
end)

-- Closures

local function shallowEqual(t1, t2)
	if t1 == t2 then
		return true
	end

	local UNIQUE_TYPES = {
		["function"] = true,
		["table"] = true,
		["userdata"] = true,
		["thread"] = true,
	}

	for k, v in pairs(t1) do
		if UNIQUE_TYPES[type(v)] then
			if type(t2[k]) ~= type(v) then
				return false
			end
		elseif t2[k] ~= v then
			return false
		end
	end

	for k, v in pairs(t2) do
		if UNIQUE_TYPES[type(v)] then
			if type(t2[k]) ~= type(v) then
				return false
			end
		elseif t1[k] ~= v then
			return false
		end
	end

	return true
end

test("checkcaller", {}, function()
	assert(checkcaller(), "Main scope should return true")
end)

test("clonefunction", {}, function()
	local function test()
		return "success"
	end
	local copy = clonefunction(test)
	assert(test() == copy(), "The clone should return the same value as the original")
	assert(test ~= copy, "The clone should not be equal to the original")
end)

test("getcallingscript", {})

test("getscriptclosure", {"getscriptfunction"}, function()
	local module = game:GetService("CoreGui").RobloxGui.Modules.Common.Constants
	local constants = getrenv().require(module)
	local generated = getscriptclosure(module)()
	assert(constants ~= generated, "Generated module should not match the original")
	assert(shallowEqual(constants, generated), "Generated constant table should be shallow equal to the original")
end)

test("hookfunction", {"replaceclosure"}, function()
	local function test()
		return true
	end
	local ref = hookfunction(test, function()
		return false
	end)
	assert(test() == false, "Function should return false")
	assert(ref() == true, "Original function should return true")
	assert(test ~= ref, "Original function should not be same as the reference")
end)

test("iscclosure", {}, function()
	assert(iscclosure(print) == true, "Function 'print' should be a C closure")
	assert(iscclosure(function() end) == false, "Executor function should not be a C closure")
end)

test("islclosure", {}, function()
	assert(islclosure(print) == false, "Function 'print' should not be a Lua closure")
	assert(islclosure(function() end) == true, "Executor function should be a Lua closure")
end)

test("isexecutorclosure", {"checkclosure", "isourclosure"}, function()
	assert(isexecutorclosure(isexecutorclosure) == true, "Did not return true for an executor global")
	assert(isexecutorclosure(newcclosure(function() end)) == true, "Did not return true for an executor C closure")
	assert(isexecutorclosure(function() end) == true, "Did not return true for an executor Luau closure")
	assert(isexecutorclosure(print) == false, "Did not return false for a Roblox global")
end)

test("loadstring", {}, function()
	local animate = game:GetService("Players").LocalPlayer.Character.Animate
	local bytecode = getscriptbytecode(animate)
	local func = loadstring(bytecode)
	assert(type(func) ~= "function", "Luau bytecode should not be loadable!")
	assert(assert(loadstring("return ... + 1"))(1) == 2, "Failed to do simple math")
	assert(type(select(2, loadstring("f"))) == "string", "Loadstring did not return anything for a compiler error")
end)

test("newcclosure", {}, function()
	local function test()
		return true
	end
	local testC = newcclosure(test)
	assert(test() == testC(), "New C closure should return the same value as the original")
	assert(test ~= testC, "New C closure should not be same as the original")
	assert(iscclosure(testC), "New C closure should be a C closure")
end)

-- Console

test("rconsoleclear", {"consoleclear"})

test("rconsolecreate", {"consolecreate"})

test("rconsoledestroy", {"consoledestroy"})

test("rconsoleinput", {"consoleinput"})

test("rconsoleprint", {"consoleprint"})

test("rconsolesettitle", {"rconsolename", "consolesettitle"})

-- Crypt

test("crypt.base64encode", {"crypt.base64.encode", "crypt.base64_encode", "base64.encode", "base64_encode"}, function()
	assert(crypt.base64encode("test") == "dGVzdA==", "Base64 encoding failed")
end)

test("crypt.base64decode", {"crypt.base64.decode", "crypt.base64_decode", "base64.decode", "base64_decode"}, function()
	assert(crypt.base64decode("dGVzdA==") == "test", "Base64 decoding failed")
end)

test("crypt.encrypt", {}, function()
	local key = crypt.generatekey()
	local encrypted, iv = crypt.encrypt("test", key, nil, "CBC")
	assert(iv, "crypt.encrypt should return an IV")
	local decrypted = crypt.decrypt(encrypted, key, iv, "CBC")
	assert(decrypted == "test", "Failed to decrypt raw string from encrypted data")
end)

test("crypt.decrypt", {}, function()
	local key, iv = crypt.generatekey(), crypt.generatekey()
	local encrypted = crypt.encrypt("test", key, iv, "CBC")
	local decrypted = crypt.decrypt(encrypted, key, iv, "CBC")
	assert(decrypted == "test", "Failed to decrypt raw string from encrypted data")
end)

test("crypt.generatebytes", {}, function()
	local size = math.random(10, 100)
	local bytes = crypt.generatebytes(size)
	assert(#crypt.base64decode(bytes) == size, "The decoded result should be " .. size .. " bytes long (got " .. #crypt.base64decode(bytes) .. " decoded, " .. #bytes .. " raw)")
end)

test("crypt.generatekey", {}, function()
	local key = crypt.generatekey()
	assert(#crypt.base64decode(key) == 32, "Generated key should be 32 bytes long when decoded")
end)

test("crypt.hash", {}, function()
	local algorithms = {'sha1', 'sha384', 'sha512', 'md5', 'sha256', 'sha3-224', 'sha3-256', 'sha3-512'}
	for _, algorithm in ipairs(algorithms) do
		local hash = crypt.hash("test", algorithm)
		assert(hash, "crypt.hash on algorithm '" .. algorithm .. "' should return a hash")
	end
end)

--- Debug

test("debug.getconstant", {}, function()
	local function test()
		print("Hello, world!")
	end
	assert(debug.getconstant(test, 1) == "print", "First constant must be print")
	assert(debug.getconstant(test, 2) == nil, "Second constant must be nil")
	assert(debug.getconstant(test, 3) == "Hello, world!", "Third constant must be 'Hello, world!'")
end)

test("debug.getconstants", {}, function()
	local function test()
		local num = 5000 .. 50000
		print("Hello, world!", num, warn)
	end
	local constants = debug.getconstants(test)
	assert(constants[1] == 50000, "First constant must be 50000")
	assert(constants[2] == "print", "Second constant must be print")
	assert(constants[3] == nil, "Third constant must be nil")
	assert(constants[4] == "Hello, world!", "Fourth constant must be 'Hello, world!'")
	assert(constants[5] == "warn", "Fifth constant must be warn")
end)

test("debug.getinfo", {}, function()
	local types = {
		source = "string",
		short_src = "string",
		func = "function",
		what = "string",
		currentline = "number",
		name = "string",
		nups = "number",
		numparams = "number",
		is_vararg = "number",
	}
	local function test(...)
		print(...)
	end
	local info = debug.getinfo(test)
	for k, v in pairs(types) do
		assert(info[k] ~= nil, "Did not return a table with a '" .. k .. "' field")
		assert(type(info[k]) == v, "Did not return a table with " .. k .. " as a " .. v .. " (got " .. type(info[k]) .. ")")
	end
end)

test("debug.getproto", {}, function()
	local function test()
		local function proto()
			return true
		end
	end
	local proto = debug.getproto(test, 1, true)[1]
	local realproto = debug.getproto(test, 1)
	assert(proto, "Failed to get the inner function")
	assert(proto() == true, "The inner function did not return anything")
	if not realproto() then
		return "Proto return values are disabled on this executor"
	end
end)

test("debug.getprotos", {}, function()
	local function test()
		local function _1()
			return true
		end
		local function _2()
			return true
		end
		local function _3()
			return true
		end
	end
	for i in ipairs(debug.getprotos(test)) do
		local proto = debug.getproto(test, i, true)[1]
		local realproto = debug.getproto(test, i)
		assert(proto(), "Failed to get inner function " .. i)
		if not realproto() then
			return "Proto return values are disabled on this executor"
		end
	end
end)

test("debug.getstack", {}, function()
	local _ = "a" .. "b"
	assert(debug.getstack(1, 1) == "ab", "The first item in the stack should be 'ab'")
	assert(debug.getstack(1)[1] == "ab", "The first item in the stack table should be 'ab'")
end)

test("debug.getupvalue", {}, function()
	local upvalue = function() end
	local function test()
		print(upvalue)
	end
	assert(debug.getupvalue(test, 1) == upvalue, "Unexpected value returned from debug.getupvalue")
end)

test("debug.getupvalues", {}, function()
	local upvalue = function() end
	local function test()
		print(upvalue)
	end
	local upvalues = debug.getupvalues(test)
	assert(upvalues[1] == upvalue, "Unexpected value returned from debug.getupvalues")
end)

test("debug.setconstant", {}, function()
	local function test()
		return "fail"
	end
	debug.setconstant(test, 1, "success")
	assert(test() == "success", "debug.setconstant did not set the first constant")
end)

test("debug.setstack", {}, function()
	local function test()
		return "fail", debug.setstack(1, 1, "success")
	end
	assert(test() == "success", "debug.setstack did not set the first stack item")
end)

test("debug.setupvalue", {}, function()
	local function upvalue()
		return "fail"
	end
	local function test()
		return upvalue()
	end
	debug.setupvalue(test, 1, function()
		return "success"
	end)
	assert(test() == "success", "debug.setupvalue did not set the first upvalue")
end)

-- Filesystem

if isfolder and makefolder and delfolder then
	if isfolder(".tests") then
		delfolder(".tests")
	end
	makefolder(".tests")
end

test("readfile", {}, function()
	writefile(".tests/readfile.txt", "success")
	assert(readfile(".tests/readfile.txt") == "success", "Did not return the contents of the file")
end)

test("listfiles", {}, function()
	makefolder(".tests/listfiles")
	writefile(".tests/listfiles/test_1.txt", "success")
	writefile(".tests/listfiles/test_2.txt", "success")
	local files = listfiles(".tests/listfiles")
	assert(#files == 2, "Did not return the correct number of files")
	assert(isfile(files[1]), "Did not return a file path")
	assert(readfile(files[1]) == "success", "Did not return the correct files")
	makefolder(".tests/listfiles_2")
	makefolder(".tests/listfiles_2/test_1")
	makefolder(".tests/listfiles_2/test_2")
	local folders = listfiles(".tests/listfiles_2")
	assert(#folders == 2, "Did not return the correct number of folders")
	assert(isfolder(folders[1]), "Did not return a folder path")
end)

test("writefile", {}, function()
	writefile(".tests/writefile.txt", "success")
	assert(readfile(".tests/writefile.txt") == "success", "Did not write the file")
	local requiresFileExt = pcall(function()
		writefile(".tests/writefile", "success")
		assert(isfile(".tests/writefile.txt"))
	end)
	if not requiresFileExt then
		return "This executor requires a file extension in writefile"
	end
end)

test("makefolder", {}, function()
	makefolder(".tests/makefolder")
	assert(isfolder(".tests/makefolder"), "Did not create the folder")
end)

test("appendfile", {}, function()
	writefile(".tests/appendfile.txt", "su")
	appendfile(".tests/appendfile.txt", "cce")
	appendfile(".tests/appendfile.txt", "ss")
	assert(readfile(".tests/appendfile.txt") == "success", "Did not append the file")
end)

test("isfile", {}, function()
	writefile(".tests/isfile.txt", "success")
	assert(isfile(".tests/isfile.txt") == true, "Did not return true for a file")
	assert(isfile(".tests") == false, "Did not return false for a folder")
	assert(isfile(".tests/doesnotexist.exe") == false, "Did not return false for a nonexistent path (got " .. tostring(isfile(".tests/doesnotexist.exe")) .. ")")
end)

test("isfolder", {}, function()
	assert(isfolder(".tests") == true, "Did not return false for a folder")
	assert(isfolder(".tests/doesnotexist.exe") == false, "Did not return false for a nonexistent path (got " .. tostring(isfolder(".tests/doesnotexist.exe")) .. ")")
end)

test("delfolder", {}, function()
	makefolder(".tests/delfolder")
	delfolder(".tests/delfolder")
	assert(isfolder(".tests/delfolder") == false, "Failed to delete folder (isfolder = " .. tostring(isfolder(".tests/delfolder")) .. ")")
end)

test("delfile", {}, function()
	writefile(".tests/delfile.txt", "Hello, world!")
	delfile(".tests/delfile.txt")
	assert(isfile(".tests/delfile.txt") == false, "Failed to delete file (isfile = " .. tostring(isfile(".tests/delfile.txt")) .. ")")
end)

test("loadfile", {}, function()
	writefile(".tests/loadfile.txt", "return ... + 1")
	assert(assert(loadfile(".tests/loadfile.txt"))(1) == 2, "Failed to load a file with arguments")
	writefile(".tests/loadfile.txt", "f")
	local callback, err = loadfile(".tests/loadfile.txt")
	assert(err and not callback, "Did not return an error message for a compiler error")
end)

test("dofile", {})

-- Input

test("isrbxactive", {"isgameactive"}, function()
	assert(type(isrbxactive()) == "boolean", "Did not return a boolean value")
end)

test("mouse1click", {})

test("mouse1press", {})

test("mouse1release", {})

test("mouse2click", {})

test("mouse2press", {})

test("mouse2release", {})

test("mousemoveabs", {})

test("mousemoverel", {})

test("mousescroll", {})

-- Instances

test("fireclickdetector", {}, function()
	local detector = Instance.new("ClickDetector")
	fireclickdetector(detector, 50, "MouseHoverEnter")
end)

test("getcallbackvalue", {}, function()
	local bindable = Instance.new("BindableFunction")
	local function test()
	end
	bindable.OnInvoke = test
	assert(getcallbackvalue(bindable, "OnInvoke") == test, "Did not return the correct value")
end)

test("getconnections", {}, function()
	local types = {
		Enabled = "boolean",
		ForeignState = "boolean",
		LuaConnection = "boolean",
		Function = "function",
		Thread = "thread",
		Fire = "function",
		Defer = "function",
		Disconnect = "function",
		Disable = "function",
		Enable = "function",
	}
	local bindable = Instance.new("BindableEvent")
	bindable.Event:Connect(function() end)
	local connection = getconnections(bindable.Event)[1]
	for k, v in pairs(types) do
		assert(connection[k] ~= nil, "Did not return a table with a '" .. k .. "' field")
		assert(type(connection[k]) == v, "Did not return a table with " .. k .. " as a " .. v .. " (got " .. type(connection[k]) .. ")")
	end
end)

test("getcustomasset", {}, function()
	writefile(".tests/getcustomasset.txt", "success")
	local contentId = getcustomasset(".tests/getcustomasset.txt")
	assert(type(contentId) == "string", "Did not return a string")
	assert(#contentId > 0, "Returned an empty string")
	assert(string.match(contentId, "rbxasset://") == "rbxasset://", "Did not return an rbxasset url")
end)

test("gethiddenproperty", {}, function()
	local fire = Instance.new("Fire")
	local property, isHidden = gethiddenproperty(fire, "size_xml")
	assert(property == 5, "Did not return the correct value")
	assert(isHidden == true, "Did not return whether the property was hidden")
end)

test("sethiddenproperty", {}, function()
	local fire = Instance.new("Fire")
	local hidden = sethiddenproperty(fire, "size_xml", 10)
	assert(hidden, "Did not return true for the hidden property")
	assert(gethiddenproperty(fire, "size_xml") == 10, "Did not set the hidden property")
end)

test("gethui", {}, function()
	assert(typeof(gethui()) == "Instance", "Did not return an Instance")
end)

test("getinstances", {}, function()
	assert(getinstances()[1]:IsA("Instance"), "The first value is not an Instance")
end)

test("getnilinstances", {}, function()
	assert(getnilinstances()[1]:IsA("Instance"), "The first value is not an Instance")
	assert(getnilinstances()[1].Parent == nil, "The first value is not parented to nil")
end)

test("isscriptable", {}, function()
	local fire = Instance.new("Fire")
	assert(isscriptable(fire, "size_xml") == false, "Did not return false for a non-scriptable property (size_xml)")
	assert(isscriptable(fire, "Size") == true, "Did not return true for a scriptable property (Size)")
end)

test("setscriptable", {}, function()
	local fire = Instance.new("Fire")
	local wasScriptable = setscriptable(fire, "size_xml", true)
	assert(wasScriptable == false, "Did not return false for a non-scriptable property (size_xml)")
	assert(isscriptable(fire, "size_xml") == true, "Did not set the scriptable property")
	fire = Instance.new("Fire")
	assert(isscriptable(fire, "size_xml") == false, "⚠️⚠️ setscriptable persists between unique instances ⚠️⚠️")
end)

test("setrbxclipboard", {})

-- Metatable

test("getrawmetatable", {}, function()
	local metatable = { __metatable = "Locked!" }
	local object = setmetatable({}, metatable)
	assert(getrawmetatable(object) == metatable, "Did not return the metatable")
end)

test("hookmetamethod", {}, function()
	local object = setmetatable({}, { __index = newcclosure(function() return false end), __metatable = "Locked!" })
	local ref = hookmetamethod(object, "__index", function() return true end)
	assert(object.test == true, "Failed to hook a metamethod and change the return value")
	assert(ref() == false, "Did not return the original function")
end)

test("getnamecallmethod", {}, function()
	local method
	local ref
	ref = hookmetamethod(game, "__namecall", function(...)
		if not method then
			method = getnamecallmethod()
		end
		return ref(...)
	end)
	game:GetService("Lighting")
	assert(method == "GetService", "Did not get the correct method (GetService)")
end)

test("isreadonly", {}, function()
	local object = {}
	table.freeze(object)
	assert(isreadonly(object), "Did not return true for a read-only table")
end)

test("setrawmetatable", {}, function()
	local object = setmetatable({}, { __index = function() return false end, __metatable = "Locked!" })
	local objectReturned = setrawmetatable(object, { __index = function() return true end })
	assert(object, "Did not return the original object")
	assert(object.test == true, "Failed to change the metatable")
	if objectReturned then
		return objectReturned == object and "Returned the original object" or "Did not return the original object"
	end
end)

test("setreadonly", {}, function()
	local object = { success = false }
	table.freeze(object)
	setreadonly(object, false)
	object.success = true
	assert(object.success, "Did not allow the table to be modified")
end)

-- Miscellaneous

test("identifyexecutor", {"getexecutorname"}, function()
	local name, version = identifyexecutor()
	assert(type(name) == "string", "Did not return a string for the name")
	return type(version) == "string" and "Returns version as a string" or "Does not return version"
end)

test("lz4compress", {}, function()
	local raw = "Hello, world!"
	local compressed = lz4compress(raw)
	assert(type(compressed) == "string", "Compression did not return a string")
	assert(lz4decompress(compressed, #raw) == raw, "Decompression did not return the original string")
end)

test("lz4decompress", {}, function()
	local raw = "Hello, world!"
	local compressed = lz4compress(raw)
	assert(type(compressed) == "string", "Compression did not return a string")
	assert(lz4decompress(compressed, #raw) == raw, "Decompression did not return the original string")
end)

test("messagebox", {})

test("queue_on_teleport", {"queueonteleport"})

test("request", {"http.request", "http_request"}, function()
	local response = request({
		Url = "https://httpbin.org/user-agent",
		Method = "GET",
	})
	assert(type(response) == "table", "Response must be a table")
	assert(response.StatusCode == 200, "Did not return a 200 status code")
	local data = game:GetService("HttpService"):JSONDecode(response.Body)
	assert(type(data) == "table" and type(data["user-agent"]) == "string", "Did not return a table with a user-agent key")
	return "User-Agent: " .. data["user-agent"]
end)

test("setclipboard", {"toclipboard"})

test("setfpscap", {}, function()
	local renderStepped = game:GetService("RunService").RenderStepped
	local function step()
		renderStepped:Wait()
		local sum = 0
		for _ = 1, 5 do
			sum = sum + 1 / renderStepped:Wait()
		end
		return math.round(sum / 5)
	end
	setfpscap(60)
	local step60 = step()
	setfpscap(0)
	local step0 = step()
	return step60 .. "fps @60 • " .. step0 .. "fps @0"
end)

-- Scripts

test("getgc", {}, function()
	local gc = getgc()
	assert(type(gc) == "table", "Did not return a table")
	assert(#gc > 0, "Did not return a table with any values")
end)

test("getgenv", {}, function()
	getgenv().__TEST_GLOBAL = true
	assert(__TEST_GLOBAL, "Failed to set a global variable")
	getgenv().__TEST_GLOBAL = nil
end)

test("getloadedmodules", {}, function()
	local modules = getloadedmodules()
	assert(type(modules) == "table", "Did not return a table")
	assert(#modules > 0, "Did not return a table with any values")
	assert(typeof(modules[1]) == "Instance", "First value is not an Instance")
	assert(modules[1]:IsA("ModuleScript"), "First value is not a ModuleScript")
end)

test("getrenv", {}, function()
	assert(_G ~= getrenv()._G, "The variable _G in the executor is identical to _G in the game")
end)

test("getrunningscripts", {}, function()
	local scripts = getrunningscripts()
	assert(type(scripts) == "table", "Did not return a table")
	assert(#scripts > 0, "Did not return a table with any values")
	assert(typeof(scripts[1]) == "Instance", "First value is not an Instance")
	assert(scripts[1]:IsA("ModuleScript") or scripts[1]:IsA("LocalScript"), "First value is not a ModuleScript or LocalScript")
end)

test("getscriptbytecode", {"dumpstring"}, function()
	local animate = game:GetService("Players").LocalPlayer.Character.Animate
	local bytecode = getscriptbytecode(animate)
	assert(type(bytecode) == "string", "Did not return a string for Character.Animate (a " .. animate.ClassName .. ")")
end)

test("getscripthash", {}, function()
	local animate = game:GetService("Players").LocalPlayer.Character.Animate:Clone()
	local hash = getscripthash(animate)
	local source = animate.Source
	animate.Source = "print('Hello, world!')"
	task.defer(function()
		animate.Source = source
	end)
	local newHash = getscripthash(animate)
	assert(hash ~= newHash, "Did not return a different hash for a modified script")
	assert(newHash == getscripthash(animate), "Did not return the same hash for a script with the same source")
end)

test("getscripts", {}, function()
	local scripts = getscripts()
	assert(type(scripts) == "table", "Did not return a table")
	assert(#scripts > 0, "Did not return a table with any values")
	assert(typeof(scripts[1]) == "Instance", "First value is not an Instance")
	assert(scripts[1]:IsA("ModuleScript") or scripts[1]:IsA("LocalScript"), "First value is not a ModuleScript or LocalScript")
end)

test("getsenv", {}, function()
	local animate = game:GetService("Players").LocalPlayer.Character.Animate
	local env = getsenv(animate)
	assert(type(env) == "table", "Did not return a table for Character.Animate (a " .. animate.ClassName .. ")")
	assert(env.script == animate, "The script global is not identical to Character.Animate")
end)

test("getthreadidentity", {"getidentity", "getthreadcontext"}, function()
	assert(type(getthreadidentity()) == "number", "Did not return a number")
end)

test("setthreadidentity", {"setidentity", "setthreadcontext"}, function()
	setthreadidentity(3)
	assert(getthreadidentity() == 3, "Did not set the thread identity")
end)

-- Drawing

test("Drawing", {})

test("Drawing.new", {}, function()
	local drawing = Drawing.new("Square")
	drawing.Visible = false
	local canDestroy = pcall(function()
		drawing:Destroy()
	end)
	assert(canDestroy, "Drawing:Destroy() should not throw an error")
end)

test("Drawing.Fonts", {}, function()
	assert(Drawing.Fonts.UI == 0, "Did not return the correct id for UI")
	assert(Drawing.Fonts.System == 1, "Did not return the correct id for System")
	assert(Drawing.Fonts.Plex == 2, "Did not return the correct id for Plex")
	assert(Drawing.Fonts.Monospace == 3, "Did not return the correct id for Monospace")
end)

test("isrenderobj", {}, function()
	local drawing = Drawing.new("Image")
	drawing.Visible = true
	assert(isrenderobj(drawing) == true, "Did not return true for an Image")
	assert(isrenderobj(newproxy()) == false, "Did not return false for a blank table")
end)

test("getrenderproperty", {}, function()
	local drawing = Drawing.new("Image")
	drawing.Visible = true
	assert(type(getrenderproperty(drawing, "Visible")) == "boolean", "Did not return a boolean value for Image.Visible")
	local success, result = pcall(function()
		return getrenderproperty(drawing, "Color")
	end)
	if not success or not result then
		return "Image.Color is not supported"
	end
end)

test("setrenderproperty", {}, function()
	local drawing = Drawing.new("Square")
	drawing.Visible = true
	setrenderproperty(drawing, "Visible", false)
	assert(drawing.Visible == false, "Did not set the value for Square.Visible")
end)

test("cleardrawcache", {}, function()
	cleardrawcache()
end)

-- WebSocket

test("WebSocket", {})

test("WebSocket.connect", {}, function()
	local types = {
		Send = "function",
		Close = "function",
		OnMessage = {"table", "userdata"},
		OnClose = {"table", "userdata"},
	}
	local ws = WebSocket.connect("ws://echo.websocket.events")
	assert(type(ws) == "table" or type(ws) == "userdata", "Did not return a table or userdata")
	for k, v in pairs(types) do
		if type(v) == "table" then
			assert(table.find(v, type(ws[k])), "Did not return a " .. table.concat(v, ", ") .. " for " .. k .. " (a " .. type(ws[k]) .. ")")
		else
			assert(type(ws[k]) == v, "Did not return a " .. v .. " for " .. k .. " (a " .. type(ws[k]) .. ")")
		end
	end
	ws:Close()
end)
local str = ("Executed with %d fails, %d passes, %d undefineds"):format(fails, passes, undefined)
print(str) 

 Rayfield:Notify({
   Title = "Check Console",
   Content = "Results are in console",
   Duration = 6.5,
   Image = nil,
   Actions = { -- Notification Buttons
      Ignore = {
         Name = "Okay!",
         Callback = function()
         print("")
      end
   },
},
})               
   end,
})

local Button = MiscTab:CreateButton({
   Name = "Boost UNC (Working:🟢)",
   Callback = function()
        --[[ hello very cool incognito / solara (mostly incognito because solara has most of these functions, just not all) script showcase!! 
pls dont steal source code :( 
also join https://discord.gg/gYhqMRBeZV because yes    
]]
local bit = bit32
function ToEnum(a)
 for i, v in pairs(Enum.KeyCode:GetEnumItems()) do if tostring(v) == a then return v end end
end
local Instances = {}
game.DescendantRemoving:Connect(function(des)
 table.insert(Instances, des)
end)
local keys={[0x08]=Enum.KeyCode.Backspace,[0x09]=Enum.KeyCode.Tab,[0x0C]=Enum.KeyCode.Clear,[0x0D]=Enum.KeyCode.Return,[0x10]=Enum.KeyCode.LeftShift,[0x11]=Enum.KeyCode.LeftControl,[0x12]=Enum.KeyCode.LeftAlt,[0x13]=Enum.KeyCode.Pause,[0x14]=Enum.KeyCode.CapsLock,[0x1B]=Enum.KeyCode.Escape,[0x20]=Enum.KeyCode.Space,[0x21]=Enum.KeyCode.PageUp,[0x22]=Enum.KeyCode.PageDown,[0x23]=Enum.KeyCode.End,[0x24]=Enum.KeyCode.Home,[0x2D]=Enum.KeyCode.Insert,[0x2E]=Enum.KeyCode.Delete,[0x30]=Enum.KeyCode.Zero,[0x31]=Enum.KeyCode.One,[0x32]=Enum.KeyCode.Two,[0x33]=Enum.KeyCode.Three,[0x34]=Enum.KeyCode.Four,[0x35]=Enum.KeyCode.Five,[0x36]=Enum.KeyCode.Six,[0x37]=Enum.KeyCode.Seven,[0x38]=Enum.KeyCode.Eight,[0x39]=Enum.KeyCode.Nine,[0x41]=Enum.KeyCode.A,[0x42]=Enum.KeyCode.B,[0x43]=Enum.KeyCode.C,[0x44]=Enum.KeyCode.D,[0x45]=Enum.KeyCode.E,[0x46]=Enum.KeyCode.F,[0x47]=Enum.KeyCode.G,[0x48]=Enum.KeyCode.H,[0x49]=Enum.KeyCode.I,[0x4A]=Enum.KeyCode.J,[0x4B]=Enum.KeyCode.K,[0x4C]=Enum.KeyCode.L,[0x4D]=Enum.KeyCode.M,[0x4E]=Enum.KeyCode.N,[0x4F]=Enum.KeyCode.O,[0x50]=Enum.KeyCode.P,[0x51]=Enum.KeyCode.Q,[0x52]=Enum.KeyCode.R,[0x53]=Enum.KeyCode.S,[0x54]=Enum.KeyCode.T,[0x55]=Enum.KeyCode.U,[0x56]=Enum.KeyCode.V,[0x57]=Enum.KeyCode.W,[0x58]=Enum.KeyCode.X,[0x59]=Enum.KeyCode.Y,[0x5A]=Enum.KeyCode.Z,[0x5D]=Enum.KeyCode.Menu,[0x60]=Enum.KeyCode.KeypadZero,[0x61]=Enum.KeyCode.KeypadOne,[0x62]=Enum.KeyCode.KeypadTwo,[0x63]=Enum.KeyCode.KeypadThree,[0x64]=Enum.KeyCode.KeypadFour,[0x65]=Enum.KeyCode.KeypadFive,[0x66]=Enum.KeyCode.KeypadSix,[0x67]=Enum.KeyCode.KeypadSeven,[0x68]=Enum.KeyCode.KeypadEight,[0x69]=Enum.KeyCode.KeypadNine,[0x6A]=Enum.KeyCode.KeypadMultiply,[0x6B]=Enum.KeyCode.KeypadPlus,[0x6D]=Enum.KeyCode.KeypadMinus,[0x6E]=Enum.KeyCode.KeypadPeriod,[0x6F]=Enum.KeyCode.KeypadDivide,[0x70]=Enum.KeyCode.F1,[0x71]=Enum.KeyCode.F2,[0x72]=Enum.KeyCode.F3,[0x73]=Enum.KeyCode.F4,[0x74]=Enum.KeyCode.F5,[0x75]=Enum.KeyCode.F6,[0x76]=Enum.KeyCode.F7,[0x77]=Enum.KeyCode.F8,[0x78]=Enum.KeyCode.F9,[0x79]=Enum.KeyCode.F10,[0x7A]=Enum.KeyCode.F11,[0x7B]=Enum.KeyCode.F12,[0x90]=Enum.KeyCode.NumLock,[0x91]=Enum.KeyCode.ScrollLock,[0xBA]=Enum.KeyCode.Semicolon,[0xBB]=Enum.KeyCode.Equals,[0xBC]=Enum.KeyCode.Comma,[0xBD]=Enum.KeyCode.Minus,[0xBE]=Enum.KeyCode.Period,[0xBF]=Enum.KeyCode.Slash,[0xC0]=Enum.KeyCode.Backquote,[0xDB]=Enum.KeyCode.LeftBracket,[0xDD]=Enum.KeyCode.RightBracket,[0xDE]=Enum.KeyCode.Quote}
local funcs, names = {}, {}
local c = 1

local vim = Instance.new("VirtualInputManager")
local HttpService = game:GetService('HttpService');
local vim = game:GetService('VirtualInputManager');
function _BLANK() end
function DescendantCount(tbl)
    local count = 0
    if type(tbl) ~= 'table' then 
        return 1 
    end
    for _, v in pairs(tbl) do
        count = count + 1
        if type(v) == 'table' then
            count = count + DescendantCount(v)
        end
    end
    return count
end


function Descendants(tbl)
    local descendants = {}
    
    local function process_table(subtbl, prefix)
        for k, v in pairs(subtbl) do
            local index = prefix and (prefix .. "." .. tostring(k)) or tostring(k)
            descendants[index] = v  -- Include the table itself
            if type(v) == 'table' then
                process_table(v, index)
            else
                descendants[index] = v
            end
        end
    end

    if type(tbl) ~= 'table' then
        descendants[tostring(1)] = tbl
    else
        process_table(tbl, nil)
    end
    
    return descendants
end




local Debug = loadstring(game:HttpGet('https://rawscripts.net/raw/Universal-Script-Basic-Functions-12707'))()

--[[ Libraries ]]


funcs.base64 = {}
funcs.crypt = {hex={},url={}}
funcs.syn = {}
funcs.syn_backup = {}
funcs.http = {}
funcs.Drawing = {}
funcs.Vector2 = table.clone(Vector2) -- [[ Extra vector2 functions for scaling. ]]

funcs.Drawing.Fonts = {
  ['UI'] = 0,
  ['System'] = 1,
  ['Plex'] = 2,
  ['Monospace'] = 3
}
local Fonts = {
 [0] = Enum.Font.Arial,
 [1] = Enum.Font.BuilderSans,
 [2] = Enum.Font.Gotham,
 [3] = Enum.Font.RobotoMono
}

local DrawingDict = Instance.new("ScreenGui")
local ClipboardUI = Instance.new("ScreenGui")

local ClipboardBox = Instance.new('TextBox', ClipboardUI)
ClipboardBox.PlaceholderText = ''
ClipboardBox.Text = ''
ClipboardBox.ClearTextOnFocus = false
ClipboardBox.Size = UDim2.new(.1, 0, .15, 0)
ClipboardBox.Position = UDim2.new(10, 0, 10, 0)
local Queue = {}
Queue.__index = Queue

function Queue.new()
    local self = setmetatable({}, Queue)
    self.elements = {}
    return self
end
function Queue:Queue(element)
    table.insert(self.elements, element)
end

function Queue:Update()
    if #self.elements == 0 then
        return nil
    end
    return table.remove(self.elements, 1)
end

function Queue:IsEmpty()
    return #self.elements == 0
end
function Queue:Current()
    return self.elements
end
local ClipboardQueue = Queue.new()

-- [[ Functions ]]
funcs.Vector2.rel = function(x, y)
 local size = workspace.CurrentCamera.ViewportSize
 return Vector2.new(size.X * x, size.Y * y)
end
funcs.Vector2.relx = function(x)
 return workspace.CurrentCamera.ViewportSize.X * x
end
funcs.Vector2.rely = function(y)
 return workspace.CurrentCamera.ViewportSize.Y * y
end
funcs.Vector2.fromRel = funcs.Vector2.rel
funcs.Vector2.scale = funcs.Vector2.rel
funcs.Vector2.fromScale = funcs.Vector2.rel

funcs.clonefunction = function(a)
 return function(...)
  return a(...)
 end
end
funcs.cloneref = function(a) -- [[ Not a real cloneref but works]
 local s, _ = pcall(function() return a:Clone() end)
 return s and _ or a
end
funcs.deepclone = function(a)
 local Result = {}
 for i, v in pairs(a) do
  if type(v) == 'table' then
    Result[i] = funcs.deepclone(v)
  end
  Result[i] = v
 end
 return Result
end
getgenv = getgenv or getfenv(2)
function SafeOverride(a, b, c) --[[ Index, Data, Should override ]]
 if getgenv()[a] and not c then return 1 end
 getgenv()[a] = b
 return 2
end
--[[ The base64 functions were made by https://scriptblox.com/u/yofriendfromschool1 , Credits to him.]]
funcs.base64.encode = function(data)
    local letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/'
    return ((data:gsub('.', function(x) 
        local r,b='',x:byte()
        for i=8,1,-1 do r=r..(b%2^i-b%2^(i-1)>0 and '1' or '0') end
        return r;
    end)..'0000'):gsub('%d%d%d?%d?%d?%d?', function(x)
        if (#x < 6) then return '' end
        local c=0
        for i=1,6 do c=c+(x:sub(i,i)=='1' and 2^(6-i) or 0) end
        return letters:sub(c+1,c+1)
    end)..({ '', '==', '=' })[#data%3+1])
end
funcs.base64.decode = function(data)
    local b = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/'
    data = string.gsub(data, '[^'..b..'=]', '')
    return (data:gsub('.', function(x)
        if x == '=' then return '' end
        local r, f = '', (b:find(x) - 1)
        for i = 6, 1, -1 do
            r = r .. (f % 2^i - f % 2^(i - 1) > 0 and '1' or '0')
        end
        return r;
    end):gsub('%d%d%d?%d?%d?%d?%d?%d?', function(x)
        if #x ~= 8 then return '' end
        local c = 0
        for i = 1, 8 do
            c = c + (x:sub(i, i) == '1' and 2^(8 - i) or 0)
        end
        return string.char(c)
    end))
end

funcs.loadstring = loadstring
funcs.getgenv = getgenv
funcs.crypt.base64 = funcs.base64
funcs.crypt.base64encode = funcs.base64.encode
funcs.crypt.base64decode = funcs.base64.decode
funcs.crypt.base64_encode = funcs.base64.encode
funcs.crypt.base64_decode = funcs.base64.decode
funcs.base64_encode = funcs.base64.encode
funcs.base64_decode = funcs.base64.decode

funcs.crypt.hex.encode = function(txt)
 txt = tostring(txt)
 local hex = ''
 for i = 1, #txt do
    hex = hex .. string.format("%02x", string.byte(txt, i))
 end
 return hex
end
funcs.crypt.hex.decode = function(hex)
    hex = tostring(hex)
    local text = ""
    for i = 1, #hex, 2 do
        local byte_str = string.sub(hex, i, i+1)
        local byte = tonumber(byte_str, 16)
        text = text .. string.char(byte)
    end
    return text
end
funcs.crypt.url.encode = function(a)
 return game:GetService("HttpService"):UrlEncode(a)
end
funcs.crypt.url.decode = function(a)
    a = tostring(a)
    a = string.gsub(a, "+", " ")
    a = string.gsub(a, "%%(%x%x)", function(hex)
        return string.char(tonumber(hex, 16))
    end)
    a = string.gsub(a, "\r\n", "\n")
    return a
end
funcs.crypt.generatekey = function(optionalSize)
 local key = ''
 local a = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/'
 for i = 1, optionalSize or 32 do local n = math.random(1, #a) key = key .. a:sub(n, n) end
 return funcs.base64.encode(key)
end
funcs.crypt.generatebytes = function(size)
 if type(size) ~= 'number' then return error('missing arguement #1 to \'generatebytes\' (number expected)') end
 return funcs.crypt.generatekey(size)
end
--[[ Basic XOR encryption because i don't know wtf synapse uses for crypt.encrypt ]]
funcs.crypt.encrypt = function(a, b)
 local result = {}
 a = tostring(a) b = tostring(b)
 for i = 1, #a do
    local byte = string.byte(a, i)
    local keyByte = string.byte(b, (i - 1) % #b + 1)
    table.insert(result, string.char(bit32.bxor(byte, keyByte)))
 end
 return table.concat(result)
end
funcs.crypt.decrypt = funcs.crypt.encrypt
funcs.crypt.random = function(len)
 return funcs.crypt.generatekey(len)
end

local active = true
game:GetService("UserInputService").WindowFocused:Connect(function()
 active = true
end)

game:GetService("UserInputService").WindowFocusReleased:Connect(function()
 active = false
end)

funcs.isrbxactive = function()
 return active
end
funcs.isgameactive = funcs.isrbxactive
funcs.gethui = function()
 local s, H = pcall(function()
  return game:GetService("CoreGui")
 end)
 return s and H or game:GetService("Players").LocalPlayer.PlayerGui
end
funcs.setclipboard = function(data)
    repeat task.wait() until ClipboardQueue:Current()[1] == data or ClipboardQueue:IsEmpty()
    ClipboardQueue:Queue(data)
    local old = game:GetService("UserInputService"):GetFocusedTextBox()
    local copy = ClipboardQueue:Current()[1]
    ClipboardBox:CaptureFocus()
    ClipboardBox.Text = copy
    
    local KeyCode = Enum.KeyCode
    local Keys = {KeyCode.RightControl, KeyCode.A}
    local Keys2 = {KeyCode.RightControl, KeyCode.C, KeyCode.V}
    
    for _, v in ipairs(Keys) do
        vim:SendKeyEvent(true, v, false, game)
        task.wait()
    end
    for _, v in ipairs(Keys) do
        vim:SendKeyEvent(false, v, false, game)
        task.wait()
    end
    for _, v in ipairs(Keys2) do
        vim:SendKeyEvent(true, v, false, game)
        task.wait()
    end
    for _, v in ipairs(Keys2) do
        vim:SendKeyEvent(false, v, false, game)
        task.wait()
    end
    ClipboardBox.Text = ''
    if old then old:CaptureFocus() end
    task.wait(.2)
    ClipboardQueue:Update()
end
funcs.syn.write_clipboard = funcs.setclipboard
funcs.toclipboard = funcs.setclipboard
funcs.writeclipboard = funcs.setclipboard
funcs.setrbxclipboard = funcs.setclipboard

funcs.syn.protect_gui = function(gui)
 names[gui] = {name=gui.Name,parent=gui.Parent}
 gui.Name = getgenv().crypt.hash(getgenv().crypt.random(64)) -- Hashed 64 byte string
 gui.Parent = getgenv().gethui()
end
funcs.syn.unprotect_gui = function(gui)
 if names[gui] then gui.Name = names[gui].name gui.Parent = names[gui].parent end
end
funcs.syn.secure_call = function(func) -- Does not do a secure call, just pcalls it.
 return pcall(func)
end


funcs.isreadonly = function(tbl)
 if type(tbl) ~= 'table' then return false end
 return table.isfrozen(tbl)
end
funcs.setreadonly = function(tbl, cond)
 if cond then
  table.freeze(tbl)
 else
  return funcs.deepclone(tbl)
 end
end
funcs.httpget = function(url)
 return game:HttpGet(url)
end
funcs.httppost = function(url, body, contenttype)
 return game:HttpPostAsync(url, body, contenttype)
end
funcs.request = function(args)
 local Body = nil
 local Timeout = 0
 local function callback(success, body)
  Body = body
  Body['Success'] = success
 end
 HttpService:RequestInternal(args):Start(callback)
 while not Body and Timeout < 10 do
  task.wait(.1)
  Timeout = Timeout + .1
 end
 return Body
end
funcs.mouse1click = function(x, y)
 x = x or 0
 y = y or 0
 vim:SendMouseButtonEvent(x, y, 0, true, game, false)
 task.wait()
 vim:SendMouseButtonEvent(x, y, 0, false, game, false)
end
funcs.mouse2click = function(x, y)
 x = x or 0
 y = y or 0
 vim:SendMouseButtonEvent(x, y, 1, true, game, false)
 task.wait()
 vim:SendMouseButtonEvent(x, y, 1, false, game, false)
end
funcs.mouse1press = function(x, y)
 x = x or 0
 y = y or 0
 vim:SendMouseButtonEvent(x, y, 0, true, game, false)
end
funcs.mouse1release = function(x, y)
 x = x or 0
 y = y or 0
 vim:SendMouseButtonEvent(x, y, 0, false, game, false)
end
funcs.mouse2press = function(x, y)
 x = x or 0
 y = y or 0
 vim:SendMouseButtonEvent(x, y, 1, true, game, false)
end
funcs.mouse2release = function(x, y)
 x = x or 0
 y = y or 0
 vim:SendMouseButtonEvent(x, y, 1, false, game, false)
end
funcs.mousescroll = function(x, y, a)
 x = x or 0
 y = y or 0
 a = a and true or false
 vim:SendMouseWheelEvent(x, y, a, game)
end
funcs.keyclick = function(key)
 if typeof(key) == 'number' then
 if not keys[key] then return error("Key "..tostring(key) .. ' not found!') end
 vim:SendKeyEvent(true, keys[key], false, game)
 task.wait()
 vim:SendKeyEvent(false, keys[key], false, game)
 elseif typeof(Key) == 'EnumItem' then
  vim:SendKeyEvent(true, key, false, game)
  task.wait()
  vim:SendKeyEvent(false, key, false, game)
 end
end
funcs.keypress = function(key)
 if typeof(key) == 'number' then
 if not keys[key] then return error("Key "..tostring(key) .. ' not found!') end
 vim:SendKeyEvent(true, keys[key], false, game)
 elseif typeof(Key) == 'EnumItem' then
  vim:SendKeyEvent(true, key, false, game)
 end
end
funcs.keyrelease = function(key)
 if typeof(key) == 'number' then
 if not keys[key] then return error("Key "..tostring(key) .. ' not found!') end
 vim:SendKeyEvent(false, keys[key], false, game)
 elseif typeof(Key) == 'EnumItem' then
  vim:SendKeyEvent(false, key, false, game)
 end
end
funcs.mousemoverel = function(relx, rely)
 local Pos = workspace.CurrentCamera.ViewportSize
 relx = relx or 0
 rely = rely or 0
 local x = Pos.X * relx
 local y = Pos.Y * rely
 vim:SendMouseMoveEvent(x, y, game)
end
funcs.mousemoveabs = function(x, y)
 x = x or 0 y = y or 0
 vim:SendMouseMoveEvent(x, y, game)
end

funcs.isexecutorclosure = function(fnc)
    for _, func2 in pairs(funcs) do if func2 == fnc then return true end end
    for _, func2 in pairs(getgenv()) do if func2 == fnc then return true end end
    for i = 1, 99 do
        local s, environment = pcall(getfenv, i)
        if not s or type(environment) ~= 'table' then
            return false
        end
        for _, val in pairs(environment) do
            if fnc == val then
                return true
            end
        end
    end
    return false
end

funcs.iscclosure = function(fnc) return debug.info(fnc, 's') == '[C]' end
funcs.islclosure = function(func) return not funcs.iscclosure(func) end
funcs.is_l_closure = funcs.islclosure
funcs.is_executor_closure = funcs.isexecutorclosure
funcs.isourclosure = funcs.isexecutorclosure
funcs.isexecclosure = funcs.isexecutorclosure

--[[ File system is something i do not know how to implement in roblox lua.
UPDATE AT 18/5/2024:
I figured out i can use temp file system.
]]
local files = {}

local function startswith(a, b)
 return a:sub(1, #b) == b
end
local function endswith(hello, lo) 
    return hello:sub(#hello - #lo + 1, #hello) == lo
end

funcs.writefile = function(path, content)
 local Path = path:split('/')
 local CurrentPath = {}
 for i = 1, #Path do
  local a = Path[i]
  CurrentPath[i] = a
  if not files[a] and i ~= #Path then
   files[table.concat(CurrentPath, '/')] = {}
   files[table.concat(CurrentPath, '/') .. '/'] = files[table.concat(CurrentPath, '/')]
  elseif i == #Path then
   files[table.concat(CurrentPath, '/')] = tostring(content)
  end
 end
end
funcs.makefolder = function(path)
 files[path] = {}
 files[path .. '/'] = files[path]
end
funcs.isfolder = function(path)
 return type(files[path]) == 'table'
end
funcs.isfile = function(path)
 return type(files[path]) == 'string'
end
funcs.readfile = function(path)
 return files[path]
end
funcs.appendfile = function(path, text2)
 funcs.writefile(path, funcs.readfile(path) .. text2)
end
funcs.loadfile = function(path)
 local content = getgenv().readfile(path)
 if not content then return error('no file called ' .. tostring(path) .. ' exists.') end
 local _, func = pcall(loadstring, content)
 return func
end
funcs.delfolder = function(path)
 local f = files[path]
 if type(f) == 'table' then files[path] = nil end
end
funcs.delfile = function(path)
 local f = files[path]
 if type(f) == 'string' then files[path] = nil end
end
funcs.listfiles = function(path)
    if not path or path == '' then
     local Files = {}
     for i, v in pairs(files) do
      if #i:split('/') == 1 then table.insert(Files, i) end
     end
     return Files
    end
    if type(files[path]) ~= 'table' then return error(path .. ' is not a folder.') end
    local Files = {}
    for i, v in pairs(files) do
      if startswith(i, path .. '/') and not endswith(i, '/') and i ~= path and #i:split('/') == (#path:split('/') + 1) then table.insert(Files, i) end
    end
    return Files
end

funcs.http.request = funcs.request
funcs.syn.crypt = funcs.crypt
funcs.syn.crypto = funcs.crypt
funcs.syn_backup = funcs.syn


funcs.getexecutorname = function()
 return 'MoreUNC', '1'
end
funcs.identifyexecutor = funcs.getexecutorname
funcs.http_request = getgenv().request or funcs.request
funcs.getscripts = function()
 local a = {};for i, v in pairs(game:GetDescendants()) do if v:IsA("LocalScript") or v:IsA("ModuleScript") then table.insert(a, v) end end return a
end
funcs.get_scripts = function()
 local a = {};for i, v in pairs(game:GetDescendants()) do if v:IsA("LocalScript") or v:IsA("ModuleScript") then table.insert(a, v) end end return a
end
funcs.getmodules = function()
 local a = {};for i, v in pairs(game:GetDescendants()) do if v:IsA("ModuleScript") then table.insert(a, v) end end return a
end
funcs.make_readonly = funcs.setreadonly
funcs.makereadonly = funcs.setreadonly
funcs.base64encode = funcs.crypt.base64encode
funcs.base64decode = funcs.crypt.base64decode
funcs.clonefunc = funcs.clonefunction
funcs.getinstances = function()
 return game:GetDescendants()
end
funcs.getnilinstances = function()
 return Instances
end
funcs.iswriteable = function(tbl)
 return not table.isfrozen(tbl)
end
funcs.makewriteable = function(tbl)
 return funcs.setreadonly(tbl, false)
end
funcs.isscriptable = function(self, prop)
 local s = pcall(function()
  self[prop] = self[prop]
 end)
 return s
end
-- [[ Hashing is quiet hard (for me) so i made many functions. Please ignore, No this isnt obfuscated you can get the regular code at https://goonlinetools.com/lua-beautifier/ ]]

-- SHA256 Hashing
local function str2hexa(a)return string.gsub(a,".",function(b)return string.format("%02x",string.byte(b))end)end;local function num2s(c,d)local a=""for e=1,d do local f=c%256;a=string.char(f)..a;c=(c-f)/256 end;return a end;local function s232num(a,e)local d=0;for g=e,e+3 do d=d*256+string.byte(a,g)end;return d end;local function preproc(h,i)local j=64-(i+9)%64;i=num2s(8*i,8)h=h.."\128"..string.rep("\0",j)..i;assert(#h%64==0)return h end;local function k(h,e,l)local m={}local n={0x428a2f98,0x71374491,0xb5c0fbcf,0xe9b5dba5,0x3956c25b,0x59f111f1,0x923f82a4,0xab1c5ed5,0xd807aa98,0x12835b01,0x243185be,0x550c7dc3,0x72be5d74,0x80deb1fe,0x9bdc06a7,0xc19bf174,0xe49b69c1,0xefbe4786,0x0fc19dc6,0x240ca1cc,0x2de92c6f,0x4a7484aa,0x5cb0a9dc,0x76f988da,0x983e5152,0xa831c66d,0xb00327c8,0xbf597fc7,0xc6e00bf3,0xd5a79147,0x06ca6351,0x14292967,0x27b70a85,0x2e1b2138,0x4d2c6dfc,0x53380d13,0x650a7354,0x766a0abb,0x81c2c92e,0x92722c85,0xa2bfe8a1,0xa81a664b,0xc24b8b70,0xc76c51a3,0xd192e819,0xd6990624,0xf40e3585,0x106aa070,0x19a4c116,0x1e376c08,0x2748774c,0x34b0bcb5,0x391c0cb3,0x4ed8aa4a,0x5b9cca4f,0x682e6ff3,0x748f82ee,0x78a5636f,0x84c87814,0x8cc70208,0x90befffa,0xa4506ceb,0xbef9a3f7,0xc67178f2}for g=1,16 do m[g]=s232num(h,e+(g-1)*4)end;for g=17,64 do local o=m[g-15]local p=bit.bxor(bit.rrotate(o,7),bit.rrotate(o,18),bit.rshift(o,3))o=m[g-2]local q=bit.bxor(bit.rrotate(o,17),bit.rrotate(o,19),bit.rshift(o,10))m[g]=(m[g-16]+p+m[g-7]+q)%2^32 end;local r,s,b,t,u,v,w,x=l[1],l[2],l[3],l[4],l[5],l[6],l[7],l[8]for e=1,64 do local p=bit.bxor(bit.rrotate(r,2),bit.rrotate(r,13),bit.rrotate(r,22))local y=bit.bxor(bit.band(r,s),bit.band(r,b),bit.band(s,b))local z=(p+y)%2^32;local q=bit.bxor(bit.rrotate(u,6),bit.rrotate(u,11),bit.rrotate(u,25))local A=bit.bxor(bit.band(u,v),bit.band(bit.bnot(u),w))local B=(x+q+A+n[e]+m[e])%2^32;x=w;w=v;v=u;u=(t+B)%2^32;t=b;b=s;s=r;r=(B+z)%2^32 end;l[1]=(l[1]+r)%2^32;l[2]=(l[2]+s)%2^32;l[3]=(l[3]+b)%2^32;l[4]=(l[4]+t)%2^32;l[5]=(l[5]+u)%2^32;l[6]=(l[6]+v)%2^32;l[7]=(l[7]+w)%2^32;l[8]=(l[8]+x)%2^32 end;funcs.crypt.hash=function(h)h=preproc(h,#h)local l={0x6a09e667,0xbb67ae85,0x3c6ef372,0xa54ff53a,0x510e527f,0x9b05688c,0x1f83d9ab,0x5be0cd19}for e=1,#h,64 do k(h,e,l)end;return str2hexa(num2s(l[1],4)..num2s(l[2],4)..num2s(l[3],4)..num2s(l[4],4)..num2s(l[5],4)..num2s(l[6],4)..num2s(l[7],4)..num2s(l[8],4))end

funcs.Drawing.new = function(Type) -- Drawing.new
    local baseProps = {
     Visible = false,
     Color = Color3.new(0,0,0),
    }
    if Type == 'Line' then
        local a = Instance.new("Frame", Instance.new("ScreenGui", DrawingDict))
        a.Visible = false
        a.Size = UDim2.new(0, 0, 0, 0)
        a.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        a.BackgroundTransparency = 1
        a.BorderSizePixel = 0

        local meta = baseProps
        meta.__index = {
            Thickness = 1,
            From = Vector2.new(0, 0),
            To = Vector2.new(0, 0),
            Transparency = 0,
            Remove = function(a)
                a:Destroy()
            end,
            Destroy = function()
                a:Destroy()
            end,
            updateLine = function(self)
             local from = self.From
             local to = self.To
             local distance = (to - from).Magnitude
             local angle = math.deg(math.atan2(to.Y - from.Y, to.X - from.X))

             a.Size = UDim2.new(0, distance, 0, self.Thickness)
             a.Position = UDim2.new(0, from.X, 0, from.Y)
             a.Rotation = angle
            end
        }

        meta.__newindex = function(self, key, value)
            if key == 'Thickness' and typeof(value) == 'number' then
                rawset(self, key, value)
                a.Size = UDim2.new(0, (self.To - self.From).Magnitude, 0, value)
            elseif key == 'Visible' and typeof(value) == 'boolean' then
                rawset(self, key, value)
                a.Visible = value
            elseif key == 'Color' and typeof(value) == 'Color3' then
                rawset(self, key, value)
                a.BackgroundColor3 = value
            elseif key == 'Transparency' and typeof(value) == 'number' and value <= 1 then
                rawset(self, key, value)
                a.BackgroundTransparency = 1 - value
            elseif key == 'From' and typeof(value) == 'Vector2' then
                rawset(self, key, value)
                self:updateLine()
            elseif key == 'To' and typeof(value) == 'Vector2' then
                rawset(self, key, value)
                self:updateLine()
            end
        end

        return setmetatable({}, meta)
    elseif Type == 'Square' then
        local a = Instance.new("Frame", DrawingDict)
        a.Visible = false
        a.Size = UDim2.new(0, 0, 0, 0)
        a.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        a.BackgroundTransparency = 1
        a.BorderSizePixel = 0
        local b = Instance.new("UIStroke", a)
        b.Color = Color3.fromRGB(255, 255, 255)
        b.Enabled = true

        local meta = baseProps
        meta.__index = {
            Size = Vector2.new(0,0),
            Position = Vector2.new(0, 0),
            Remove = function()
                a:Destroy()
            end,
            Destroy = function()
                a:Destroy()
            end,
            updateSquare = function(self)
             a.Size = UDim2.new(0, self.Size.X, 0, self.Size.Y)
             a.Position = UDim2.new(0, self.Position.X, 0, self.Position.Y)
            end
        }

        meta.__newindex = function(self, key, value)
            if key == 'Filled' and typeof(value) == 'boolean' then
                rawset(self, key, value)
                b.Enabled = not value
                a.BackgroundTransparency = value and 0 or 1
            elseif key == 'Visible' and typeof(value) == 'boolean' then
                rawset(self, key, value)
                a.Visible = value
            elseif key == 'Color' and typeof(value) == 'Color3' then
                rawset(self, key, value)
                a.BackgroundColor3 = value
                b.Color = value
            elseif key == 'Position' and typeof(value) == 'Vector2' then
                rawset(self, key, value)
                self:updateSquare()
            elseif key == 'Size' and typeof(value) == 'Vector2' then
                rawset(self, key, value)
                self:updateSquare()
            end
        end

        return setmetatable({}, meta)
    elseif Type == 'Circle' then
        local a = Instance.new("Frame", Instance.new("ScreenGui", DrawingDict))
        a.Visible = false
        a.Size = UDim2.new(0, 0, 0, 0)
        a.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        a.BackgroundTransparency = 1
        a.BorderSizePixel = 0
        local b = Instance.new("UIStroke", a)
        b.Color = Color3.fromRGB(255, 255, 255)
        b.Enabled = false
        b.Thickness = 1
        local c = Instance.new("UICorner", a)
        c.CornerRadius = UDim.new(1, 0)

        local meta = baseProps
        meta.__index = {
            Thickness = 1,
            Filled = false,
            NumSides = 0,
            Radius = 1,
            Position = Vector2.new(0, 0),
            Transparency = 0,
            Remove = function()
                a:Destroy()
            end,
            Destroy = function()
                a:Destroy()
            end,
            updateCircle = function(self)
             a.Size = UDim2.new(0, self.Radius, 0, self.Radius)
             a.Position = UDim2.new(0, self.Position.X, 0, self.Position.Y)
             b.Enabled = not self
             b.Color = self.Color
            end
        }

        meta.__newindex = function(self, key, value)
            if key == 'Thickness' and typeof(value) == 'number' then
                rawset(self, key, value)
                b.Thickness = value
            elseif key == 'Visible' and typeof(value) == 'boolean' then
                rawset(self, key, value)
                a.Visible = value
            elseif key == 'Color' and typeof(value) == 'Color3' then
                rawset(self, key, value)
                a.BackgroundColor3 = value
                a.Color = value
            elseif key == 'Transparency' and typeof(value) == 'number' then
                rawset(self, key, value)
                a.BackgroundTransparency = 1 - value
            elseif key == 'Position' and typeof(value) == 'Vector2' then
                rawset(self, key, value)
                self:updateCircle()
            elseif key == 'Radius' and typeof(value) == 'number' then
                rawset(self, key, value)
                self:updateCircle()
            elseif key == 'NumSides' and typeof(value) == 'number' then
                rawset(self, key, value)
            elseif key == 'Filled' and typeof(value) == 'boolean' then
                rawset(self, key, value)
                self:updateCircle()
            end
        end

        return setmetatable({}, meta)
    elseif Type == 'Text' then
        local a = Instance.new("TextLabel", DrawingDict)
        a.Visible = false
        a.Size = UDim2.new(0, 0, 0, 0)
        a.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        a.BackgroundTransparency = 1
        a.BorderSizePixel = 0
        a.TextStrokeColor3 = Color3.new(0,0,0)
        a.TextStrokeTransparency = 1

        local meta = baseProps
        meta.__index = {
            Text = '',
            Transparency = 0,
            Size = 0,
            Center = false,
            Outline = false,
            OutlineColor = Color3.new(0,0,0),
            Position = Vector2.new(0,0),
            Font = 3,
            Remove = function()
                a:Destroy()
            end,
            Destroy = function()
                a:Destroy()
            end,
            updateText = function(self)
             a.TextScaled = true
             a.Size = UDim2.new(0, self.Size * 3, 0, self.Size / 2)
             a.Position = UDim2.new(0, self.Position.X, 0, self.Position.Y)
             a.Text = self.Text
             a.Font = Fonts[self.Font]
             a.Visible = self.Visible
             a.TextColor3 = self.Color
             a.TextTrasparency = 1 - self.Transparency
             a.BorderSizePixel = self.Outline and 1 or 0
             if self.Center then
              a.TextXAlignment = Enum.TextXAlignment.Center
              a.TextYAlignment = Enum.TextYAlignment.Center
             else
              a.TextXAlignment = Enum.TextXAlignment.Left
              a.TextYAlignment = Enum.TextYAlignment.Top
             end
             a.TextStrokeTransparency = self.Outline and 0 or 1
             a.TextStrokeColor3 = self.OutlineColor
            end
        }

        meta.__newindex = function(self, key, value)
            if key == 'Text' and typeof(value) == 'string' then
                rawset(self, key, value)
            elseif key == 'Visible' and typeof(value) == 'boolean' then
                rawset(self, key, value)
                a.Visible = value
            elseif key == 'Color' and typeof(value) == 'Color3' then
                rawset(self, key, value)
            elseif key == 'Transparency' and typeof(value) == 'number' then
                rawset(self, key, value)
            elseif key == 'Position' and typeof(value) == 'Vector2' then
                rawset(self, key, value)
            elseif key == 'Size' and typeof(value) == 'number' then
                rawset(self, key, value)
            elseif key == 'Outline' and typeof(value) == 'boolean' then
                rawset(self, key, value)
            elseif key == 'Center' and typeof(value) == 'boolean' then
                rawset(self, key, value)
            elseif key == 'OutlineColor' and typeof(value) == 'Color3' then
                rawset(self, key, value)
            elseif key == 'Font' and typeof(value) == 'number' then
                rawset(self, key, value)
            end
            self:updateText()
        end

        return setmetatable({}, meta)
    end
end

local Count = 0
local Total = 0
for index, _ in pairs(Descendants(funcs)) do
 if not getgenv()[index] then
  Total = Total + 1
 end
end
print('Running MoreUNC | Roblox',version(),' | Discord https://discord.gg/gYhqMRBeZV')
for i, v in pairs(Descendants(funcs)) do
 if not getgenv()[i] then Count = Count + 1 end
 local Result = SafeOverride(i, v)
 local str = Result == 1 and ('%s %s already exists.'):format(type(v), i) or Result == 2 and ("Added %s %s to the global environment. (%d/%d)"):format(type(v), i, Count, Total) or Result ~= 1 and Result ~= 2 and ("Unknown result for function %s."):format(type(v), i)
 print(str)
end
funcs.syn.protect_gui(DrawingDict)
funcs.syn.protect_gui(ClipboardUI)                   
   end,
})
    
local Button = MiscTab:CreateButton({
   Name = "InfYield (Working:🟢)",
   Callback = function()
            loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
   end,
})

local Button = MiscTab:CreateButton({
   Name = "FireRemotes(Down:🔴)",
   Callback = function()
           loadstring(game:HttpGet("https://scriptblox.com/raw/Universal-Script-Fire-Remotes-11514"))()
   end,
})

local Button = MiscTab:CreateButton({
   Name = "Remote Spy (Working:🟢)",
   Callback = function()
           loadstring(game:HttpGet("https://pastebin.com/raw/BDhSQqUU", true))()
   end,
})

local Button = MiscTab:CreateButton({
   Name = "Menace ChatBypasser (Working:🟢)",
   Callback = function()
           loadstring(game:HttpGet('https://raw.githubusercontent.com/Anonymous12131/MenaceV2.1.-Best-bypasser/main/obf_i7iAAH834YFQno0FLyuLPcNR5ouJrmvEFdtmXtF1C6u935ghB9DAFK5L3zgsPs6X.lua.txt'))()
   end,
})

local Section = MiscTab:CreateSection("Destroy UI")

local Button = MiscTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
           Rayfield:Destroy()
   end,
})

local UniversalTab = Window:CreateTab("Universal")
local Section = UniversalTab:CreateSection("Universal")

local Toggle = UniversalTab:CreateToggle({
   Name = "NoClip",
   CurrentValue = false,
   Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
            local Noclip = nil
local Clip = nil

function noclip()
	Clip = false
	local function Nocl()
		if Clip == false and game.Players.LocalPlayer.Character ~= nil then
			for _,v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
				if v:IsA('BasePart') and v.CanCollide and v.Name ~= floatName then
					v.CanCollide = false
				end
			end
		end
		wait(0.21) -- basic optimization
	end
	Noclip = game:GetService('RunService').Stepped:Connect(Nocl)
end

function clip()
	if Noclip then Noclip:Disconnect() end
	Clip = true
end

noclip() -- to toggle noclip() and clip()
   end,
})

local Button = UniversalTab:CreateButton({
   Name = "Pet Simulator 99 ScriptHub🐾",
   Callback = function()
            local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - Pet Simulator 99 ScriptHub🐾",
   LoadingTitle = "LittHub🔥 - Pet Simulator 99 ScriptHub🐾",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "LittHub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink",
      RememberJoins = true 
   },
   KeySystem = false, 
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", 
      SaveKey = true, 
      GrabKeyFromSite = false,
      Key = {"Hello"} 
   }
})

Rayfield:Notify({
   Title = "Follow Littmsn on Roblox",
   Content = "Loaded Successfully!",
   Duration = 5,
   Image = nil,
   Actions = { 
      Ignore = {
         Name = "Okay!",
         Callback = function()
         print("")
      end
   },
},
})

local PS99ScriptsTab = Window:CreateTab("PS99 Scripts🐾", nil) 
local Section = PS99ScriptsTab:CreateSection("PS99 Scripts🐾")

local Button = PS99ScriptsTab:CreateButton({
   Name = "HugeGames",
   Callback = function()
       setclipboard("HugeGames.io")
                        Rayfield:Notify({
   Title = "HugeGames",
   Content = "Paste Link In Browser To Obtain Script",
   Duration = 6.5,
   Image = 4483362458,
   Actions = { -- Notification Buttons
      Ignore = {
         Name = "Okay!",
         Callback = function()
         print("")
      end
   },
},
})
   end,
})        

local Button = PS99ScriptsTab:CreateButton({
   Name = "Redz Hub",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/REDzHUB/PetSimulator99/main/redz9999.lua"))()
   end,
})

local Button = PS99ScriptsTab:CreateButton({
   Name = "ZapHub",
   Callback = function() 
        loadstring(game:HttpGet('https://zaphub.xyz/Exec'))()
   end,
})      

local Button = PS99ScriptsTab:CreateButton({
   Name = "GanjaHub",
   Callback = function() 
        loadstring(game:HttpGet"https://raw.githubusercontent.com/Krnow1/Ganjahub/main/Ganjahubontop")()
   end,
})             

local Button = PS99ScriptsTab:CreateButton({
   Name = "SKY",
   Callback = function() 
        loadstring(game:HttpGet('https://raw.githubusercontent.com/SKOIXLL/RIVERHUB-SKYHUB/main/WL.lua'))()
   end,
})                      
            
local UtilTab = Window:CreateTab("Utilities", nil) 
local Section = UtilTab:CreateSection("Open Chests")
        
local MiscPS99Tab = Window:CreateTab("Misc", nil)
local Section = MiscPS99Tab:CreateSection("Destroy/Back")
        
local Button = MiscPS99Tab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
        loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();                 
   end,
})    

local Button = MiscPS99Tab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
        Rayfield:Destroy()                        
   end,
})

local Paragraph = MiscPS99Tab:CreateParagraph({Title = "Last Updated 05/05/24", Content = ""})
            
   end,  
})

local Button = UniversalTab:CreateButton({
   Name = "My Restaurant ScriptHub👨‍🍳",
   Callback = function()
           local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
            
   local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - My Restaurant ScriptHub👨‍🍳",
   LoadingTitle = "LittHub🔥 - My Restaurant ScriptHub👨‍🍳",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "MyRestaurantTab"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

Rayfield:Notify({
   Title = "Follow Littmsn on Roblox",
   Content = "Loaded Successfully!",
   Duration = 5,
   Image = nil,
   Actions = { 
      Ignore = {
         Name = "Okay!",
         Callback = function()
         print("")
      end
   },
},
})
            
local MyRestaurantTab = Window:CreateTab("My Restaurant Scripts👨‍🍳", nil) -- Title, Image
local Section = MyRestaurantTab:CreateSection("My Restaurant Scripts👨‍🍳")         

local Button = MyRestaurantTab:CreateButton({
   Name = "My Restaurant Cheater.fun",
   Callback = function()
   loadstring(game:HttpGet('https://pastebin.com/raw/z7TFbGEL'))()
   end,
})

local Button = MyRestaurantTab:CreateButton({
   Name = "My Restaurant (Milk)👽",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/scriptpastebin/raw/main/MyRestaurant"))()
   end,
})

local Button = MyRestaurantTab:CreateButton({
   Name = "MY RESTAURANT (WD)👽",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/Muhammad6196/Project-WD/main/Mainstring.lua"))()
   end,
})            

local Button = MyRestaurantTab:CreateButton({
   Name = "MY RESTAURANT (FAST NPC)👽",
   Callback = function()
   loadstring(game:HttpGet("https://rawscripts.net/raw/My-Restaurant!-Fast-Autofarm-4610"))()
   end,
})             

local Button = MyRestaurantTab:CreateButton({
   Name = "MY RESTAURANT (LIGHTNING)👽",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/ProjectLightningDev/Project-Lightning-Loader/main/Loader.Lua"))()
   end,
}) 
            
local Button = MyRestaurantTab:CreateButton({
   Name = "MY RESTAURANT (BEST)👽",
   Callback = function()
   loadstring(game:HttpGet("https://system-exodus.com/scripts/MyRestaurant/MyRestaurant.lua", true))()
   end,
}) 

local Button = MyRestaurantTab:CreateButton({
   Name = "CLICKER SIMULATOR (For Mobile📱)",
   Callback = function()
   loadstring(game:HttpGet("https://rawscripts.net/raw/My-Restaurant!-Fast-Autofarm-4610"))()
   end,
})
            
local MyRestaurantMiscTab = Window:CreateTab("Misc", nil) -- Title, Image
local Section = MyRestaurantMiscTab:CreateSection("Destroy/Back")

local Button = MyRestaurantMiscTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();
   end,
})          

local Button = MyRestaurantMiscTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
   Rayfield:Destroy()
   end,
})

local Paragraph = MyRestaurantMiscTab:CreateParagraph({Title = "Last Updated 08/05/24", Content = ""})
            
   end,
})

local Button = UniversalTab:CreateButton({
   Name = "Big PaintBall ScriptHub",
   Callback = function()
       local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

            local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - Big PaintBall ScriptHub",
   LoadingTitle = "LittHub🔥 - Big PaintBall ScriptHub",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local BPBScriptTab = Window:CreateTab("Big PaintBall Scripts", nil) -- Title, Image
local Section = BPBScriptTab:CreateSection("Big PaintBall Scripts")   

local Button = BPBScriptTab:CreateButton({
   Name = "BIG Paintball [AIM/ESP/SPEED/OBVIUOSLYKILL]",
   Callback = function()
   loadstring(game:HttpGet("https://www.pastebin.com/raw/PuaaGKsT"))()
   end,
})   

local Button = BPBScriptTab:CreateButton({
   Name = "Big Paintball OP Script",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/LeoKholYt/roblox/main/bigpaintball.lua",true))()
   end,
}) 

local Button = BPBScriptTab:CreateButton({
   Name = "OwlHub (Universal)",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/CriShoux/OwlHub/master/OwlHub.txt"))();
   end,
})             

local Button = BPBScriptTab:CreateButton({
   Name = "Unfair Hub Script",
   Callback = function()
   loadstring(game:HttpGet(('https://raw.githubusercontent.com/rblxscriptsnet/unfair/main/rblxhub.lua'),true))()
   end,
})  

local BPBMiscTab = Window:CreateTab("Misc", nil) -- Title, Image
local Section = BPBMiscTab:CreateSection("Back/Destroy")   

local Button = BPBMiscTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();
   end,
})  

local Button = BPBMiscTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
   Rayfield:Destroy()
   end,
})

local Paragraph = BPBMiscTab:CreateParagraph({Title = "Last Updated 08/05/24", Content = ""})
            
   end,
})

local Button = UniversalTab:CreateButton({
   Name = "Prison Life️ ScriptHub👮",
   Callback = function()
   local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

            local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - Prison Life️ ScriptHub👮",
   LoadingTitle = "LittHub🔥 - Prison Life️ ScriptHub👮",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local PLTab = Window:CreateTab("Prison Life Scripts", nil) -- Title, Image
local Section = PLTab:CreateSection("Prison Life Scripts")

local Button = PLTab:CreateButton({
   Name = "Prison Life [Gud Mod/Kill Aura/Taze all]",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/GwnStefano/NexusHub/main/Main", true))()
   end,
})

local Button = PLTab:CreateButton({
   Name = "Prison Life: Katana, Fly, Tiger Admin",
   Callback = function()
   loadstring("\108\111\97\100\115\116\114\105\110\103\40\103\97\109\101\58\72\116\116\112\71\101\116\40\34\104\116\116\112\115\58\47\47\114\97\119\46\103\105\116\104\117\98\117\115\101\114\99\111\110\116\101\110\116\46\99\111\109\47\103\48\48\108\88\112\108\111\105\116\101\114\47\103\48\48\108\88\112\108\111\105\116\101\114\47\109\97\105\110\47\70\101\37\50\48\98\121\112\97\115\115\34\44\32\116\114\117\101\41\41\40\41\10")() 
   end,
})  

local Button = PLTab:CreateButton({
   Name = "Hawk Hub",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/TheHanki/Hawk/main/Loader", true))() 
   end,
})              

local Button = PLTab:CreateButton({
   Name = "TIGER ADMIN",
   Callback = function()
   loadstring(game:HttpGet('https://raw.githubusercontent.com/H17S32/Tiger_Admin/main/MAIN'))() 
   end,
}) 

local Button = PLTab:CreateButton({
   Name = "Prison Life: Get All Weapons, Click Arrest, Kill All",
   Callback = function()
   loadstring(game:HttpGet(('https://raw.githubusercontent.com/zeuise0002/SSSWWW222/main/README.md'),true))()
   end,
})            

local PLMTab = Window:CreateTab("Misc", nil) -- Title, Image
local Section = PLMTab:CreateSection("Back/Destroy")

local Button = PLMTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();
   end,
})    

local Button = PLMTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
   Rayfield:Destroy()
   end,
})             
            
   end,
})

local Button = UniversalTab:CreateButton({
   Name = "JailBreak️ ScriptHub👮",
   Callback = function()
   local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

            local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - JailBreak ScriptHub👮",
   LoadingTitle = "LittHub🔥 - JailBreak ScriptHub👮",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local JBTab = Window:CreateTab("JailBreak Scripts", nil) -- Title, Image
local Section = JBTab:CreateSection("JailBreak Scripts")

local Button = JBTab:CreateButton({
   Name = "JAILBREAK (VYNIXIUS)",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/RegularVynixu/Vynixius/main/Loader.lua"))()
   end,
})

local Button = JBTab:CreateButton({
   Name = "JAILBREAK (FARM)",
   Callback = function()
   loadstring(game:HttpGet('https://scripts.luawl.com/14245/JailbreakerFree.lua'))()
   end,
})            

local Button = JBTab:CreateButton({
   Name = "JAILBREAK (SUBHUB)",
   Callback = function()
   pcall(function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/Kw6m/Subbers-scripts/main/jailbreak", true))()
end)
   end,
}) 

local Button = JBTab:CreateButton({
   Name = "JAILBREAK (DIAMOND)",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/BloxiYT/Diamond/main/JailBreak"))()
   end,
}) 

local Button = JBTab:CreateButton({
   Name = "JAILBREAK (PINK)",
   Callback = function()
   loadstring(game:HttpGet('https://scripts.luawl.com/14245/JailbreakerFree.lua'))()
   end,
})   

local Button = JBTab:CreateButton({
   Name = "JAILBREAK",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/wawsdasdacx/ohascriptnrrewading/main/jbsaxcriptidk1"))();
   end,
})  

local JBMTab = Window:CreateTab("Misc", nil) -- Title, Image
local Section = JBMTab:CreateSection("Back/Destroy")            

local Button = JBMTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/wawsdasdacx/ohascriptnrrewading/main/jbsaxcriptidk1"))();
   end,
}) 

local Button = JBMTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
  Rayfield:Destroy()
   end,
})             
            
   end,
})

local Button = UniversalTab:CreateButton({
   Name = "BladeBall ScriptHub",
   Callback = function()
       local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

            local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - BladeBall ScriptHub",
   LoadingTitle = "LittHub🔥 - BladeBall ScriptHub",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local BBTab = Window:CreateTab("BladeBall Scripts", nil) -- Title, Image
local Section = BBTab:CreateSection("BladeBall Scripts")

local Button = BBTab:CreateButton({
   Name = "HYPERHUB",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/imaaan00bb/PublicHyperHubTest/main/jkhsdfhjfdsjksjhks"))()
   end,
})

local Button = BBTab:CreateButton({
   Name = "BLADE BALL SCRIPT OP",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/7Fa0T52n",true))()
   end,
})

local Button = BBTab:CreateButton({
   Name = "BLADE BALL (XNOX)",
   Callback = function()
   loadstring(game:HttpGet("https://paste.gg/p/anonymous/42c468c6f0d94d6a86fc90caf7f0e897/files/9d3a059ff4064dc0b9efe621c774d175/raw"))()
   end,
})  

local Button = BBTab:CreateButton({
   Name = "BLADE BALL (BLUE)⚡",
   Callback = function()
  loadstring(game:HttpGet("https://raw.githubusercontent.com/kmmwhocare/Crazzy-Hub/main/Blade%20Ball"))()
   end,
}) 

local Button = BBTab:CreateButton({
   Name = "Script Close Combat",
   Callback = function()
  loadstring(game:HttpGet("https://raw.githubusercontent.com/kidshop4/scriptbladeballk/main/bladeball.lua"))()
   end,
}) 

local Button = BBTab:CreateButton({
   Name = "ZapHub",
   Callback = function()
  loadstring(game:HttpGet('https://zaphub.xyz/Exec'))()
   end,
})            

local Button = BBTab:CreateButton({
   Name = "BLADE BALL (REDZ)",
   Callback = function()
  loadstring(game:HttpGet("https://raw.githubusercontent.com/REDzHUB/BladeBall/main/redz9999"))()
   end,
}) 

local BBMTab = Window:CreateTab("Misc", nil) -- Title, Image            
local Section = BBMTab:CreateSection("Back/Destroy")

local Button = BBMTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();
   end,
})            

local Button = BBMTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
   Rayfield:Destroy()
   end,
})  
            
   end,
})

local Button = UniversalTab:CreateButton({
   Name = "Strongest BattleGrounds⚡",
   Callback = function()
       local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

            local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - Strongest BattleGrounds⚡",
   LoadingTitle = "LittHub🔥 - Strongest BattleGrounds⚡",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local SBTab = Window:CreateTab("Strongest BattleGrounds ScriptHub", nil) -- Title, Image
local Section = SBTab:CreateSection("Strongest BattleGrounds ScriptHub")            

local Button = SBTab:CreateButton({
   Name = "The Strongest Battlegrounds: Auto Farm, Anti Stun, Extra Range",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/TheHanki/Hawk/main/Loader", true))()
   end,
})

local Button = SBTab:CreateButton({
   Name = "The Strongest Battlegrounds BEST GUI (MANY FEATURES!)",
   Callback = function()
   loadstring(game:HttpGet(('https://raw.githubusercontent.com/zeuise0002/SSSWWW222/main/README.md'),true))()
   end,
})            

local Button = SBTab:CreateButton({
   Name = "The Strongest Battlegrounds: Invisible, Auto Farm Player, Fling",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/LOLking123456/Saitama111/main/battle121"))()
   end,
})

local Button = SBTab:CreateButton({
   Name = "The Strongest Battlegrounds: AutoFarm, Hit Aura, Auto Safe & More",
   Callback = function()
   loadstring(game:HttpGet('https://raw.githubusercontent.com/gitroblox2023/chillscriptX/main/77_9HO6H2PR80MG.lua'))()
   end,
})

local Button = SBTab:CreateButton({
   Name = "Collorem The Strongest Battlegrounds Script",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/sandwichk/RobloxScripts/main/Scripts/BadWare/Hub/Load.lua", true))()
   end,
})   

 local SBMTab = Window:CreateTab("Misc", nil) -- Title, Image
 local Section = SBMTab:CreateSection("Back/Destroy")           

local Button = SBMTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();
   end,
})

local Button = SBMTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
   Rayfield:Destroy()
   end,
})
            
   end,
})

local Button = UniversalTab:CreateButton({
   Name = "BloxFruits⚡",
   Callback = function()
   local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

            local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - BloxFruits ScriptHub",
   LoadingTitle = "LittHub🔥 - BloxFruits ScriptHub",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local BFTab = Window:CreateTab("BloxFruits Scripts", nil) -- Title, Image
local Section = BFTab:CreateSection("BloxFruits Scripts")

local Button = BFTab:CreateButton({
   Name = "BLOX FRUITS (MATSUNE NEW)",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/Yatsuraa/Matsune/main/Matsunebeta.lua"))()
   end,
}) 

local Button = BFTab:CreateButton({
   Name = "BLOX FRUITS (SEAGATE BLUE)",
   Callback = function()
   _G.Loader = true
loadstring(game:HttpGet("https://raw.githubusercontent.com/SeaBabyBF/seamain/main/SeaGateNextGenz"))()
   end,
})         

local Button = BFTab:CreateButton({
   Name = "BLOX FRUITS (AUTO BOUNTY)",
   Callback = function()
   getgenv().config = {
    ["Team"] = "Pirates",
    ["Use Race"] = {
        ["V3"] = true,
        ["V4"] = true
    },
    ["Info Screen"] = true,
    ["White Screen"] = false,
    ["BypassTp"] = true,
    ["SkipFruit"] = {
        "Portal-Portal"
    },
    ["Skip Race V4 User"] = true,
    ["MainSkillToggle"] = {
        ["Melee"] = {
            ["Enable"] = true,
            ["Delay"] = 1,
            ["Skills"] = {
                ["Z"] = {
                    ["Enable"] = true,
                    ["HoldTime"] = 0,
                },
                [ "X"] = {
                    ["Enable"] = true,
                    ["HoldTime"] = 0,
                },
                ["C"] = {
                    ["Enable"] = true,
                    ["HoldTime"] = 0,
                },
            },
        },
        ["Blox Fruit"] = {
            ["Enable"] = false,
            ["Delay"] = 2,
            ["Skills"] = {
                ["Z"] = {
                    ["Enable"] = true,
                    ["HoldTime"] = 0,
                },
                ["X"] = {
                    ["Enable"] = true,
                    ["HoldTime"] = 2,
                },
                ["C"] = {
                    ["Enable"] = false,
                    ["HoldTime"] = 0,
                },
                ["V"] = {
                    ["Enable"] = false,
                    ["HoldTime"] = 0,
                },
                ["F"] = {
                    ["Enable"] = false,
                    ["HoldTime"] = 0,
                },
            },
        },
        ["Gun"] = {
            ["Enable"] = false,
            ["Delay"] = 1,
            ["Skills"] = {
                ["Z"] = {
                    ["Enable"] = false,
                    ["HoldTime"] = 0,
                },
                ["X"] = {
                    ["Enable"] = false,
                    ["HoldTime"] = 0,
                },
            },
        },
        ["Sword"] = {
            ["Enable"] = true,
            ["Delay"] = 1,
            ["Skills"] = {
                ["Z"] = {
                    ["Enable"] = true,
                    ["HoldTime"] = 0,
                },
                ["X"] = {
                    ["Enable"] = true,
                    ["HoldTime"] = 0,
                },
            },
        }
    },
    ["Webhooks"] = {
        ["Link Webhook"] = "",
        ["Toggle Webhook"] = true
    },
    ["ChatSpam"] = {"Hallo"},
    ["MinBountyHunt"] = 0,
    ["MaxBountyHunt"] = 30000000,
    ["SafeHealth"] = 4000
}
loadstring(game:HttpGet("https://raw.githubusercontent.com/LumosSera/SeraHub/main/AutoBounty.lua"))()
   end,
})

local Button = BFTab:CreateButton({
   Name = "BLOX FRUITS (MIN SEAGATE)",
   Callback = function()
   _G.LoadUiFast = false
loadstring(game:HttpGet("https://raw.githubusercontent.com/CheemsNhuChiAl/MinGamingHub/main/mingamingupdatenew"))()
   end,
}) 

local Button = BFTab:CreateButton({
   Name = "Mango Hub Blox Fruits",
   Callback = function()
   getgenv().WaterMark = true
loadstring(game:HttpGet("https://gitlab.com/L1ZOT/mango-hub/-/raw/main/Mango-Bloxf-Fruits-Beta"))()
   end,
}) 

local BFMTab = Window:CreateTab("Misc", nil) -- Title, Image
local Section = BFMTab:CreateSection("Back/Destroy")     

local Button = BFMTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();
   end,
})    

local Button = BFMTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
   Rayfield:Destroy()
   end,
})             
            
   end,
})

local Button = UniversalTab:CreateButton({
   Name = "Sonic.EXE: The disaster",
   Callback = function()
        local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

            local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - Sonic.EXE: The disaster ScriptHub",
   LoadingTitle = "LittHub🔥 - Sonic.EXE: The disaster ScriptHub",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local SDTab = Window:CreateTab("Sonic.EXE: The disaster Scripts", nil) -- Title, Image
local Section = SDTab:CreateSection("Sonic.EXE: The disaster Scripts")

 local Button = SDTab:CreateButton({
   Name = "Immortal Mod",
   Callback = function()
   while true do
wait(0.6)

local name = game.Players.LocalPlayer.Name
local A_1 = "revive"
local A_2 = game.Workspace[name]
local Event = game:GetService("ReplicatedStorage").events.action
Event:FireServer(A_1, A_2)

end
   end,
}) 

local Button = SDTab:CreateButton({
   Name = "Press E to Fly",
   Callback = function()
   local uis = game:GetService("UserInputService")
uis.InputBegan:Connect(function(input, e)
  if e then return end
  if input.KeyCode == Enum.KeyCode.E then
game.ReplicatedStorage.events.action:FireServer("glide")
  end
end)



   end,
})            

local SDTab = Window:CreateTab("Misc", nil) -- Title, Image
local Section = SDTab:CreateSection("Back/Destroy") 

local Button = SDTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();
   end,
})            

local Button = SDTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
   Rayfield:Destroy()
   end,
})  
            
   end,
})

local Button = UniversalTab:CreateButton({
   Name = "Murder Mystery 2",
   Callback = function()
   local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

            local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - Murder Mystery 2 ScriptHub",
   LoadingTitle = "LittHub🔥 - Murder Mystery 2 ScriptHub",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local MMTab = Window:CreateTab("MM2 Scripts", nil) -- Title, Image
local Section = MMTab:CreateSection("MM2 Scripts")

local Button = MMTab:CreateButton({
   Name = "Murder Mystery 2: ESP MORE",
   Callback = function()
   loadstring(game:GetObjects("rbxassetid://4001118261")[1].Source)()
   end,
})

local Button = MMTab:CreateButton({
   Name = "Murder Mystery 2 Hack - MM2 Admin Panel Pastebin:",
   Callback = function()
   loadstring(game:HttpGet('https://pastebin.com/raw/e89Mn4Ec'))()
   end,
}) 

local Button = MMTab:CreateButton({
   Name = "MURDER MYSTERY 2 (KIDACHI)",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/KidichiHB/Kidachi/main/Scripts/MM2_V2"))()
   end,
}) 

local MMMTab = Window:CreateTab("Misc", nil) -- Title, Image
local Section = MMMTab:CreateSection("Back/Destroy")            

local Button = MMMTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();
   end,
})

local Button = MMMTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
   Rayfield:Destroy()
   end,
})            
            
   end,
})

local Button = UniversalTab:CreateButton({
   Name = "Arsenal",
   Callback = function()
      local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
      
      local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - Arsenal ScriptHub",
   LoadingTitle = "LittHub🔥 - Arsenal ScriptHub",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local ATab = Window:CreateTab("Arsenal Scripts", nil) -- Title, Image
local Section = ATab:CreateSection("Arsenal Scripts")

local Button = ATab:CreateButton({
   Name = "Thunder Client V2",
   Callback = function()
   if getgenv().thunderclient then return end
getgenv().thunderclient = true
loadstring(game:HttpGet("https://api.luarmor.net/files/v3/verified/dca3e69649ed196af0ac6577f743a0ae.lua"))()
   end,
})

local Button = ATab:CreateButton({
   Name = "Arsenal OP SCRIPT GUI",
   Callback = function()
    loadstring(game:HttpGet("https://pastebin.com/raw/W0HC8XvW"))()
   end,
})

local AMTab = Window:CreateTab("Misc", nil) -- Title, Image
local Section = AMTab:CreateSection("Back/Destroy")

local Button = AMTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();
   end,
})

local Button = AMTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
   Rayfield:Destroy()
   end,
})


   end,
})

local Button = UniversalTab:CreateButton({
   Name = "Brookhaven 🏡RP",
   Callback = function()
   local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
   
   local Window = Rayfield:CreateWindow({
   Name = "LittHub🔥 - Brookhaven 🏡RP ScriptHub",
   LoadingTitle = "LittHub🔥 - Brookhaven 🏡RP ScriptHub",
   LoadingSubtitle = "by Littmsn",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local BRTab = Window:CreateTab("Brookhaven 🏡RP ScriptHub", nil) -- Title, Image
local Section = BRTab:CreateSection("Brookhaven 🏡RP ScriptHub")

local Button = BRTab:CreateButton({
   Name = "Rochips haven",
   Callback = function()
   --//rochips haven//--
g,ld,gl,Panel,Rochips_ = game,loadstring,"https://glot.io/snippets","a6c7y0","gvjv"
ld(g:HttpGet((''..gl..'/'..Rochips_..''..Panel.. '/raw/main.lua'),true))()
   end,
})

local Button = BRTab:CreateButton({
   Name = "IceHub - Brookhaven RP",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/IceMael7/NewIceHub/main/Brookhaven"))()
   end,
})

local Button = BRTab:CreateButton({
   Name = "Melystial Brookhaven script",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/Melystial/Brookhaven-script/main/brookhaven"))()
   end,
})

local Button = BRTab:CreateButton({
   Name = "Brookhaven RP [All Pases, Fe Headless, Garage]",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/ChillSoftworks/Houseg/main/Housegui"))()
   end,
})

local Button = BRTab:CreateButton({
   Name = "brookhaven script!(metahub)",
   Callback = function()
   loadstring(game:HttpGet("https://raw.githubusercontent.com/NocturneMoDz/BROOKHAVEN-GUI-/main/METAB", true))()
   end,
})

local BRMTab = Window:CreateTab("Misc", nil) -- Title, Image
local Section = BRMTab:CreateSection("Back/Destroy")

local Button = BRMTab:CreateButton({
   Name = "Back To Hub",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/v4nf9WVz"))();
   end,
})

local Button = BRMTab:CreateButton({
   Name = "Destroy UI",
   Callback = function()
   Rayfield:Destroy()
   end,
})

   end,
})

local Section = UniversalTab:CreateSection("More Soon!")

local AdminTab = Window:CreateTab("Admin Scripts", nil)
local Section = AdminTab:CreateSection("Admin Scripts")

local Button = AdminTab:CreateButton({
   Name = "Infinte Yield",
   Callback = function()
            loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
   end,
})

local Button = AdminTab:CreateButton({
   Name = "CMD-X",
   Callback = function()
            loadstring(game:HttpGet("https://raw.githubusercontent.com/CMD-X/CMD-X/master/Source", true))()
   end,
})

local Button = AdminTab:CreateButton({
   Name = "Nameless Admin FE",
   Callback = function()
            --[[
	WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
]]
loadstring(game:HttpGet('https://raw.githubusercontent.com/FilteringEnabled/NamelessAdmin/main/Source'))()
   end,
})

local Button = AdminTab:CreateButton({
   Name = "fates Admin",
   Callback = function()
            loadstring(game:HttpGet("https://raw.githubusercontent.com/fatesc/fates-admin/main/main.lua"))();
   end,
})

local OtherScriptHubsTab = Window:CreateTab("Other ScriptHubs")
local Section = OtherScriptHubsTab:CreateSection("ScriptHubs (🔑Keyless)")

local Button = OtherScriptHubsTab:CreateButton({
   Name = "ScriptHub V3 BETA",
   Callback = function()
          loadstring(game:HttpGet("https://raw.githubusercontent.com/scripthubekitten/scripthubv3beta/main/scripthubv3beta1", true))()
   end,
})

local Button = OtherScriptHubsTab:CreateButton({
   Name = "ScriptHub V2",
   Callback = function()
          loadstring(game:HttpGet("https://raw.githubusercontent.com/scripthubekitten/SCRIPTHUBV2/main/SCRIPTHUBV2", true))()
   end,
})

local Button = OtherScriptHubsTab:CreateButton({
   Name = "Domain X",
   Callback = function()
          loadstring(game:HttpGet(("https://raw.githubusercontent.com/drakker33/rblx-decaying-winter/main/DecayingWinter.lua"), true))()
   end,
})

local Button = OtherScriptHubsTab:CreateButton({
   Name = "EZ HUB",
   Callback = function()
          loadstring(game:HttpGet(('https://raw.githubusercontent.com/debug420/Ez-Industries-Launcher-Data/master/Launcher.lua'),true))()
   end,
})

local Button = OtherScriptHubsTab:CreateButton({
   Name = "Pedulum Hub",
   Callback = function()
        --[[
	WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
]]
loadstring(game:HttpGet("https://raw.githubusercontent.com/Tescalus/Pendulum-Hubs-Source/main/Pendulum%20Hub%20V5.lua"))()
   end,
})

local Button = OtherScriptHubsTab:CreateButton({
   Name = "Spanish Hub V3",
   Callback = function()
          local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("🟦⬜⭐⬜🟦🟦⬜⬜⭐SPANISH HUB - nescoroco⭐⬜⬜🟦🟦⬜⭐⬜🟦", "Midnight")
   end,
})

local Button = OtherScriptHubsTab:CreateButton({
   Name = "OwlHub",
   Callback = function()
          loadstring(game:HttpGet("https://raw.githubusercontent.com/CriShoux/OwlHub/master/OwlHub.txt"))();
   end,
})

local Button = OtherScriptHubsTab:CreateButton({
   Name = "ZEPHYR X",
   Callback = function()
          pcall(function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/ECLIPSEXHUB/ECLIPSE-X/main/ECLIPSE%20X.txt", true))()
end)
   end,
})

local Button = OtherScriptHubsTab:CreateButton({
   Name = "Parvus Hub",
   Callback = function()
          loadstring(game:HttpGetAsync("https://raw.githubusercontent.com/AlexR32/Parvus/main/Loader.lua"))("Parvus hitting p!")
   end,
})

local UpdatesTab = Window:CreateTab("Updates", nil)
local Section = UpdatesTab:CreateSection("Most Recent")

local Paragraph = UpdatesTab:CreateParagraph({Title = "Update 20/05/24", Content = "Added 4 New ScriptHubs, UNC TEST/BOOSTER "})

local Section = UpdatesTab:CreateSection("Update History")

local Paragraph = UpdatesTab:CreateParagraph({Title = "Update 13/05/24", Content = "Added BladeBall ScriptHub, JailBreak ScriptHub, Prison Life ScriptHub"})    
local Paragraph = UpdatesTab:CreateParagraph({Title = "Update 08/05/24", Content = "Added MyRestaurant ScriptHub, BPB ScriptHub, Update History"})
local Paragraph = UpdatesTab:CreateParagraph({Title = "Update 06/05/24", Content = "Added PS99 ScriptHub, Other ScriptHubs Tab"})
local Paragraph = UpdatesTab:CreateParagraph({Title = "Update 05/05/24", Content = "Added Universal Tab, Admin Scripts"})
local Paragraph = UpdatesTab:CreateParagraph({Title = "Update 03/05/24", Content = "Made Home Page, Misc About"})


local AboutTab = Window:CreateTab("About", nil)
local Section = AboutTab:CreateSection("About")

local Button = AboutTab:CreateButton({
   Name = "Discord Server",
   Callback = function()
           setclipboard("test")
            wait(1)
            Rayfield:Notify({
   Title = "Discord Invite",
   Content = "Copied!",
   Duration = 6.5,
   Image = 4483362458,
   Actions = { -- Notification Buttons
      Ignore = {
         Name = "Okay!",
         Callback = function()
         print("")
      end
   },
},
})
   end,
})

local Paragraph = AboutTab:CreateParagraph({Title = "Supported Executors", Content = "Hydrogen, Wave, Solara, Ro-Executor, Delta, Script-Ware, Any PC Really "})
local Paragraph = AboutTab:CreateParagraph({Title = "Follow @Littmsn On Roblox", Content = ""})
