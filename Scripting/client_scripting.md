---
title: Client Side Scripting
description: Client Side Scripting
published: true
date: 2022-12-22T09:22:58.542Z
tags: scripting, client, lua, coding, communication
editor: markdown
dateCreated: 2021-01-12T00:34:24.843Z
---

# Client Side Scripting

BeamMP allows you to create your own client side plugins as well. We have provided a few functions that you can use to communicate with other multiplayer mods, and other players through the server.


# Functions
> List of available events for scripting:
{.is-info}

|Function|Notes|
|---|---|
|`TriggerServerEvent("eventName", "data")`|Triggers an event in the server lua environment, both parameters are strings|
|`TriggerClientEvent("eventName", "data")`|Triggers an event in the local lua environment, both parameters are strings. Good for communication between plugins|
|`AddEventHandler("eventName", Function)`|Adds the 2nd parameter to the table to be called when eventName is received (either locally or from the server), Function will get 1 parameter, a string containing the event data|



> For example to parse the chat use the included `ChatMessageReceived` event as such:
{.is-info}
```lua
local function chatReceived(msg) -- Receive event with parameters
	print("chat received: "..msg)
	local i = string.find(s, ":") -- Find where our first ':' is, used to separate the sender and message 
	if i == nil then
		print("error parsing message: separator could not be found!")
		return -- Could not find separator, cancel function
	end
	print("index of separator: "..tostring(i))
	local sender = string.sub(msg, 1, i-1) -- Substring our input to separate its 2 parts
	local message = string.sub(msg, i+1, -1)  -- Do whatever you want to with the message
	print("sender: " .. sender)
	print("message: ".. message)
end

AddEventHandler("ChatMessageReceived", chatReceived) -- Add our event handler to the list managed by BeamMP
```

