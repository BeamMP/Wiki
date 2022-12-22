---
title: Mod Documentation
description: This page is for the documentation of the Lua Mod.
published: true
date: 2022-12-22T09:22:51.567Z
tags: 
editor: markdown
dateCreated: 2022-12-21T14:01:49.658Z
---

# Introduction

***

Since the beginning BeamMP has been built on custom messages. This consists of a structure like `<IDENTIFIER>:<SUBIDENTIFIER/PARAMS>:<PARAMS>`

# Data Documentation
## Received Packets

| Example | Protocol | Identifier | Sub Identifier | Data | Comments |
|---------|----------|------------|----------------|------|----------|
|         | `TCP`    | `A`        |                |      | Launcher heartbeat |
|         | `TCP`    | `B`        |                |      | Server List |
|         | `TCP`    | `L`        |                |      | Mods List |
|         | `TCP`    | `M`        |                |      | Map Received, Tell the game to load the map |
|         | `TCP`    | `N`        |                |      | Login Received / Confirmed |
|         | `TCP`    | `U`        | `l` \| `p`               |      | Messages, This U packet is used for all UI related messages |
|         | `TCP`    | `Z`        |                |      | Launcher / Client Version |

## Sent Packets

| Example | Protocol | Identifier | Sub Identifier | Data | Comments |
|---------|----------|------------|----------------|------|----------|
|         | `TCP`    | `C`        |                |      | Launcher heartbeat |
|         | `TCP`    | `B`        |                |      | Server List |
