# Survival Game

Welcome! We are glad to have you here :3.

This is the official repository for the game and here we have all the project files.

In this place you will also learn how to work on the project and the needed tools for it!

**Places:**

- [Main Place](https://www.roblox.com/games/118877659209203/Survival-Game)

- [Testing Place](https://www.roblox.com/games/82037517571314/Survival-Game)

- [Map/Assets Place](https://create.roblox.com/dashboard/creations/experiences/9460281250/overview)

**Note: You can only make changes inside the Map/Assets place. Any changes made in the Main place or Testing place will be overwritten.**

# Current Roles:

<details>
<summary><strong> Modellers / Builders / SFX / VFX / ... </strong></summary>

## Setup Guide

As long as you're not a programmer, you **do NOT** need to do the programmer setup. Actuallly you just have to use your preferred tools!

### Understanding the workflow

Until the game’s release _(and even after)_, your workflow will be very simple!

<details>
<summary><strong> Saving changes </strong></summary>

1. **Build or edit the map**
   - Edit the **[map place](https://create.roblox.com/dashboard/creations/experiences/9507794502/overview)**
   - Or create models in Blender (or your preferred software) and upload them there.
   - Always follow programmer guidelines (folder structure, asset placement, feature limits, etc.).

2. **Download the place file**
   - Once finished, download the place as a `.rbxl` file and name it as `Map` --> `Map.rblx`.

3. **Create a new branch**
   - Go [here](https://github.com/lumii-dev/survival-game-dev-repository/branches) and click **“Create new branch”**.
   - Name the branch saying what you changed (leave the source as `main`).

4. **Replace the map file**
   - Open your new branch.
   - Go to the `~/places/` folder.
   - Delete `Map.rbxl` (three dots --> delete --> commit changes).
   - Upload your new `.rbxl` file (commit changes).
   - Make sure the file name is **exactly** `Map.rbxl`.

5. **Create a Pull Request**
   - Go back to the branch root.
   - Click **“Compare & pull request”**.
   - Title: short summary of what you did.
   - Description: add details if needed.
   - Click **“Create pull request”**.

6. **Wait for testing**
   - CI checks will run automatically.
   - Your changes will be merged with the code and uploaded to the  
     **[testing place](https://www.roblox.com/games/82037517571314/Survival-Game)**.
   - Test everything carefully.

7. **If something breaks**
   - If the issue is related to your changes:
     - Click **“Close pull request”**.
     - Fix the issue.
     - Repeat the process.

8. **If everything works**
   - Once all checks pass:
     - Click **“Merge pull request”**.
     - Confirm the merge.
     - Delete the branch.
   - Your work is now live in the main place!

Everything can be reverted if needed, so don’t worry, just follow the steps carefully.

</details>

</details>

<br>

<details>
<summary><strong> Programmers </strong></summary>

## Setup Guide

This guide explains how to set up the development environment for this project.  
Follow the steps **in order** and you’ll be ready to code in a few minutes.

<details>
<summary><strong> Guide </strong></summary>

<br>

<details>
<summary> Requirements </summary>

### Requirements

Make sure you have these installed **before starting**:

- **[VS Code](https://code.visualstudio.com/download)**
- **[Git](https://git-scm.com/)**
- **[Node.js](https://nodejs.org/en/download)**
- **[Rokit](https://github.com/rojo-rbx/rokit)**

**After installing all tools make sure to reboot so next commands work properly.**

</details>

<details>
<summary> Git Setup </summary>

### Git Setup

Open a terminal (Command Prompt, PowerShell, Cmd, or Terminal) and configure your Git:

- `git config --global user.name "github-username"`
  - Sets the name that will appear as the author of your commits.

- `git config --global user.email "emailYouUsedInGithub@gmail.com"`
  - Sets the email used to link your commits to your GitHub account.

This only needs to be done once. (Don't close the terminal)

</details>

<details>
<summary> Clone the repository </summary>

### Clone the repository

In the same terminal type these commands:

- `mkdir Documents/projects`
  - Creates a folder called "projects" inside Documents.

- `cd Documents/projects`
  - This opens the folder we created in the terminal.

Now, clone the repository:

- `git clone https://github.com/lumii-dev/survival-game-dev-repository survival-game`
  - This creates a folder with the name `survival-game` that has all the repo content.
 
(Don't close the terminal yet)

</details>

<details>
<summary> Rokit and Node.js Setup </summary>

### Rokit and Node.js Setup

**Remember! You should have rebooted your pc after installing needed tools!**

In the same terminal, let's go inside the folder that has the repo in it:

- `cd survival-game`
  - Opens the repo folder in the terminal. (If it doesn't work because you closed the terminal / reboot your pc, use this command: `cd Documents/projects/survival-game`)

And run this command:

- `npm run setup`
  - This is a custom script! It will install all Rokit tools referenced inside `./aftman.toml` and install all Node.js dependencies inside `./package.json`
 
(You can now close the terminal if you want)
 
</details>

<details>
<summary> Open the Project in VS Code </summary>

### Open the Project in VS Code

Now, let's open the project inside VS Code!

You can do this manually inside VS Code or by running:

- `code ./`
  - This command opens the repo folder inside VS Code. We use `./` because we are already inside of the repo folder.

</details>

<details>
<summary> VS Code Setup </summary>

### VS Code Setup

#### Extensions

The required extensions are listed in: `./.vscode/extensions.json`

When you open the repo folder in VS Code, it should automatically prompt you to install them.  
You can also install them manually if needed.

#### Configuration

VS Code configuration is already included in: `./.vscode/settings.json`

No manual setup required, it works automatically when you open the repo.

#### Tasks

VS Code tasks are defined in: `./.vscode/tasks.json`

They will be available automatically once the repo is opened in VS Code.

</details>

<details>
<summary> Next Steps! </summary>

### Done!

You’re now fully set up and ready to work on the project as a programmer!

Please look at "Understanding the workflow", it has a lot of needed information to work in the project. Feel free to take your time to understand it!

If something doesn’t work, check the terminal output and ask!

</details>

</details>

## Understanding the workflow

This section covers the project structure, tooling, and best practices for working on this project.
Stay in touch with the team when making features, changes, or fixes.

<details>
<summary><strong> Project Structure </strong></summary>

<br>

> This section focuses **only on project structure**.  
> For code practices and examples, see **Code Practices**.

### Where to work

- Go to `./places/Code.rblxl` and open it with Roblox studio! You should always work inside VS CODE and sync your changes to the roblox file (Check Sync to Roblox Studio section). Also, don't forget to save changes to the file.

### Architecture

The game is divided into **three main layers**:

- **Client** --> `StarterPlayer.StarterPlayerScripts.Client`
- **Server** --> `ServerScriptService.Server`
- **Common** --> `ReplicatedStorage.Common`

So keep in mind we are referring to this locations when we mention them.

What we do is a feature-based (or service-based) architecture, where each game feature is organized as a singleton service with clear client, server, and common (shared) code.

> **Singleton:** A singleton is a design pattern where only one instance of something exists and is shared everywhere in the project.

---

### Working Directory (`./src`)

You should work **almost exclusively** inside the `./src` directory.

> You _can_ edit other files, but **only if you know exactly what you’re doing**.

Inside `./src`, folders are mapped automatically to Roblox Studio.

---

### `./src/classes`

Used to store **classes only**. Usefull if you want to use `OOP`.

> **OOP (Object-Oriented Programming)**: This is a way of writing code where you organize logic around objects that represent real things or concepts, grouping data (state) and functions (behavior) together so code is easier to understand, reuse, and reason about.
> **Classes:** A class is a blueprint for creating objects: it defines what data they have and what functions they can do, but it doesn’t do anything by itself until an object is created from it.

This folder is split by execution context:

- `/classes/Client/Files...` --> `Client.Classes.Files...`
- `/classes/Server/Files...` --> `Server.Classes.Files...`
- `/classes/Common/Files...` --> `Common.Classes.Files...`

---

### `./src/features`

This is where **all game features (services)** live. These will be **ModuleScripts**

Each feature gets its **own folder** (example: `Inventory`).

#### Required ModuleScripts inside a feature:

- `/features/Inventory/InventoryServiceClient.luau` --> `Client.Services.InventoryServiceClient`
- `/features/Inventory/InventoryServiceServer.luau` --> `Server.Services.InventoryServiceServer`
- `/features/Inventory/InventoryServiceUtils.luau` --> `Common.Services.InventoryServiceUtils`

#### Optional Subfolders:

**IMPORTANT:**  Files inside these subfolders are injected **directly into the service scripts**.  If the service script does **not** exist, the files **will not appear in Studio**.

- `/features/Inventory/Client/Files...` --> `Client.Services.InventoryServiceClient.Files...`
- `/features/Inventory/Server/Files...` --> `Server.Services.InventoryServiceServer.Files...`
- `/features/Inventory/Common/Files...` --> `Common.Services.InventoryServiceUtils.Files...`

---

### `./src/common`

Used for content needed by **both client and server**.

- `./src/common/files...` --> `Common.Files...`

---

### `./src/startup`

Startup scripts that initialize the **module loader**.

These scripts must run **only once**:

- `/startup/Client.client.luau` --> `StarterPlayer.StarterPlayerScripts.Client`
- `/startup/Server.server.luau` --> `ServerScriptService.Server`

---

### `./ServerPackages & ./Packages`

These are tools that other people create, so everyone can use them.

- `./ServerPackages` --> `ServerScriptService.ServerPackages`
- `./Packages` --> `ReplicatedStorage.Packages`

> To see what packages we are using check **Documentation** section!

---

### Notes:

- All mappings are handled automatically by the setup.
- Reference files **as if you were working directly in Studio**.
- If you feel lost just ask or see other's code to have a reference!

</details>

<details>
<summary><strong>Code Practices</strong></summary>

<br>

> This section focuses **only on coding practices**.  
> For folder structure and file placement, see **Project Organization**.

### Module Loader

Our goal is to keep the codebase **clean, scalable, and easy to extend**.  
To achieve this, we also use a **modular architecture** based on **ModuleScripts**.

If you already know [how ModuleScripts work](https://create.roblox.com/docs/tutorials/fundamentals/coding-6/intro-to-module-scripts), you know they must be `require`d to run.  
That’s exactly why we use a **module loader**.

#### How the module loader works

- The loader scans the **descendants of given folders**
- Every **ModuleScript** found is: Required and stored internally.
- If a **ModuleScript** has a booleand attribute enabled called **Ignore**, this module won't load.
- After _all_ modules are required, the loader calls: `module:init()`
- The `init()` calls are **not parallel** they run in order!

**IMPORTANT:** Every service must implement `:init()` in order to work properly.

### Why this approach?

- Keeps features **decoupled**.
- Makes systems **easy to extend**.
- Removes the need for **BindableEvents**.
- Modules can interact **directly through code**.
- Allows us to use the service-based architecture.

### Where the loader is used

The module loader is only run **twice** in the entire project:

- Once on the **server**
- Once on the **client**

As you can see inside `./src/startup/`.

Apart from that has other use that we don't cover here! See Code Practices section.

---

### Services

As explained in _Project Organization_, the game is divided into **features**.
Each feature is implemented as a **service**.

> **A service** is a ModuleScript that acts as a **singleton** (a single, persistent instance) providing reusable functionality.

#### Key rules for services

- One service per feature.
- Loaded automatically by the module loader.
- Exists for the entire game lifetime.
- Can depend on other services if needed.

Services can exist in three contexts:

- **Client**
- **Server**
- **Common**

### Examples

<details>
<summary> Server & Client Service </summary>

```
--!strict

local InventoryServiceContext = {}

function InventoryServiceContext.addSomethingToImportantTable(self: InventoryServiceContext, ...: any)
    local expected = {...}

    if #expected == 0 then
        error(`Expected more than one item to add to importan table! Received cero. `)
    end

    local importanTable = self.importantTable

    for _, item in expected do
        table.insert(importanTable, item)
        print(`This {item} was inserted to important table!`)
    end
end

function InventoryServiceContext.init(self: InventoryServiceContext)
    self.importantTable = {}

    self.addSomethingToImportantTable(self, "This", "And also this")
end

type InventoryServiceContext = typeof(InventoryServiceContext) & {
	importantTable: {},
}

return InventoryServiceContext :: InventoryServiceContext
```
Instead of InventoryService**Context** we would want to put InventoryService**Client** or InventoryService**Server** as we stated in Project Structure section.

**Explaining why we do certain things:**
- `--!strict` Error Prevention, enables the strongest level of type-checking. It forces the editor to flag logical inconsistencies and typos immediately, preventing runtime crashes before the code is ever executed.
- `self` Context Reference, represents the specific object or "instance" the function is acting upon. It ensures that the function modifies the correct data set when multiple versions of the same table exist.
- `type` Structural Blueprint, defines a custom "shape" for your data. By declaring a type, you provide the editor with a map of what properties a table should have, enabling smarter autocomplete and clearer documentation.
- `:: (Type Assertion)` Explicit Intent, used to clarify an object's identity to the compiler. It is a manual override that says, "Treat this variable as this specific type".

</details>

<details>
<summary> Utils Service </summary>

```
--!strict
local InventoryServiceUtils = {}

function InventoryServiceUtils.someUtilityThatClientOrServerNeeds(...: any): number
	local things = { ... }

	return #things
end

return InventoryServiceUtils
```

**Explaining why we do certain things:**
- Nothing too interesting tbh.

</details>

Please, check services in the project for real examples and patterns. If you feel lost, please ask!

---

### Code Practices

These are the practices that I personally follow, I'll list them if you need help with that!

As long your code is understandable and you have good practices you should be fine!

1. **Strict typing (--!strict).**
   - Types are enforced to reduce runtime errors and improve clarity. You can remove it after you're done.

2. **Clear Client / Server / Common separation.**
   - Client --> visuals and local state
   - Server --> game logic and authority
   - Common --> shared logic and utilities

3. **State lives on the server.**
   - The server owns and mutates game state; the client only reflects it.

4. **Packet-based communication / Networking.**
   - All client–server communication goes through Packet library.

5. **Send the least possible data over the network.**
   - Only sync what the client actually needs to optimize bandwidth

6. **Pure builder functions.**
   - Data construction is isolated and predictable. This also improves readability.

7. **Avoid deep nesting.**
   - Prefer early returns and continue to keep code flat and readable.

8. **Descriptive conditionals**
   - Try to use clear, meaningful variable names in if statements to explain intent.

9. **Defensive error handling**
   - Use warn for recoverable issues and error for invalid states.

10. **No hidden side effects**
    - Functions do one thing and make changes explicit.

11. **Avoid function argument mess**
    - Prefer passing a single table instead of many arguments so order doesn’t matter and usage is clearer.

12. **Consistent naming & structure**
    - Predictable file names and patterns across the codebase.

You can take inspiration from others code. If you need help or ur still learning like everyone feel free to ask :3.

---

### Notes

- Keep services focused on **one responsibility**
- Communicate changes with the team early

</details>

<details>
<summary><strong> Syncing to Roblox Studio  </strong></summary>

This is a very simple step!

- Open `./places/Code.rbxlx` in Roblox Studio
- Open the terminal inside VS Code and type this command `rojo serve`
- Open Rojo plugin in Roblox Studio and click "Connect"

That's it! Every time you edit/create/delete a file it should change.
Just make sure to be always connected :3.

</details>

<details>
<summary><strong> Understanding Github / Publishing changes </strong></summary>

### Github:

GitHub is very useful when working with a team. It allows everyone to work on different features or fixes without interfering with each other’s code. When someone updates the `main` branch, those changes can be pulled so everyone stays up to date.

> **Branches:** A branch is a safe copy of the project where you can work without breaking anything.
>
> - `main` -> Stable version (latest update)
> - Your branch -> Where you make changes safely
> - You can experiment, break things, and fix them without affecting `main`.

All of this can be done via commands and you can do this in the VS Code terminal! And make sure you **ALWAYS** have latest main branch changes!

**IMPORTANT: Every time you want to make a change, you MUST create a new branch. This keeps `main` stable and becomes even more important after release.**

### Git Commands:

These are some of the commands you will need. If something goes wrong or you need help please ask!

1. `git fetch origin`
   - This checks for updates in the `main` branch.
2. `git status`
   - Then check if `main` is behind, If you see something like: `Your branch is behind 'origin/main' by X commits`, That means `main` changed.
3. `git pull --rebase origin main`
   - This downloads changes from `main` and re-applies your changes on top.
4. `git checkout -b feature-name`
   - Create a brand new branch, make sure to change `feature-name`
5. `git add .`
   - This is staging and tells Git which changes you want to include in the next commit. `.` means that it will add ALL changes you did.
6. `git commit -m "Title" -m "Description if needed"`
   - This is a commint and saves a snapshot of your changes, with a message explaining what you did.
7. `git push -u origin feature-name`
   - This uploads your feature branch to GitHub so others can see it and you can open a pull request.
8. `git checkout branch-name`
   - This switches your working branch to a branch. Ideally `main`.

Sometimes `git pull --rebase origin main` could fail, but why and what you have to do?:

- **Why:** This means that you and main branch tried to change the same lines / files.
- **What to do:** Git will pause and ask you to fix them manually. It should show you what commands you have to put. If you need help please, ask.

### Publishing changes:

> **Pull Request or PR:** A pull request is how you ask to add those changes from your branch into main

> **Github Actions:** GitHub Actions are automated tasks that run when something happens in the repo (like a push or a pull request), to check, build, or test code automatically.

When you open a PR, github runs 2 actions we created! The first action (CI) runs two check one being linting with Selene, the second one styling with Stylua. The second action (RELEASE-TESTING) grabs `./places/Code.rbxl` and `./places/Map.rbxl` and merge some selected locations into a single place called `Output.rbxlx` (located in the same folder), after that it will automatically publish that place to the [testing place](https://www.roblox.com/games/82037517571314/Survival-Game) so tests can be run before implementing a feature into the `main` branch.

After testing, if everything goes fine, click the green merge button, confirm it. If while testing were errors, you will have to close the PR, fix error in your branch and re-open the PR.

After clicking the merge button the repo will do the same two actions but instad it will publish the `Output.rbxlx` file to the [main place](https://www.roblox.com/games/118877659209203/Survival-Game)

</details>

<details>
<summary><strong> Documentation </strong></summary>

Here you can see what packages we are using and direct links to every needed documentation!

- **ServerPackages**:
  - [ProfileStore](https://madstudioroblox.github.io/ProfileStore/)
  - [Cmdr](https://eryn.io/Cmdr/guide/Setup.html)

- **Packages**:
  - [Packet](https://devforum.roblox.com/t/packet-networking-library/3573907?page=3)

- **Other**:
  - [Rojo](https://rojo.space/docs/v7/)
  - [Stylua](https://github.com/JohnnyMorganz/StyLua)
  - [Selente](https://kampfkarren.github.io/selene/)
  - [Rokit](https://github.com/rojo-rbx/rokit)
  - [Lune](https://lune-org.github.io/docs/roblox/1-introduction/)

</details>

</details>
