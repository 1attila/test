<div align="center">
  <!-- REPLACE THE SRC BELOW WITH THE LINK TO YOUR NEW LOGO -->
  <img src="https://github.com/1attila/test/blob/main/cube.svg?raw=true" alt="Conduit Logo" width="600" />

  <br/><br/>

  [![Python Versions](https://img.shields.io/pypi/pyversions/mconduit.svg)](https://pypi.org/project/mconduit)
  [![PyPI Version](https://img.shields.io/pypi/v/mconduit.svg)](https://pypi.org/project/mconduit)
  [![License](https://img.shields.io/github/license/1attila/Conduit.svg)](https://github.com/1attila/Conduit/blob/main/LICENSE)

  <p><b>A powerful, lightweight, and independent Python framework for building Minecraft server plugins.</b></p>
</div>

---

## ✨ See it in action!
Conduit unlocks completely new possibilities for Vanilla Minecraft servers using the power of Python. Here are just a few examples of what you can build:

<table align="center">
  <tr>
    <td align="center" width="50%">
      <!-- REPLACE THE SRC WITH YOUR ACTUAL IMAGE LINK -->
      <img src="https://via.placeholder.com/400x225.png?text=Renderer+Plugin" alt="Renderer Plugin" width="100%"><br>
      <b>📸 Renderer</b><br>
      Render in-game screenshots and automatically send them via a Discord bot!
    </td>
    <td align="center" width="50%">
      <!-- REPLACE THE SRC WITH YOUR ACTUAL IMAGE LINK -->
      <img src="https://github.com/1attila/test/blob/main/LitematicPlugin.png?raw=true" alt="Litematic Plugin" width="100%"><br>
      <b>🏗️ Litematic</b><br>
      A pure, mod-less Python implementation for loading Litematica schematics directly into your world.
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <!-- REPLACE THE SRC WITH YOUR ACTUAL IMAGE LINK -->
      <img src="https://via.placeholder.com/400x225.png?text=PictureLoader+Plugin" alt="PictureLoader Plugin" width="100%"><br>
      <b>🖼️ PictureLoader</b><br>
      Load high-quality, realistic images directly in-game utilizing `text_displays`.
    </td>
    <td align="center" width="50%">
      <!-- REPLACE THE SRC WITH YOUR ACTUAL IMAGE LINK -->
      <img src="https://via.placeholder.com/400x225.png?text=Status+Plugin" alt="Status Plugin" width="100%"><br>
      <b>🖥️ Status</b><br>
      Fetch and monitor the real-time status of any machine running on the server.
    </td>
  </tr>
</table>

## 📖 What is Conduit?

Conduit is an easy-to-use tool that allows you to control one or multiple Minecraft servers using Python. 

It is designed with flexibility in mind and can be used in two ways:
1. **As a Standalone Server:** Run `python -m mconduit` from your console, and it will automatically load all your plugins, connect to your servers, and start listening to events.
2. **As an API Framework:** Import `mconduit` directly into your own Python applications to harness its powerful features—like Rcon dispatching, log-tailing, and data fetching—on your own terms.

## 🚀 Key Features

- **Completely Independent:** Runs in a parallel process. Update or restart Conduit without having to restart your Minecraft server!
- **Modern Python API:** Clean, intuitive, and strongly typed APIs for the best Developer Experience (DX).
- **Event-Driven:** Uses Pygtail to actively read server logs, efficiently extracting useful information to trigger your custom events.
- **Rcon Integration:** Execute commands and fetch player information seamlessly via Rcon.
- **Rich Feature Set:** Built-in support for Permissions, Custom Commands, Multilingual translation, JSON Text generation, Data fetching, and a comprehensive CLI.

---

## ⚙️ How it Works (Conduit vs MCDR)

Conduit is highly inspired by [MCDReforged](https://github.com/MCDReforged/MCDReforged), but with a major architectural difference: **Conduit doesn't wrap or run the Minecraft server directly.** It runs in a parallel process, communicating via Pygtail (Logs) and Rcon. 

This makes installation drastically easier, prevents server crashes if a plugin fails, and allows managing multiple servers from a single instance.

### The Conduit Architecture
```mermaid
flowchart LR
    c("Conduit (Single Process)")

    s1("Survival Server")
    s2("Creative Server")
    s3("Mirror Server")

    cli("CLI")

    s1 -->|Logs| Pygtail --> c
    s2 -->|Logs| Pygtail --> c
    s3 -->|Logs| Pygtail --> c

    c <-->|Commands/Data| r1("Rcon") <--> s1
    c <-->|Commands/Data| r2("Rcon") <--> s2
    c <-->|Commands/Data| r3("Rcon") <--> s3

    c <--> cli
    c <--> p("Python Plugins")
    cli <-.-> u[/User/]
```
### Why choose Conduit?

Pros:
Easier and faster setup out of the box.

Completely independent process (safeguards your MC server uptime).

Update and reload plugins without stopping the Minecraft server.

One central CLI to manage handlers/attributes across multiple servers.

Extremely nice and pythonic API.

Current Limitations:

Currently only fully supports Vanilla (Bukkit/Spigot/Paper support coming soon).
