---
title: Error Codes & Meanings
description: This page is for the error codes that exist within our application. We will likely have the meaning and a possible solution to your issue.
published: true
date: 2022-12-22T09:22:42.738Z
tags: error, code
editor: markdown
dateCreated: 2020-07-18T12:17:43.280Z
---

> For any other issues not on this list, you can refer to https://docs.microsoft.com/en-us/windows/win32/winsock/windows-sockets-error-codes-2 if you know a bit about how networks / sockets work.
{.is-warning}

# Launcher Error Codes
Below is a list of all the Launcher Error Codes, what they mean & how to solve them in most cases.
If the launcher starts but encounters random errors they should be reported

> Note: If the launcher closes immediately check the log you will find startup error codes
{.is-info}

> If the launcher gets stuck updating that means it requires administrator privileges or you need to update manually, sometimes the antivirus may block downloads as well
{.is-info}


`Logger file init failed`
- The launcher doesn't have the ability to create files, Launching as admin could fix the issue

`Sorry Backend System Outage! Don't worry it will back on soon!`
- The Backend did not respond could be the firewall or ISP

`Primary Servers Offline! sorry for the inconvenience!`
- The Launcher failed to check for an update firewall or ISP

`Launcher Update failed!`
- The launcher failed to download the new version


`Please close the game and try again`
- This error will happen if the game is already running under the same profile / launcher was unable clear the multiplayer/mods folder

`Please launch the game at least once`
- This will happen when the launcher tries to modify the game's profile directory and fails. Launching the game should fix it

`Failed to Launch the game! launcher closing soon`
- Launcher failed to start the game launching the game once before retrying could fix it

`Game Closed! launcher closing soon`
- This will happen after the launcher was able to start the game and shouldn't happen unless the game failed to start or closed

`Failed to find the game please launch it. Report this if the issue persists`
- Code 3 means that the launcher was unable to find the game's info (game directory, profile directory, version ect...) in the registry entry. Potential fix is to just run the game at least once so the registry values get created
- Code 4 means the same except the launcher was unable to read the registry values



# Other Error Codes (Server and Launcher)
Below is a list of all the Server Error Codes, what they mean & how to solve them in most cases.

> Note: If the server closes immediately check the log you will find startup error codes
{.is-info}

`Code 10060`
- There is an issue with your ports. Please check you have port forwarded and opened it on incoming on your firewall

`Code 10022`
- This is an issue with binding to the port. Check if the port is in use or use a different port

`Code 10048`
- address already in use, another BeamMP server or program is already running on that port

`Code 10051`
- bad port forwarding or other similar "unreachable" issue - verify that its all setup properly

`Code 10052`
- network reset, happens if the network drops connection while a connection is being established. should never happen. just retry

`Code 10053`
- connection aborted, timeout or other network error, just retry

`Code 10054`
- on launcher: server closed
- on server: client disconnected

`Code 10060 / 10061`
- network timed out, on launcher, this usually means that the server wasnt port forwarded properly

`Code 10064`
- unlikely error, but it means that the host died, so server shutdown or ports were closed, connection died some other way

`Code 10065`
- host not reachable: no internet or bad port forwarding, or any other similar issue*