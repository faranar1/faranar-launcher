# Faranar Launcher

A personal Minecraft: Java Edition launcher that I'm building for my own use.

> NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.

## Why it exists

Convenience. It keeps my game setups organized and gets me into the game faster:

- one setup per "world box": a Minecraft version, a mod loader (Fabric, Quilt, NeoForge or Forge) and its own mods
- launches straight into a singleplayer world or a server (Quick Play)
- installs mods from Modrinth for the right version and loader
- a "base" setup per version with my performance mods

## Who uses it

Only me, on my own PC, with my own Microsoft accounts.

- Not distributed: no releases, no downloads, no other users
- Free and not commercial: no ads, no telemetry, no paid features
- The code isn't public yet while it's in early development; happy to share it with the review team

## How Microsoft login works

- Official Microsoft identity platform: OAuth 2.0 authorization code flow with PKCE, through the open-source library minecraft-launcher-lib
- The password is only typed on Microsoft's sign-in page; the launcher never sees it
- Scopes: XboxLive.signin, offline_access
- Microsoft -> Xbox Live -> XSTS -> Minecraft services, only to get my profile, launch the game and change my own skin with the official skin API
- Tokens stay on my PC, encrypted with Windows DPAPI, and are only sent to Microsoft/Xbox/Minecraft services and the game
- Playing requires an account that owns Minecraft: Java Edition

## What it does not do

- No offline/cracked accounts or account sharing
- No game modifications to bypass anti-cheat, no server exploits
- Game files come only from Mojang's official servers

Before this app is approved, a development test mode can start singleplayer with the Java profile already signed in on my official Minecraft Launcher. Multiplayer and chat are disabled in that mode.

## Details

- Azure application (client) ID: 1297dfe9-be08-485e-b63b-6d416e2ab439 (personal Microsoft accounts only)
- Built with Python, CustomTkinter, minecraft-launcher-lib and the Modrinth API
- Contact: open an issue on this repository
