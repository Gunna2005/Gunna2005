--Library--> --Made by Gunna#8852
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Gunna Studios", "BloodTheme")

--Main-->

local Main = Window:NewTab("Main")
local MainSection = Main:NewSection("Main")

MainSection:NewButton("Silent Aim", "Aimbot But More Controlled", function()
local repo = 'https://raw.githubusercontent.com/wally-rblx/LinoriaLib/main/'
 
local Library = loadstring(game:HttpGet(repo .. 'Library.lua'))()
local ThemeManager = loadstring(game:HttpGet(repo .. 'addons/ThemeManager.lua'))()
local SaveManager = loadstring(game:HttpGet(repo .. 'addons/SaveManager.lua'))()
 
local Window = Library:CreateWindow({

    Title = 'Gunna Studios',
    Center = true, 
    AutoShow = true,
})
 

local Tabs = {
    
    Main = Window:AddTab('Target'), 
    Visual = Window:AddTab('Visual'), 
    ['UI Settings'] = Window:AddTab('UI Settings'),
}
 

local LeftGroupBox = Tabs.Main:AddLeftGroupbox('Target')
local RightGroupBox = Tabs.Main:AddRightGroupbox('Target Settings')
 
LeftGroupBox:AddToggle('Showdot', {
    Text = 'ShowBox',
    Default = true, 
    Tooltip = '', 
});
 
 
LeftGroupBox:AddToggle('Target', {
    Text = 'Target',
    Default = true, 
    Tooltip = '', 
})
Toggles.Target:OnChanged(function()
    
    getgenv().Target = Toggles.Target.Value
end)
 
-- This should print to the console: "My toggle state changed! New value: false"
Toggles.Target:SetValue(false)
 
LeftGroupBox:AddToggle('Airshot', {
    Text = 'Airshot',
    Default = true, -- Default value (true / false)
    Tooltip = '', -- Information shown when you hover over the toggle
})
Toggles.Airshot:OnChanged(function()
    -- here we get our toggle object & then get its value
    getgenv().AirshotFunccc = Toggles.Airshot.Value
end)
 
-- This should print to the console: "My toggle state changed! New value: false"
Toggles.Airshot:SetValue(false)
 
 
LeftGroupBox:AddToggle('NotifMode', {
    Text = 'Notification',
    Default = true, -- Default value (true / false)
})
 
LeftGroupBox:AddToggle('ChatMode', {
    Text = 'Chat Mode',
    Default = true, -- Default value (true / false)
    Tooltip = '', -- Information shown when you hover over the toggle
})
Toggles.ChatMode:OnChanged(function()
    -- here we get our toggle object & then get its value
    getgenv().ChatMode = Toggles.ChatMode.Value
end)
 
-- This should print to the console: "My toggle state changed! New value: false"
Toggles.ChatMode:SetValue(false)
 
 
 
Toggles.NotifMode:OnChanged(function()
    getgenv().NotifMode = Toggles.NotifMode.Value
end)
 
-- This should print to the console: "My toggle state changed! New value: false"
Toggles.NotifMode:SetValue(false)
 
LeftGroupBox:AddToggle('AutoPred', {
    Text = 'Ping Based',
    Default = true, -- Default value (true / false)
    Tooltip = '', -- Information shown when you hover over the toggle
})
Toggles.AutoPred:OnChanged(function()
    -- here we get our toggle object & then get its value
    getgenv().AutoPrediction = Toggles.AutoPred.Value
end)
 
-- This should print to the console: "My toggle state changed! New value: false"
Toggles.AutoPred:SetValue(false)
 
-- Groupbox:AddInput
-- Arguments: Idx, Info
LeftGroupBox:AddInput('Prediction', {
    Default = '0.1229',
    Numeric = false, -- true / false, only allows numbers
    Finished = false, -- true / false, only calls callback when you press enter
 
    Text = 'Prediction',
    Tooltip = '', -- Information shown when you hover over the textbox
 
    Placeholder = 'Enter New Pred Here', -- placeholder text when the box is empty
    -- MaxLength is also an option which is the max length of the text
})
 
Options.Prediction:OnChanged(function()
    getgenv().Prediction = Options.Prediction.Value
end)
 
Options.Prediction:SetValue(0.1229)
 
-- Groupbox:AddDropdown
-- Arguments: Idx, Info
 
LeftGroupBox:AddDropdown('MyDropdown', {
    Values = { 'Head', 'UpperTorso', 'HumanoidRootPart', 'RightFoot' },
    Default = 1, -- number index of the value / string
    Multi = false, -- true / false, allows multiple choices to be selected
 
    Text = 'Hitpart',
    Tooltip = 'This is a tooltip', -- Information shown when you hover over the textbox
})
 
Options.MyDropdown:OnChanged(function()
    getgenv().Partz = Options.MyDropdown.Value
end)
 
Options.MyDropdown:SetValue('UpperTorso')
 
 
RightGroupBox:AddDivider()
 
-- // Target Settings -- //
 
 
RightGroupBox:AddLabel('Hitbox Color'):AddColorPicker('ColorPicker', {
    Default = Color3.new(0, 1, 0), -- Bright green
    Title = 'Hitbox Color', -- Optional. Allows you to have a custom color picker title (when you open it)
});
 
 
RightGroupBox:AddSlider('MySlider', {
    Text = 'Hitbox Transparency',
 
    -- Text, Default, Min, Max, Rounding must be specified.
    -- Rounding is the number of decimal places for precision.
 
    -- Example:
    -- Rounding 0 - 5
    -- Rounding 1 - 5.1
    -- Rounding 2 - 5.15
    -- Rounding 3 - 5.155
 
    Default = 0,
    Min = 0,
    Max = 1,
    Rounding = 1,
 
    Compact = false, -- If set to true, then it will hide the label
});
 
Options.MySlider:SetValue(0.3)
 
RightGroupBox:AddDivider()
 
RightGroupBox:AddToggle('FOVToggle', {
    Text = 'FOV',
    Default = true, -- Default value (true / false)
    Tooltip = '', -- Information shown when you hover over the toggle
});
 
RightGroupBox:AddToggle('FOVFilled', {
    Text = 'FOV Filled',
    Default = false, -- Default value (true / false)
    Tooltip = '', -- Information shown when you hover over the toggle
});
 
RightGroupBox:AddSlider('FOV', {
    Text = 'FOV Radius',
 
    Default = 0,
    Min = 0,
    Max = 750,
    Rounding = 0,
 
    Compact = false, -- If set to true, then it will hide the label
});
 
Options.FOV:SetValue(280)
 
RightGroupBox:AddSlider('Thickness', {
    Text = 'FOV Thickness',
 
    Default = 0,
    Min = 0,
    Max = 10,
    Rounding = 1,
 
    Compact = false, -- If set to true, then it will hide the label
});
 
Options.Thickness:SetValue(0)
 
RightGroupBox:AddSlider('FOVTrans', {
    Text = 'FOV Transparency',
 
    -- Text, Default, Min, Max, Rounding must be specified.
    -- Rounding is the number of decimal places for precision.
 
    -- Example:
    -- Rounding 0 - 5
    -- Rounding 1 - 5.1
    -- Rounding 2 - 5.15
    -- Rounding 3 - 5.155
 
    Default = 0.8,
    Min = 0,
    Max = 1,
    Rounding = 1,
 
    Compact = false, -- If set to true, then it will hide the label
});
 
 
-- Library functions
-- Sets the watermark visibility
Library:SetWatermarkVisibility(true)
 
-- Sets the watermark text
Library:SetWatermark('Gunna Studios')
 
Library.KeybindFrame.Visible = true; -- todo: add a function for this
 
Library:OnUnload(function()
    print('Unloaded!')
    Library.Unloaded = true
end)
 
-- UI Settings
local MenuGroup = Tabs['UI Settings']:AddLeftGroupbox('Menu')
 
-- I set NoUI so it does not show up in the keybinds menu
MenuGroup:AddButton('Unload', function() Library:Unload() end)
MenuGroup:AddLabel('Menu bind'):AddKeyPicker('MenuKeybind', { Default = 'End', NoUI = true, Text = 'Menu keybind' }) 
 
Library.ToggleKeybind = Options.MenuKeybind -- Allows you to have a custom keybind for the menu
 
-- Addons:
-- SaveManager (Allows you to have a configuration system)
-- ThemeManager (Allows you to have a menu theme system)
 
-- Hand the library over to our managers
ThemeManager:SetLibrary(Library)
SaveManager:SetLibrary(Library)
 
-- Ignore keys that are used by ThemeManager. 
-- (we dont want configs to save themes, do we?)
SaveManager:IgnoreThemeSettings() 
 
-- Adds our MenuKeybind to the ignore list 
-- (do you want each config to have a different menu key? probably not.)
SaveManager:SetIgnoreIndexes({ 'MenuKeybind' }) 
 
-- use case for doing it this way: 
-- a script hub could have themes in a global folder
-- and game configs in a separate folder per game
ThemeManager:SetFolder('MyScriptHub')
SaveManager:SetFolder('MyScriptHub/specific-game')
 
-- Builds our config menu on the right side of our tab
SaveManager:BuildConfigSection(Tabs['UI Settings']) 
 
ThemeManager:ApplyToTab(Tabs['UI Settings'])
 
-- Toggle
    getgenv().ChatMode = false
        getgenv().PartMode = true
        getgenv().Key = Enum.KeyCode.Q
    --
 
    --
        _G.Types = {
            Ball = Enum.PartType.Ball,
            Block = Enum.PartType.Block, 
            Cylinder = Enum.PartType.Cylinder
        }
 
        --variables                 
            local Tracer = Instance.new("Part", game.Workspace)
        Tracer.Name = "gay"	
        Tracer.Anchored = true		
        Tracer.CanCollide = false
        Tracer.Parent = game.Workspace	
        Tracer.Shape = _G.Types.Block 
        Tracer.Size = Vector3.new(7,7,7)
        game:GetService("RunService").RenderStepped:Connect(function()
        Tracer.Transparency = Options.MySlider.Value
        Tracer.Color = Options.ColorPicker.Value
        end)
        --
        local plr = game.Players.LocalPlayer
    local mouse = plr:GetMouse()
    local Runserv = game:GetService("RunService")
 
    circle = Drawing.new("Circle")
    circle.Color = Color3.fromRGB(173,216,230)
    circle.Thickness = 5
    circle.NumSides = 732
    circle.Transparency = 0.8
    game:GetService("RunService").RenderStepped:Connect(function()
    circle.Thickness = Options.Thickness.Value
    circle.Radius = Options.FOV.Value
    circle.Visible = Toggles.FOVToggle.Value
    circle.Transparency = Options.FOVTrans.Value
    circle.Filled = Toggles.FOVFilled.Value
    end)
 
    Runserv.RenderStepped:Connect(function()
        circle.Position = Vector2.new(mouse.X,mouse.Y+35)
        if getgenv().AirshotFunccc == true then
                if Plr ~= nil then else return; end
                if Plr.Character.Humanoid.Jump == true and Plr.Character.Humanoid.FloorMaterial == Enum.Material.Air then
                    getgenv().Partz = "RightFoot"
                else
                    Plr.Character:WaitForChild("Humanoid").StateChanged:Connect(function(old,new)
                        if new == Enum.HumanoidStateType.Freefall then
                        getgenv().Partz = "RightFoot"
                        else
                            getgenv().Partz = "HumanoidRootPart"
                        end
                    end)
                end
    end
    end)
 
            local guimain = Instance.new("Folder", game.CoreGui)
            local CC = game:GetService"Workspace".CurrentCamera
        local LocalMouse = game.Players.LocalPlayer:GetMouse()
            local Locking = false
 
 
        --
        if getgenv().valiansh == true then
                            game.StarterGui:SetCore("SendNotification", {
                       Title = "Gunna Studios",
                       Text = "Already Loaded!",
                       Duration = 5
 
                       })
            return
        end
 
        getgenv().valiansh = true
 
            local UserInputService = game:GetService("UserInputService")
 
        UserInputService.InputBegan:Connect(function(keygo,ok)
               if (not ok) then
               if (keygo.KeyCode == getgenv().Key) then
                   if getgenv().Target == true then
                   Locking = not Locking
 
                   if Locking then
                   Plr =  getClosestPlayerToCursor()
                    if getgenv().ChatMode then
            local A_1 = "Target: "..tostring(Plr.Character.Humanoid.DisplayName) local A_2 = "All" local Event = game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest Event:FireServer(A_1, A_2) 
                end	
                   if getgenv().NotifMode then
                    game.StarterGui:SetCore("SendNotification", {
            Title = "Gunna Stuidos";
            Text = "Target: "..tostring(Plr.Character.Humanoid.DisplayName);
 
        })
        end
        elseif not Locking then
             if getgenv().ChatMode then
            local A_1 = "Unlocked!" local A_2 = "All" local Event = game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest Event:FireServer(A_1, A_2) 
                end	
            if getgenv().NotifMode then
                            game.StarterGui:SetCore("SendNotification", {
                       Title = "Gunna Studios",
                       Text = "Unlocked",
                       Duration = 5
                   })
               elseif getgenv().Target == false then
                            game.StarterGui:SetCore("SendNotification", {
                       Title = "Gunna Studios",
                       Text = "Target left or died.",
                       Duration = 5
 
                       })
 
                   end
 
 
     end     end   
    end
    end
    end)
 
        function getClosestPlayerToCursor()
            local closestPlayer
            local shortestDistance = circle.Radius
 
            for i, v in pairs(game.Players:GetPlayers()) do
                if v ~= game.Players.LocalPlayer and v.Character and v.Character:FindFirstChild("Humanoid") and v.Character.Humanoid.Health ~= 0 and v.Character:FindFirstChild("LowerTorso") then
                    local pos = CC:WorldToViewportPoint(v.Character.PrimaryPart.Position)
                    local magnitude = (Vector2.new(pos.X, pos.Y) - Vector2.new(LocalMouse.X, LocalMouse.Y)).magnitude
                    if magnitude < shortestDistance then
                        closestPlayer = v
                        shortestDistance = magnitude
                    end
                end
            end
            return closestPlayer
        end
    --
    if getgenv().PartMode then
        game:GetService"RunService".Stepped:connect(function()
            if Locking and Plr.Character and Plr.Character:FindFirstChild("LowerTorso") then
                Tracer.CFrame = CFrame.new(Plr.Character.LowerTorso.Position+(Plr.Character.LowerTorso.Velocity*Prediction))
            else
                Tracer.CFrame = CFrame.new(0, 9999, 0)
            end
        end)
    end
 
 
 
        --
        local rawmetatable = getrawmetatable(game)
        local old = rawmetatable.__namecall
        setreadonly(rawmetatable, false)
        rawmetatable.__namecall = newcclosure(function(...)
            local args = {...}
            if Locking and getnamecallmethod() == "FireServer" and args[2] == "UpdateMousePos" then
                args[3] = Plr.Character[getgenv().Partz].Position+(Plr.Character[getgenv().Partz].Velocity*Prediction)
                return old(unpack(args))
            end
            return old(...)
        end)
    ---
        while wait() do
        if getgenv().AutoPrediction == true then
            local pingvalue = game:GetService("Stats").Network.ServerStatsItem["Data Ping"]:GetValueString()
            local split = string.split(pingvalue,'(')
            local ping = tonumber(split[1])
            if ping < 130 then
                getgenv().Prediction = 0.151
            elseif ping < 125 then
                getgenv().Prediction = 0.149
            elseif ping < 110 then
                getgenv().Prediction = 0.140
            elseif ping < 105 then
                getgenv().Prediction = 0.133
            elseif ping < 90 then
                getgenv().Prediction = 0.130
            elseif ping < 80 then
                getgenv().Prediction = 0.128
            elseif ping < 70 then
                getgenv().Prediction = 0.1230
            elseif ping < 60 then
                getgenv().Prediction = 0.1229
            elseif ping < 50 then
                getgenv().Prediction = 0.1225
            elseif ping < 40 then
                getgenv().Prediction = 0.1256
            end
        end
        end    
end)
MainSection:NewButton("Esp", "Lets You See AnyOne From AnyWhere", function()
--- Tut
 
local esp_settings = { ---- table for esp settings 
    textsize = 8,
    colour = 255,255,255
}
 
local gui = Instance.new("BillboardGui")
local esp = Instance.new("TextLabel",gui) ---- new instances to make the billboard gui and the textlabel
 
 
 
gui.Name = "Cracked esp"; ---- properties of the esp
gui.ResetOnSpawn = false
gui.AlwaysOnTop = true;
gui.LightInfluence = 0;
gui.Size = UDim2.new(1.75, 0, 1.75, 0);
esp.BackgroundColor3 = Color3.fromRGB(255, 255, 255);
esp.Text = ""
esp.Size = UDim2.new(0.0001, 0.00001, 0.0001, 0.00001);
esp.BorderSizePixel = 4;
esp.BorderColor3 = Color3.new(esp_settings.colour)
esp.BorderSizePixel = 0
esp.Font = "GothamSemibold"
esp.TextSize = esp_settings.textsize
esp.TextColor3 = Color3.fromRGB(esp_settings.colour) -- text colour
 
game:GetService("RunService").RenderStepped:Connect(function() ---- loops faster than a while loop :)
    for i,v in pairs (game:GetService("Players"):GetPlayers()) do
        if v ~= game:GetService("Players").LocalPlayer and v.Character.Head:FindFirstChild("Cracked esp")==nil  then -- craeting checks for team check, local player etc
            esp.Text = "{"..v.Name.."}"
            gui:Clone().Parent = v.Character.Head
    end
end
end)
end)
MainSection:NewButton("ClickTp", "Tp Anywhere (CTRLClick)", function()
    noclip = false
    local UIS = game:GetService("UserInputService")
    local Player = game.Players.LocalPlayer
    local Mouse = Player:GetMouse()
    
    
    function GetCharacter()
        return game.Players.LocalPlayer.Character
    end
    
    function Teleport(pos)
        local Char = GetCharacter()
        if Char then
            Char:MoveTo(pos)
        end
    end
    
    
    UIS.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 and UIS:IsKeyDown(Enum.KeyCode.LeftControl) then
            Teleport(Mouse.Hit.p)
        end
        end)
end)
MainSection:NewButton("CoolShit", "Prank People", function()
loadstring(game:HttpGet('https://raw.githubusercontent.com/ant-7802/--/main/straightmilk.lua'))()
end)

--PLayer-->

local Player = Window:NewTab("Player")
local PlayerSection = Player:NewSection("Player")

PlayerSection:NewSlider("WalkSpeed", "SliderInfo", 500, 16, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)
PlayerSection:NewSlider("JumpHigh", "SliderInfo", 350, 50, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.JumpHigh = s
end)
PlayerSection:NewButton("Fly  (G)", "FlyToTheSky", function()
   repeat wait() 
    until game.Players.LocalPlayer and game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character:findFirstChild("Head") and game.Players.LocalPlayer.Character:findFirstChild("Humanoid") 
local mouse = game.Players.LocalPlayer:GetMouse() 
repeat wait() until mouse
local plr = game.Players.LocalPlayer 
local torso = plr.Character.Head 
local flying = false
local deb = true 
local ctrl = {f = 0, b = 0, l = 0, r = 0} 
local lastctrl = {f = 0, b = 0, l = 0, r = 0} 
local maxspeed = 400 
local speed = 5000 
 
function Fly() 
local bg = Instance.new("BodyGyro", torso) 
bg.P = 9e4 
bg.maxTorque = Vector3.new(9e9, 9e9, 9e9) 
bg.cframe = torso.CFrame 
local bv = Instance.new("BodyVelocity", torso) 
bv.velocity = Vector3.new(0,0.1,0) 
bv.maxForce = Vector3.new(9e9, 9e9, 9e9) 
repeat wait() 
plr.Character.Humanoid.PlatformStand = true 
if ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0 then 
speed = speed+.5+(speed/maxspeed) 
if speed > maxspeed then 
speed = maxspeed 
end 
elseif not (ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0) and speed ~= 0 then 
speed = speed-1 
if speed < 0 then 
speed = 0 
end 
end 
if (ctrl.l + ctrl.r) ~= 0 or (ctrl.f + ctrl.b) ~= 0 then 
bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (ctrl.f+ctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(ctrl.l+ctrl.r,(ctrl.f+ctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed 
lastctrl = {f = ctrl.f, b = ctrl.b, l = ctrl.l, r = ctrl.r} 
elseif (ctrl.l + ctrl.r) == 0 and (ctrl.f + ctrl.b) == 0 and speed ~= 0 then 
bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (lastctrl.f+lastctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(lastctrl.l+lastctrl.r,(lastctrl.f+lastctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed 
else 
bv.velocity = Vector3.new(0,0.1,0) 
end 
bg.cframe = game.Workspace.CurrentCamera.CoordinateFrame * CFrame.Angles(-math.rad((ctrl.f+ctrl.b)*50*speed/maxspeed),0,0) 
until not flying 
ctrl = {f = 0, b = 0, l = 0, r = 0} 
lastctrl = {f = 0, b = 0, l = 0, r = 0} 
speed = 0 
bg:Destroy() 
bv:Destroy() 
plr.Character.Humanoid.PlatformStand = false 
end 
mouse.KeyDown:connect(function(key) 
if key:lower() == "g" then 
if flying then flying = false 
else 
flying = true 
Fly() 
end 
elseif key:lower() == "w" then 
ctrl.f = 1 
elseif key:lower() == "s" then 
ctrl.b = -1 
elseif key:lower() == "a" then 
ctrl.l = -1 
elseif key:lower() == "d" then 
ctrl.r = 1 
end 
end) 
mouse.KeyUp:connect(function(key) 
if key:lower() == "w" then 
ctrl.f = 0 
elseif key:lower() == "s" then 
ctrl.b = 0 
elseif key:lower() == "a" then 
ctrl.l = 0 
elseif key:lower() == "d" then 
ctrl.r = 0 
end 
end)
Fly() 
end)

--Other-->

local Other = Window:NewTab("Other")
local OtherSection = Other:NewSection("Other")
OtherSection:NewButton("MadeBy (Gunna#8852)", "Discord UserName", function()
    print("Clicked")
end)
OtherSection:NewButton("https://discord.gg/9NHdwsZtS8", "Discord Server", function()
    print("Clicked")
end)
OtherSection:NewButton("Dm Gunna#8852 For Payed Gui's", "Dm Gunna (Gunna#8852)", function()
    print("Clicked")
end)
