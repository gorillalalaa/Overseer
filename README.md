# 🛠️ Modular Admin Command Panel Framework

A modular admin command framework built for scalability, performance, and ease of use in Roblox projects. This system is designed to keep your codebase clean while allowing you to expand functionality effortlessly.

---

## ✨ Features

* **Modular Command System**
  Each command is its own module, making it easy to add, remove, or update without touching the core.

* **Rank-Based Permissions**
  Flexible permission system with customizable ranks and user assignments.

* **Dynamic Command Handling**
  Commands are automatically detected and executed through a centralized handler.

* **Lightweight & Optimized**
  Designed with performance in mind — minimal overhead and fast execution.

* **Clean Architecture**
  Separation of concerns between core systems, commands, and utilities.

---

## 🚀 Getting Started

1. Place the framework into your project.
2. Require the main module with
```lua
local Overseer = require(path.to.overseer)
-- other code...
```
3. Configure your ranks in Overseer.OvShared.Config.Ranks
4. Start adding commands!

---

## 🧩 Creating a Command

Each command should be its own module. Example:

```lua
return {
    Name = "kick",
    Description = "Kicks a player",
    RankRequired = 1,

    Execute = function(player, args)
        local target = args[1]
        if target then
            target:Kick("You have been kicked.")
        end
    end
}
```

### Each module should be put in a folder and then to register them you should run

```lua
local Overseer = require(path.to.overseer)
Overseer:RegisterCommandsIn(path.to.commandfolder)
```

### To register default commands you should do

```lua
local Overseer = require(path.to.overseer)
Overseer:RegisterDefaultCommands()
```

---

## 🔐 Rank System

The framework uses a numeric rank system:

* Lower value = higher permission (e.g. Owner = 0)
* Higher value = lower permission (e.g. Utilities = 5)

You can:

* Assign users to ranks
* Retrieve ranks dynamically
* Get labels for display

---

## ⚡ Performance

Built with efficiency in mind:

* Fast command lookup
* Minimal runtime overhead
* Optimized loops and execution paths

---

## 📌 Goals

* Keep admin systems **clean and maintainable**
* Allow **easy expansion** without rewriting code
* Provide a **solid foundation** for any Roblox project

---

## 📄 License

Free to use and modify for your own projects.

---

## 🙌 Contributing

Feel free to fork, improve, and expand the framework!
