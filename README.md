
Hi there, I wanna share one tip how to make development your roblox exploit scripts quicker.

If you are tired of copying and pasting code into executors where there are no hubs and tabs, as well as executing it every time, this method is for you.

This setup will allow you to run your code only by one hotkey in roblox.

Requirements:
- any static site serve tool


I use the service from npm, but you can use any other equivalent tool of your choice.

# instalation
- Install NodeJS https://nodejs.org/en/download (if not already installed)
- Open your bash terminal and run `npm i --global serve`

# running
- Move to your project directory via terminal `cd project`
- Start server, run command: `serve --p 1337`

<img src="https://github.com/asyv3n/roblox-dev-script-env/assets/153901936/ea872183-cc56-4df0-970b-0ebe89088439" width="350">

Now your folder `project` available by http and https connection.

<img src="https://github.com/asyv3n/roblox-dev-script-env/assets/153901936/9fe647cb-de60-47a2-9d3d-ab2150783044" width="350">

You already can use in your exploit, but wait! We will prevent a lot of injections.
`loadstring(game:HttpGet("http://localhost:1337/main.lua"))()`

# binding hot reload

```lua
local UserInputService = game:GetService("UserInputService")
UserInputService.InputBegan:Connect(function(input)
    if input.KeyCode == Enum.KeyCode.L then
        loadstring(game:HttpGet("http://localhost:1337/main.lua"))()
    end
end)
```

Paste this code in some file like `remote.lua` and transfer to autoexec folder of your exploit and execute.

If u have no auto execute folder just paste it in executor window.


Now every time when you will press `L` button in game your local script will be executed in game. 

!Whithout copy pasting and redundant injects by your exploit.


![](https://github.com/asyv3n/roblox-dev-script-env/assets/153901936/7c2d34ee-82a1-492b-98bc-6075cee1ab26)

https://streamable.com/nzdy0p
