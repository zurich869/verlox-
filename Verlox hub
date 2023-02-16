local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Verlox hub script⭐", "BloodTheme")
--main
local Main = Window:NewTab("Main")
local MainSection = Main:NewSection("Main")


MainSection:NewToggle("inf jump", "makes you jump high", function(state)
    if state then
        local InfiniteJumpEnabled = true
game:GetService("UserInputService").JumpRequest:connect(function()
    if InfiniteJumpEnabled then
        game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
    end
end)
    else
        local InfiniteJumpEnabled = false
game:GetService("UserInputService").JumpRequest:connect(function()
    if InfiniteJumpEnabled then
        game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping")
    end
end)
    end
end)


MainSection:NewButton("Infinite Yield ", "FE Admin commands", function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()

end)

MainSection:NewButton("hood modded script ", "This gives u aimlock in hood modded", function()
    local Settings = { AimLock = { Enabled = true, Aimlockkey = "q", Prediction = 0.130340, Aimpart = 'HumanoidRootPart', Notifications = true }, Settings = { Thickness = 3.5, Transparency = 1, Color = Color3.fromRGB(106, 13, 173), FOV = true } } local CurrentCamera = game:GetService("Workspace").CurrentCamera local Inset = game:GetService("GuiService"):GetGuiInset().Y local RunService = game:GetService("RunService") local Mouse = game.Players.LocalPlayer:GetMouse() local LocalPlayer = game.Players.LocalPlayer local Line = Drawing.new("Line") local Circle = Drawing.new("Circle") local Plr = game.Players.LocalPlayer Mouse.KeyDown:Connect(function(KeyPressed) if KeyPressed == (Settings.AimLock.Aimlockkey) then if Settings.AimLock.Enabled == true then Settings.AimLock.Enabled = false if Settings.AimLock.Notifications == true then Plr = FindClosestPlayer() game.StarterGui:SetCore("SendNotification", { Title = "p", Text = "Unlocked" }) end else Plr = FindClosestPlayer() Settings.AimLock.Enabled = true if Settings.AimLock.Notifications == true then game.StarterGui:SetCore("SendNotification", { Title = "p", Text = "Locked On : " .. tostring(Plr.Character.Humanoid.DisplayName) }) end end end end) function FindClosestPlayer() local ClosestDistance, ClosestPlayer = math.huge, nil; for _, Player in next, game:GetService("Players"):GetPlayers() do if Player ~= LocalPlayer then local Character = Player.Character if Character and Character.Humanoid.Health > 1 then local Position, IsVisibleOnViewPort = CurrentCamera:WorldToViewportPoint(Character.HumanoidRootPart .Position) if IsVisibleOnViewPort then local Distance = (Vector2.new(Mouse.X, Mouse.Y) - Vector2.new(Position.X, Position.Y)).Magnitude if Distance < ClosestDistance then ClosestPlayer = Player ClosestDistance = Distance end end end end end return ClosestPlayer, ClosestDistance end RunService.Heartbeat:connect(function() if Settings.AimLock.Enabled == true then local Vector = CurrentCamera:WorldToViewportPoint(Plr.Character[Settings.AimLock.Aimpart].Position + (Plr.Character[Settings.AimLock.Aimpart].Velocity * Settings.AimLock.Prediction)) Line.Color = Settings.Settings.Color Line.Transparency = Settings.Settings .Transparency Line.Thickness = Settings.Settings .Thickness Line.From = Vector2.new(Mouse.X, Mouse.Y + Inset) Line.To = Vector2.new(Vector.X, Vector.Y) Line.Visible = true Circle.Position = Vector2.new(Mouse.X, Mouse.Y + Inset) Circle.Visible = Settings.Settings.FOV Circle.Thickness = 1.5 Circle.Thickness = 2 Circle.Radius = 60 Circle.Color = Settings.Settings.Color elseif Settings.AimLock.FOV == true then Circle.Visible = true else Circle.Visible = false Line.Visible = false end end) local mt = getrawmetatable(game) local old = mt.__namecall setreadonly(mt, false) mt.__namecall = newcclosure(function(...) local args = {...} if Settings.AimLock.Enabled and getnamecallmethod() == "FireServer" and args[2] == "MousePos" then args[3] = Plr.Character[Settings.AimLock.Aimpart].Position + (Plr.Character[Settings.AimLock.Aimpart].Velocity * Settings.AimLock.Prediction) return old(unpack(args)) end return old(...) end)
end)


--LOCAL PLAYER
local Player = Window:NewTab("Player")
local PlayerSection = Player:NewSection("Player")

PlayerSection:NewSlider("Walkspeed", "Speed", 500, 16, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)

PlayerSection:NewSlider("jumpower", "jump high", 350, 50, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.Jumpower = s
end)

PlayerSection:NewButton("reset WS/JP", "Reset to all defualt ", function()
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = 50
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 16
end)


--OTHER
local Other = Window:NewTab("Other")
local OtherSection = Other:NewSection("Other")

OtherSection:NewButton("Chat Spoofer", "Chat to other people ", function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/ant-7802/--/main/straightmilk.lua'))()
end)

OtherSection:NewButton("bypass fly", "bird mode", function()
    local speed = 50
    local bodyvelocityenabled = true
    
    local Imput = game:GetService("UserInputService")
    local Plr = game.Players.LocalPlayer
    local nextmsgspd = false
    local nextmsgrc = false
    local flying = true
    local rc = 5
    local Mouse = Plr:GetMouse()
    local cn
    local cn1
    local cn2
    local cn3
    local cn4
    local currentTween
    
    local speedPart = Instance.new("Part", workspace)
    speedPart.Anchored = true
    speedPart.Transparency = 1
    speedPart.CanCollide = false
    speedPart.Size = Vector3.new(10, 25, 10)
    
    function To(position)
    if not flying then return end
    local Chr = Plr.Character
    if Chr ~= nil then
    local ts = game:GetService("TweenService")
    local char = game.Players.LocalPlayer.Character
    local hm = char.HumanoidRootPart
    local dist = (hm.Position - Mouse.Hit.p).magnitude
    local tweenspeed = dist/tonumber(speed)
    local ti = TweenInfo.new(tonumber(tweenspeed), Enum.EasingStyle.Linear)
    local tp = {CFrame = CFrame.new(position)}
    currentTween = ts:Create(hm, ti, tp)
    currentTween:Play()
    if bodyvelocityenabled == true then
    local bv = Instance.new("BodyVelocity")
    bv.Name = "BypassedFlyBodyVelocity"
    bv.Parent = hm
    bv.MaxForce = Vector3.new(100000,100000,100000)
    bv.Velocity = Vector3.new(0,0,0)
    wait(tonumber(tweenspeed))
    bv:Destroy()
    end
    end
    end
    
    cn4 = Imput.InputBegan:Connect(function(input)
        if input.KeyCode == Enum.KeyCode.F then
            flying = not flying
            for i,v in pairs(Plr.Character:GetDescendants()) do
                if v.Name == "BypassedFlyBodyVelocity" then
                    v:Destroy()
                end
            end
        end
    end)
    
    cn = Plr.Chatted:Connect(function(msg)
        if nextmsgspd then
            speed = tonumber(msg)
            nextmsgspd = false
        end
        if nextmsgrc then
            rc = tonumber(msg)
            nextmsgrc = false
        end
        if string.lower(tostring(msg)) == "set fly speed" then
            nextmsgspd = true
        end
        if string.lower(tostring(msg)) == "toggle visibility" then
            if speedPart.Transparency == 1 then
                speedPart.Transparency = .75
            else speedPart.Transparency = 1
            end
        end
        if string.lower(tostring(msg)) == "set rc" then
            nextmsgrc = true
        end
        if string.lower(tostring(msg)) == "unload fly" then
            cn:Disconnect()
            cn1:Disconnect()
            cn2:Disconnect()
            cn3:Disconnect()
            cn4:Disconnect()
            speedPart:Destroy()
            flying = false
            wait(.1)
            for i,v in pairs(Plr.Character:GetDescendants()) do
                if v.Name == "BypassedFlyBodyVelocity" then
                    v:Destroy()
                end
            end
            spawn(function()
                currentTween:Cancel()
            end)
            print("Unloaded.")
        end
    end)
    
    local mousePressed = false
    
    cn1 = Mouse.Button1Down:Connect(function()
        mousePressed = true
    end)
    
    cn2 = Mouse.Button1Up:Connect(function()
        mousePressed = false
        if currentTween then
            currentTween:Cancel()
        end
    end)
    
    local btz = 0
    cn3 = game:GetService("RunService").Heartbeat:Connect(function()
        speedPart.CFrame = CFrame.new(Plr.Character.HumanoidRootPart.Position + (Mouse.UnitRay.Direction * 15), Plr.Character.HumanoidRootPart.Position)
        if flying and mousePressed and btz >= rc then
            btz = 0
            if currentTween then
                currentTween:Cancel()
            end
            To(Plr.Character.HumanoidRootPart.Position + (Mouse.UnitRay.Direction * 50) + Vector3.new(0, 2.5, 0))
        end
        btz = btz + 1
    end)
    wait(.03)
    print("Bypassed fly loaded")
end)




OtherSection:NewButton("Prison life script ", "FE Admin commands", function()
-- Gui to Lua
-- Version: 3.2
-- Script Created by verlox

FavoriteColor = Color3.fromRGB(0, 0, 255) --(Red, Green, Blue) from 0 to 255

local function getGuns()
	--Remington870--------------------------------------------
	game.Workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["Remington 870"].ITEMPICKUP) --Remington 870
	----------------------------------------------------------

	--M4A1----------------------------------------------------
	if (game:GetService("MarketplaceService"):UserOwnsGamePassAsync(game.Players.LocalPlayer.UserId, 96651)) then
		game.Workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["M4A1"].ITEMPICKUP)
	else --If you don't have gamepass for M4A1 then you will get the converted AK-47
		game.Workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["AK-47"].ITEMPICKUP) 
		require(game.Players.LocalPlayer.Backpack:FindFirstChild("AK-47"):FindFirstChild("GunStates"))["FireRate"] = 0.09
	end
	----------------------------------------------------------
	
	--AK-47---------------------------------------------------
	if (game:GetService("MarketplaceService"):UserOwnsGamePassAsync(game.Players.LocalPlayer.UserId, 96651)) then
		--If you don't have gamepass for M4A1 then you will not get this AK-47
		game.Workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["AK-47"].ITEMPICKUP)
	end
	----------------------------------------------------------
	
	--M9---------------------------------------------------
	game.Workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["M9"].ITEMPICKUP)
	if game.Players.LocalPlayer:FindFirstChild("M9") then
		game.Players.LocalPlayer:FindFirstChild("M9").Parent = game.Players.LocalPlayer.Backpack
	end
	-------------------------------------------------------
end

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local ObGuns = Instance.new("TextButton")
local NexusTP = Instance.new("TextButton")
local BackTP = Instance.new("TextButton")
local BeGuardF = Instance.new("TextButton")
local BeInmate = Instance.new("TextButton")
local BeCriminal = Instance.new("TextButton")
local BeNeutral = Instance.new("TextButton")
local YardTP = Instance.new("TextButton")
local CafeTP = Instance.new("TextButton")
local Refresh = Instance.new("TextButton")
local Respawn = Instance.new("TextButton")
local BeGuard = Instance.new("TextButton")
local CellsTP = Instance.new("TextButton")
local Lock = Instance.new("TextButton")
local ArmoryTP = Instance.new("TextButton")
local ChatEnabled = true
local BubblesEnabled = true

--Properties:
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Frame.BorderColor3 = FavoriteColor
Frame.BorderSizePixel = 3
Frame.Position = UDim2.new(0.8, 0, 0.1, 0)
Frame.Size = UDim2.new(0, 200, 0, 300)
Frame.BorderMode = "Inset"

Title.Name = "Title"
Title.Parent = Frame
Title.AnchorPoint = Vector2.new(0.5, 0.5)
Title.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Title.BackgroundTransparency = 1.000
Title.BorderColor3 = Color3.fromRGB(0, 0, 0)
Title.Position = UDim2.new(0.5, 0, 0.0700000003, 0)
Title.Size = UDim2.new(0, 180, 0, 50)
Title.Font = Enum.Font.SourceSans
Title.Text = "Verlox script"
Title.TextColor3 = FavoriteColor
Title.TextScaled = true
Title.TextSize = 30.000
Title.TextWrapped = true

ObGuns.Name = "ObGuns"
ObGuns.Parent = Frame
ObGuns.AnchorPoint = Vector2.new(0.5, 0.5)
ObGuns.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ObGuns.BorderColor3 = FavoriteColor
ObGuns.BorderSizePixel = 2
ObGuns.Position = UDim2.new(0.275000006, 0, 0.200000003, 0)
ObGuns.Size = UDim2.new(0, 73, 0, 32)
ObGuns.Font = Enum.Font.SourceSans
ObGuns.Text = "Guns"
ObGuns.TextColor3 = FavoriteColor
ObGuns.TextSize = 25.000
ObGuns.TextWrapped = true
ObGuns.BorderMode = "Inset"

NexusTP.Name = "verlox TP"
NexusTP.Parent = Frame
NexusTP.AnchorPoint = Vector2.new(0.5, 0.5)
NexusTP.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
NexusTP.BorderColor3 = FavoriteColor
NexusTP.BorderSizePixel = 2
NexusTP.Position = UDim2.new(0.275000006, 0, 0.340000004, 0)
NexusTP.Size = UDim2.new(0, 73, 0, 32)
NexusTP.Font = Enum.Font.SourceSans
NexusTP.Text = "verlox"
NexusTP.TextColor3 = FavoriteColor
NexusTP.TextSize = 25.000
NexusTP.TextWrapped = true
NexusTP.BorderMode = "Inset"

BackTP.Name = "BackTP"
BackTP.Parent = Frame
BackTP.AnchorPoint = Vector2.new(0.5, 0.5)
BackTP.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
BackTP.BorderColor3 = FavoriteColor
BackTP.BorderSizePixel = 2
BackTP.Position = UDim2.new(0.275000006, 0, 0.479999989, 0)
BackTP.Size = UDim2.new(0, 73, 0, 32)
BackTP.Font = Enum.Font.SourceSans
BackTP.Text = "Go behind the cafe"
BackTP.TextColor3 = FavoriteColor
BackTP.TextSize = 25.000
BackTP.TextWrapped = true
BackTP.BorderMode = "Inset"

BeGuardF.Name = "BeGuardF"
BeGuardF.Parent = Frame
BeGuardF.AnchorPoint = Vector2.new(0.5, 0.5)
BeGuardF.BackgroundColor3 = Color3.fromRGB(9, 0, 77)
BeGuardF.BorderColor3 = FavoriteColor
BeGuardF.BorderSizePixel = 2
BeGuardF.Position = UDim2.new(0.680000007, 0, 0.224999994, 0)
BeGuardF.Size = UDim2.new(0, 20, 0, 17)
BeGuardF.SizeConstraint = Enum.SizeConstraint.RelativeXX
BeGuardF.ZIndex = 3
BeGuardF.Font = Enum.Font.SourceSans
BeGuardF.Text = ""
BeGuardF.TextColor3 = FavoriteColor
BeGuardF.TextSize = 25.000
BeGuardF.TextWrapped = true
BeGuardF.BorderMode = "Inset"

BeInmate.Name = "BeInmate"
BeInmate.Parent = Frame
BeInmate.AnchorPoint = Vector2.new(0.5, 0.5)
BeInmate.BackgroundColor3 = Color3.fromRGB(92, 40, 1)
BeInmate.BorderColor3 = FavoriteColor
BeInmate.BorderSizePixel = 2
BeInmate.Position = UDim2.new(0.589999974, 0, 0.200000003, 0)
BeInmate.Size = UDim2.new(0, 20, 0, 32)
BeInmate.ZIndex = 2
BeInmate.Font = Enum.Font.SourceSans
BeInmate.Text = ""
BeInmate.TextColor3 = FavoriteColor
BeInmate.TextSize = 25.000
BeInmate.TextWrapped = true
BeInmate.BorderMode = "Inset"

BeCriminal.Name = "BeCriminal"
BeCriminal.Parent = Frame
BeCriminal.AnchorPoint = Vector2.new(0.5, 0.5)
BeCriminal.BackgroundColor3 = Color3.fromRGB(96, 0, 1)
BeCriminal.BorderColor3 = FavoriteColor
BeCriminal.BorderSizePixel = 2
BeCriminal.Position = UDim2.new(0.769999981, 0, 0.200000003, 0)
BeCriminal.Size = UDim2.new(0, 20, 0, 32)
BeCriminal.ZIndex = 2
BeCriminal.Font = Enum.Font.SourceSans
BeCriminal.Text = ""
BeCriminal.TextColor3 = FavoriteColor
BeCriminal.TextSize = 25.000
BeCriminal.TextWrapped = true
BeCriminal.BorderMode = "Inset"

BeNeutral.Name = "BeNeutral"
BeNeutral.Parent = Frame
BeNeutral.AnchorPoint = Vector2.new(0.5, 0.5)
BeNeutral.BackgroundColor3 = Color3.fromRGB(140, 140, 140)
BeNeutral.BorderColor3 = FavoriteColor
BeNeutral.BorderSizePixel = 2
BeNeutral.Position = UDim2.new(0.860000014, 0, 0.200000003, 0)
BeNeutral.Size = UDim2.new(0, 20, 0, 32)
BeNeutral.ZIndex = 2
BeNeutral.Font = Enum.Font.SourceSans
BeNeutral.Text = ""
BeNeutral.TextColor3 = FavoriteColor
BeNeutral.TextSize = 25.000
BeNeutral.TextWrapped = true
BeNeutral.BorderMode = "Inset"

YardTP.Name = "YardTP"
YardTP.Parent = Frame
YardTP.AnchorPoint = Vector2.new(0.5, 0.5)
YardTP.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
YardTP.BorderColor3 = FavoriteColor
YardTP.BorderSizePixel = 2
YardTP.Position = UDim2.new(0.725000024, 0, 0.340000004, 0)
YardTP.Size = UDim2.new(0, 73, 0, 32)
YardTP.Font = Enum.Font.SourceSans
YardTP.Text = "Yard"
YardTP.TextColor3 = FavoriteColor
YardTP.TextSize = 25.000
YardTP.TextWrapped = true
YardTP.BorderMode = "Inset"

CafeTP.Name = "CafeTP"
CafeTP.Parent = Frame
CafeTP.AnchorPoint = Vector2.new(0.5, 0.5)
CafeTP.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
CafeTP.BorderColor3 = FavoriteColor
CafeTP.BorderSizePixel = 2
CafeTP.Position = UDim2.new(0.725000024, 0, 0.479999989, 0)
CafeTP.Size = UDim2.new(0, 73, 0, 32)
CafeTP.Font = Enum.Font.SourceSans
CafeTP.Text = "Cafe"
CafeTP.TextColor3 = FavoriteColor
CafeTP.TextSize = 25.000
CafeTP.TextWrapped = true
CafeTP.BorderMode = "Inset"

Refresh.Name = "Refresh"
Refresh.Parent = Frame
Refresh.AnchorPoint = Vector2.new(0.5, 0.5)
Refresh.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Refresh.BorderColor3 = FavoriteColor
Refresh.BorderSizePixel = 2
Refresh.Position = UDim2.new(0.275000006, 0, 0.899999976, 0)
Refresh.Size = UDim2.new(0, 73, 0, 32)
Refresh.Font = Enum.Font.SourceSans
Refresh.Text = "Re"
Refresh.TextColor3 = FavoriteColor
Refresh.TextSize = 25.000
Refresh.TextWrapped = true
Refresh.BorderMode = "Inset"

Respawn.Name = "Respawn"
Respawn.Parent = Frame
Respawn.Active = false
Respawn.AnchorPoint = Vector2.new(0.5, 0.5)
Respawn.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Respawn.BorderColor3 = FavoriteColor
Respawn.BorderSizePixel = 2
Respawn.Position = UDim2.new(0.725000024, 0, 0.899999976, 0)
Respawn.Size = UDim2.new(0, 73, 0, 32)
Respawn.Font = Enum.Font.SourceSans
Respawn.Text = "Spawn"
Respawn.TextColor3 = FavoriteColor
Respawn.TextSize = 25.000
Respawn.TextWrapped = true
Respawn.BorderMode = "Inset"

BeGuard.Name = "BeGuard"
BeGuard.Parent = Frame
BeGuard.AnchorPoint = Vector2.new(0.5, 0.5)
BeGuard.BackgroundColor3 = Color3.fromRGB(9, 0, 77)
BeGuard.BorderColor3 = FavoriteColor
BeGuard.BorderSizePixel = 2
BeGuard.Position = UDim2.new(0.680000007, 0, 0.174999997, 0)
BeGuard.Size = UDim2.new(0, 20, 0, 17)
BeGuard.SizeConstraint = Enum.SizeConstraint.RelativeXX
BeGuard.ZIndex = 3
BeGuard.Font = Enum.Font.SourceSans
BeGuard.Text = ""
BeGuard.TextColor3 = FavoriteColor
BeGuard.TextSize = 25.000
BeGuard.TextWrapped = true
BeGuard.BorderMode = "Inset"

CellsTP.Name = "CellsTP"
CellsTP.Parent = Frame
CellsTP.AnchorPoint = Vector2.new(0.5, 0.5)
CellsTP.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
CellsTP.BorderColor3 = FavoriteColor
CellsTP.BorderSizePixel = 2
CellsTP.Position = UDim2.new(0.725000024, 0, 0.620000005, 0)
CellsTP.Size = UDim2.new(0, 73, 0, 32)
CellsTP.Font = Enum.Font.SourceSans
CellsTP.Text = "Cells"
CellsTP.TextColor3 = FavoriteColor
CellsTP.TextSize = 25.000
CellsTP.TextWrapped = true
CellsTP.BorderMode = "Inset"

Lock.Name = "Lock"
Lock.Parent = Frame
Lock.AnchorPoint = Vector2.new(0.5, 0.5)
Lock.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Lock.BorderColor3 = FavoriteColor
Lock.BorderSizePixel = 2
Lock.Position = UDim2.new(0.5, 0, 0.75999999, 0)
Lock.Size = UDim2.new(0, 156, 0, 32)
Lock.Font = Enum.Font.SourceSans
Lock.Text = "Lock"
Lock.TextColor3 = FavoriteColor
Lock.TextSize = 25.000
Lock.TextWrapped = true
Lock.BorderMode = "Inset"

ArmoryTP.Name = "ArmoryTP"
ArmoryTP.Parent = Frame
ArmoryTP.AnchorPoint = Vector2.new(0.5, 0.5)
ArmoryTP.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ArmoryTP.BorderColor3 = FavoriteColor
ArmoryTP.BorderSizePixel = 2
ArmoryTP.Position = UDim2.new(0.275000006, 0, 0.620000005, 0)
ArmoryTP.Size = UDim2.new(0, 73, 0, 32)
ArmoryTP.Font = Enum.Font.SourceSans
ArmoryTP.Text = "Armory"
ArmoryTP.TextColor3 = FavoriteColor
ArmoryTP.TextSize = 25.000
ArmoryTP.TextWrapped = true
ArmoryTP.BorderMode = "Inset"

ArmoryTP.MouseButton1Down:connect(function()
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(798,99,2260)
end)

BackTP.MouseButton1Down:connect(function()
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(980, 101, 2327)
end)

BeCriminal.MouseButton1Down:connect(function()
	local lastPos = game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart").position
	LCS = game.Workspace["Criminals Spawn"].SpawnLocation
	LCS.CanCollide = false
	LCS.Size = Vector3.new(51.05, 24.12, 54.76)
	LCS.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
	LCS.Transparency = 1
	wait(0.5)
	LCS.CFrame = CFrame.new(-920.510803, 92.2271957, 2138.27002, 0, 0, -1, 0, 1, 0, 1, 0, 0)
	LCS.Size = Vector3.new(6, 0.2, 6)
	LCS.Transparency = 0
	wait()
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(lastPos)
end)

BeGuard.MouseButton1Down:connect(function()
	Workspace.Remote.TeamEvent:FireServer("Bright blue")
end)

BeGuardF.MouseButton1Down:connect(function()
	local lastPos = game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart").position
	workspace.Remote.loadchar:InvokeServer("", "Bright blue")
	wait()
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(lastPos)
end)

BeInmate.MouseButton1Down:connect(function()
	Workspace.Remote.TeamEvent:FireServer("Bright orange")
end)

BeNeutral.MouseButton1Down:connect(function()
	Workspace.Remote.TeamEvent:FireServer("Medium stone grey")
end)

CafeTP.MouseButton1Down:connect(function()
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(879,99,2247)
end)

CellsTP.MouseButton1Down:connect(function()
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(910,99,2477)
end)

Lock.MouseButton1Down:connect(function()
	game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 24
	game.Players.LocalPlayer.Character.ClientInputHandler.Disabled = true
	game.Players.LocalPlayer.CharacterAdded:connect(function()
	game.Workspace:WaitForChild(game.Players.LocalPlayer.Name)
	game.Players.LocalPlayer.Character.ClientInputHandler.Disabled = true
	end)
end)

NexusTP.MouseButton1Down:connect(function()
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(879,99,2377)
end)

ObGuns.MouseButton1Down:connect(function()	
	if game.Players.LocalPlayer.Team.Name == "Criminals" then 
		if game.Players.LocalPlayer.Character:FindFirstChildOfClass("ForceField") then return end
	end
	getGuns()
end)

Refresh.MouseButton1Down:connect(function()
	if (game.Players.LocalPlayer.Team.Name ~= "Criminals") then
		local lastPos = game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart").position
		local plr = game.Players.LocalPlayer.Name
		local gayevent = game:GetService("Workspace").Remote.loadchar
		gayevent:InvokeServer(plr)
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(lastPos)
	else
		local lastPos = game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart").position
		Workspace.Remote.TeamEvent:FireServer("Bright orange")
		wait()
		local plr = game.Players.LocalPlayer.Name
		local gayevent = game:GetService("Workspace").Remote.loadchar
		gayevent:InvokeServer(plr)
		LCS = game.Workspace["Criminals Spawn"].SpawnLocation
		LCS.CanCollide = false
		LCS.Size = Vector3.new(51.05, 24.12, 54.76)
		LCS.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
		LCS.Transparency = 1
		wait(0.5)
		LCS.CFrame = CFrame.new(-920.510803, 92.2271957, 2138.27002, 0, 0, -1, 0, 1, 0, 1, 0, 0)
		LCS.Size = Vector3.new(6, 0.2, 6)
		LCS.Transparency = 0
		wait()
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(lastPos)
	end
end)

Respawn.MouseButton1Down:connect(function()
	local lastPos = game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart").position
	local plr = game.Players.LocalPlayer.Name
	local gayevent = game:GetService("Workspace").Remote.loadchar
	gayevent:InvokeServer(plr)
end)

YardTP.MouseButton1Down:connect(function()
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(779,99,2477)
end)

game:GetService("UserInputService").InputBegan:connect(function(inputObject, gameProcessedEvent)
	if gameProcessedEvent then return end
	local children = Frame:GetChildren()
    if inputObject.KeyCode == Enum.KeyCode.Q then
    	if Frame.BackgroundTransparency == 0 then
			Frame.BackgroundTransparency = 1
			for i, child in ipairs(children) do
				print(child.Name)
				child.BackgroundTransparency = 1
				child.TextTransparency = 1
			end
		else
			Frame.BackgroundTransparency = 0
			for i, child in ipairs(children) do
				if child.Name ~= "Title" then
					child.BackgroundTransparency = 0
				end
				child.TextTransparency = 0
			end
		end
    end
	if inputObject.KeyCode == Enum.KeyCode.Z then
		if ChatEnabled then
			ChatEnabled = false
			game:GetService("StarterGui"):SetCoreGuiEnabled(Enum.CoreGuiType.Chat, false)
			for i, player in pairs(game.Players:GetPlayers()) do
				player:WaitForChild("PlayerScripts").BubbleChat.Disabled = true
				player:WaitForChild("PlayerGui").BubbleChat:Destroy()
			end
		else
			ChatEnabled = true
			game:GetService("StarterGui"):SetCoreGuiEnabled(Enum.CoreGuiType.Chat, true)
			for i, player in pairs(game.Players:GetPlayers()) do
				player:WaitForChild("PlayerScripts").BubbleChat.Disabled = false
			end
		end
	end
	if inputObject.KeyCode == Enum.KeyCode.Slash then
		ChatEnabled = true
		game:GetService("StarterGui"):SetCoreGuiEnabled(Enum.CoreGuiType.Chat, true)
	end
	if inputObject.KeyCode == Enum.KeyCode.X then
		if BubblesEnabled then
			BubblesEnabled = false
			for i, player in pairs(game.Players:GetPlayers()) do
				player:WaitForChild("PlayerScripts").BubbleChat.Disabled = true
				player:WaitForChild("PlayerGui").BubbleChat:Destroy()
			end
		else
			BubblesEnabled = true
			for i, player in pairs(game.Players:GetPlayers()) do
				player:WaitForChild("PlayerScripts").BubbleChat.Disabled = false
			end
		end
	end
	if inputObject.KeyCode == Enum.KeyCode.E then
		if game.Players.LocalPlayer.Team.Name == "Criminals" then 
			if game.Players.LocalPlayer.Character:FindFirstChildOfClass("ForceField") then return end
		end
		if (game.Players.LocalPlayer.Backpack:FindFirstChild("M9")) then
			game.Players.LocalPlayer.Backpack:FindFirstChild("M9").Parent = game.Players.LocalPlayer
		end
		if (game.Players.LocalPlayer.Backpack:FindFirstChild("Taser")) then
			game.Players.LocalPlayer.Backpack.Taser:Destroy()
		end
		if (game.Players.LocalPlayer.Backpack:FindFirstChild("Handcuffs")) then
			game.Players.LocalPlayer.Backpack.Handcuffs:Destroy()
		end
		getGuns()
	end
end)



function dragify(Frame)
dragToggle = nil
dragSpeed = 100000 -- You can edit this.
dragInput = nil
dragStart = nil
dragPos = nil

function updateInput(input)
Delta = input.Position - dragStart
Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + Delta.X, startPos.Y.Scale, startPos.Y.Offset + Delta.Y)
game:GetService("TweenService"):Create(Frame, TweenInfo.new(0), {Position = Position}):Play()
end

Frame.InputBegan:Connect(function(input)
if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) then
dragToggle = true
dragStart = input.Position
startPos = Frame.Position
input.Changed:Connect(function()
if (input.UserInputState == Enum.UserInputState.End) then
dragToggle = false
end
end)
end
end)

Frame.InputChanged:Connect(function(input)
if (input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch) then
dragInput = input
end
end)

game:GetService("UserInputService").InputChanged:Connect(function(input)
if (input == dragInput and dragToggle) then
updateInput(input)
end
end)
end

dragify(Frame)

end)


OtherSection:NewButton("Prison life Aimlock", "this gives u aimlock", function()
 --https://www.youtube.com/c/anto6666 
-- // Constants \\ --
-- [ Services ] --
local Services = setmetatable({}, {__index = function(Self, Index)
    local NewService = game.GetService(game, Index)
    if NewService then
    Self[Index] = NewService
    end
    return NewService
    end})
    
    -- [ Modules ] --
    local UserInterface = loadstring(game:HttpGet("https://raw.githubusercontent.com/icuck/collection-dump/main/AbstractUI", true))()
    local Drawing = loadstring(game:HttpGet("https://raw.githubusercontent.com/iHavoc101/Genesis-Studios/main/Modules/DrawingAPI.lua", true))()
    
    local ToolTip = require(Services.ReplicatedStorage.Modules_client.TooltipModule)
    
    -- [ LocalPlayer ] --
    local LocalPlayer = Services.Players.LocalPlayer
    local Camera = workspace.CurrentCamera
    
    -- [ Raycast Parameters ] --
    local RaycastParameters = RaycastParams.new()
    RaycastParameters.IgnoreWater = true
    RaycastParameters.FilterType = Enum.RaycastFilterType.Blacklist
    RaycastParameters.FilterDescendantsInstances = {LocalPlayer.Character}
    
    -- // Variables \\ --
    -- [ Info ] --
    local Info = {
       SilentAIMEnabled = false;
       TriggeredEnabled = false;
       ArmsCheckEnabled = true;
       TeamWhitelist = "";
       FieldOfView = 250;
    }
    
    local LastArrest = time()
    
    -- [ Interface ] --
    local FOVCircle = Drawing.new("Circle", {
       Thickness = 2.5,
       Color = Color3.fromRGB(200, 200, 200),
       NumSides = 25,
       Radius = _G.FOV
    })
    
    local Target = Drawing.new("Triangle", {
       Thickness = 5,
       Color = Color3.fromRGB(0, 200, 255)
    })
    
    -- [ Weapons ] --
    local Weapons = {
       "Remington 870";
       "AK-47";
       "M9";
       "M4A1";
       "Hammer";
       "Crude Knife";
    }
    
    -- [ Metatable ] --
    local RawMetatable = getrawmetatable(game)
    local __NameCall = RawMetatable.__namecall
    local __Index = RawMetatable.__index
    
    
    -- // Functions \\ --
    local function ValidCharacter(Character)
       return Character and (Character.FindFirstChildWhichIsA(Character, "Humanoid") and Character.FindFirstChildWhichIsA(Character, "Humanoid").Health ~= 0) or false
    end
    
    local function NotObstructing(Destination, Ancestor)
       -- [ Camera ] --
       local ObstructingParts = Camera.GetPartsObscuringTarget(Camera, {Destination}, {Ancestor, LocalPlayer.Character})
    
       for i,v in ipairs(ObstructingParts) do
           pcall(function()
               if v.Transparency >= 1 then
                   table.remove(ObstructingParts, i)
               end
           end)
       end
    
       if #ObstructingParts <= 0 then
           return true
       end
    
       -- [ Raycast ] --
       RaycastParameters.FilterDescendantsInstances = {LocalPlayer.Character}
    
       local Origin = Camera.CFrame.Position
       local Direction = (Destination - Origin).Unit * 500
       local RayResult = workspace.Raycast(workspace, Origin, Direction, RaycastParameters) or {
           Instance = nil;
           Position = Origin + Direction;
           Material = Enum.Material.Air;
       }
    
       if RayResult.Instance and (RayResult.Instance.IsDescendantOf(RayResult.Instance, Ancestor) or RayResult.Instance == Ancestor) then
           return true
       end
    
       -- [ Obstructed ] --
       return false
    end
    
    local function IsArmed(Player)
       for i,v in ipairs(Weapons) do
           local Tool = Player.Backpack.FindFirstChild(Player.Backpack, v) or Player.Character.FindFirstChild(Player.Character, v)
           if Tool then
               return true
           end
       end
       return false
    end
    
    local function ClosestPlayerToCursor(Distance)
       local Closest = nil
       local Position = nil
       local ShortestDistance = Distance or math.huge
    
       local MousePosition = Services.UserInputService.GetMouseLocation(Services.UserInputService)
    
       for i, v in ipairs(Services.Players.GetPlayers(Services.Players)) do
           if v ~= LocalPlayer and (v.Team ~= LocalPlayer.Team and tostring(v.Team) ~= Info.TeamWhitelist) and ValidCharacter(v.Character) then
               if Info.ArmsCheckEnabled and (v.Team == Services.Teams.Inmates and IsArmed(v) == false) then
                   continue
               end
    
               local ViewportPosition, OnScreen = Camera.WorldToViewportPoint(Camera, v.Character.PrimaryPart.Position)
               local Magnitude = (Vector2.new(ViewportPosition.X, ViewportPosition.Y) - MousePosition).Magnitude
    
               if OnScreen == false or NotObstructing(v.Character.PrimaryPart.Position, v.Character) == false then
                   continue
               end
    
               if Magnitude < ShortestDistance  then
                   Closest = v
                   Position = ViewportPosition
                   ShortestDistance = Magnitude
               end
           end
       end
    
       return Closest, Position
    end
    
    local function SwitchGuns()
       if LocalPlayer.Character.FindFirstChild(LocalPlayer.Character, "Remington 870") then
           local Tool = LocalPlayer.Backpack.FindFirstChild(LocalPlayer.Backpack, "M4A1") or LocalPlayer.Backpack.FindFirstChild(LocalPlayer.Backpack, "AK-47") or LocalPlayer.Backpack.FindFirstChild(LocalPlayer.Backpack, "M9")
    
           local Humanoid = LocalPlayer.Character.FindFirstChildWhichIsA(LocalPlayer.Character, "Humanoid")
           Humanoid.EquipTool(Humanoid, Tool)
       else
           local Tool = LocalPlayer.Backpack.FindFirstChild(LocalPlayer.Backpack, "Remington 870")
    
           local Humanoid = LocalPlayer.Character.FindFirstChildWhichIsA(LocalPlayer.Character, "Humanoid")
           Humanoid.EquipTool(Humanoid, Tool)
       end
    end
    
    local function Crash(Gun, BulletCount, ShotCount)
       local ShootEvent = Services.ReplicatedStorage.ShootEvent
       local StartTime = time()
       local BulletTable = {}
    
       for i = 1, BulletCount do
           BulletTable[i] = {
               Cframe = CFrame.new(),
               Distance = math.huge
           }
       end
       for i = 1, ShotCount do
           ShootEvent:FireServer(BulletTable, Gun)
           if time() - StartTime > 5 then
               break
           end
       end
    end
    
    -- // User Interface \\ --
    -- [ Window ] --
    local Window = UserInterface.new("verlox aimlock", UDim2.new(0, 420, 0, 420))
    
    -- [ Assists ] --
    Window:Divider("Assists")
    
    Window:Toggle("Silent Aim", "Shoots toward the nearest player to your cursor.", false, function(State)
       Info.SilentAIMEnabled = State
    end)
    
    Window:Toggle("Trigger Bot", "Press G to temporarily disable.", false, function(State)
       Info.TriggeredEnabled = State
    end)
    
    Window:Slider("Field Of View", "Recommended: 250", 50, 500, 250, function(Value)
       Info.FieldOfView = Value
    end)
    
    Window:Dropdown("Team Whitelist", "Team for Silent-Aim to ignore.", {"Guards", "Inmates", "Criminals"}, function(Value)
       Info.TeamWhitelist = Value
    end)
    
    Window:Toggle("Danger Check", "Checks if an Inmate has gun.", false, function(State)
       Info.ArmsCheckEnabled = State
    end)
    
    -- [ Rage ] --
    Window:Divider("Rage")
    
    Window:Button("Kill All", "Kills everyone in-game", function()
       local GunScript = (LocalPlayer.Backpack:FindFirstChild("GunInterface", true) or LocalPlayer.Character:FindFirstChild("GunInterface", true))
       if GunScript then
           for i,v in ipairs(game.Players:GetPlayers()) do
               if v ~= LocalPlayer then
                   local BulletInfo = {
                       [1] = {
                           ["RayObject"] = Ray.new(Vector3.new(845.555908, 101.429337, 2269.43945), Vector3.new(-391.152252, 8.65560055, -83.2166901)),
                           ["Distance"] = 3.2524313926697,
                           ["Cframe"] = CFrame.new(840.310791, 101.334137, 2267.87988, 0.0636406094, 0.151434347, -0.986416459, 0, 0.988420188, 0.151741937, 0.997972965, -0.00965694897, 0.0629036576),
                           ["Hit"] = v.Character.Head
                       },
                       [2] = {
                           ["RayObject"] = Ray.new(Vector3.new(845.555908, 101.429337, 2269.43945), Vector3.new(-392.481476, -8.44939327, -76.7261353)),
                           ["Distance"] = 3.2699294090271,
                           ["Cframe"] = CFrame.new(840.290466, 101.184189, 2267.93506, 0.0964837447, 0.0589403138, -0.993587971, 4.65661287e-10, 0.998245299, 0.0592165813, 0.995334625, -0.00571343815, 0.0963144377),
                           ["Hit"] = v.Character.Head
                       },
                       [3] = {
                           ["RayObject"] = Ray.new(Vector3.new(845.555908, 101.429337, 2269.43945), Vector3.new(-389.21701, -2.50536323, -92.2163162)),
                           ["Distance"] = 3.1665518283844,
                           ["Cframe"] = CFrame.new(840.338867, 101.236496, 2267.80371, 0.0166504811, 0.0941716284, -0.995416701, 1.16415322e-10, 0.995554805, 0.0941846818, 0.999861419, -0.00156822044, 0.0165764652),
                           ["Hit"] = v.Character.Head
                       },
                       [4] = {
                           ["RayObject"] = Ray.new(Vector3.new(845.555908, 101.429337, 2269.43945), Vector3.new(-393.353973, 3.13988972, -72.5452042)),
                           ["Distance"] = 3.3218522071838,
                           ["Cframe"] = CFrame.new(840.277222, 101.285957, 2267.9707, 0.117109694, 0.118740402, -0.985994935, -1.86264515e-09, 0.992826641, 0.119563118, 0.993119001, -0.0140019981, 0.116269611),
                           ["Hit"] = v.Character.Head
                       },
                       [5] = {
                           ["RayObject"] = Ray.new(Vector3.new(845.555908, 101.429337, 2269.43945), Vector3.new(-390.73172, 3.2097764, -85.5477524)),
                           ["Distance"] = 3.222757101059,
                           ["Cframe"] = CFrame.new(840.317993, 101.286423, 2267.86035, 0.0517584644, 0.123365127, -0.991010666, 0, 0.992340803, 0.123530701, 0.99865967, -0.00639375951, 0.0513620302),
                           ["Hit"] = v.Character.Head
                       }
                   }
                   Services.ReplicatedStorage.ShootEvent:FireServer(BulletInfo, GunScript.Parent)
                   Services.ReplicatedStorage.ShootEvent:FireServer(BulletInfo, GunScript.Parent)
               end
           end
       else
           ToolTip.update("No gun found!")
       end
    end)
    
    Window:Button("Gun Modification", "Modifies the current gun you are holding.", function()
       local GunStates = LocalPlayer.Character:FindFirstChild("GunStates", true)
       if GunStates then
           local GunInfo = require(GunStates)
           GunInfo.ReloadTime = 0
           GunInfo.FireRate = 0
           GunInfo.AutoFire = true
           GunInfo.StoredAmmo = math.huge
           GunInfo.MaxAmmo = math.huge
           GunInfo.CurrentAmmo = math.huge
       end
    end)
    
    -- [ Miscellaneous ] --
    Window:Divider("Miscellaneous")
    
    Window:Button("Get Guns", "Grabs all", function()
       local HasSWAT = Services.MarketplaceService:UserOwnsGamePassAsync(LocalPlayer.UserId, 96651)
    
       workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["Remington 870"].ITEMPICKUP)
       if HasSWAT then
           workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["M4A1"].ITEMPICKUP)
       end
       workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["AK-47"].ITEMPICKUP)
       workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["M9"].ITEMPICKUP)
    
       if HasSWAT then
           workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.clothes["Riot Police"].ITEMPICKUP)
       end
    end)
    
    -- [ Credits ] --
    Window:Divider("Credits")
    
    Window:Button("OminousVibes#7259", "Script Creator", function()
       setclipboard("OminousVibes#7259")
    end)
    
    
    -- // Metatable \\ --
    setreadonly(RawMetatable, false)
    
    RawMetatable.__index = newcclosure(function(Self, Index)
       if Info.SilentAIMEnabled == true and checkcaller() == false then
           if typeof(Self) == "Instance" and (Self:IsA("PlayerMouse") or Self:IsA("Mouse")) then
               if Index == "Hit" then
                   local Closest = ClosestPlayerToCursor(Info.FieldOfView)
                   if Closest then
                       local Velocity = Closest.Character.PrimaryPart.AssemblyLinearVelocity
                       local Prediction = Velocity.Unit
                       if Velocity.Magnitude == 0 then
                           Prediction = Vector3.new(0, 0, 0)
                       end
                       return CFrame.new(Closest.Character.Head.Position + Prediction)
                   end
               end
           end
       end
    
       return __Index(Self, Index)
    end)
    
    
    setreadonly(RawMetatable, true)
    
    -- // Event Listeners \\ --
    Services.RunService.RenderStepped:Connect(function()
       if Info.SilentAIMEnabled == true then
           -- FOV --
           FOVCircle.Visible = true
           FOVCircle.Radius = Info.FieldOfView
           FOVCircle.Position = Services.UserInputService:GetMouseLocation()
    
           -- Target --
           local Closest, Position = ClosestPlayerToCursor(Info.FieldOfView)
           if Closest then
               Target.PointA = Vector2.new(Position.X - 25, Position.Y + 25)
               Target.PointB = Vector2.new(Position.X + 25, Position.Y + 25)
               Target.PointC = Vector2.new(Position.X, Position.Y - 25)
               if Info.TriggeredEnabled and not Services.UserInputService:IsKeyDown(Enum.KeyCode.G) then
                   mouse1click()
               end
           end
           Target.Visible = Closest ~= nil
       else
           FOVCircle.Visible = false
           Target.Visible = false
       end
    end)
    
    LocalPlayer.Chatted:Connect(function(Message)
       if string.find(Message:lower(), "-lag") then
           local GunScript = (LocalPlayer.Backpack:FindFirstChild("GunInterface", true) or LocalPlayer.Character:FindFirstChild("GunInterface", true))
           if GunScript then
               ToolTip.update("Lagging...")
               Crash(GunScript.Parent, 100, 10)
               ToolTip.update("Lagged!")
           else
              ToolTip.update("Error: No gun found!")
           end
       end
    end)
    
    local LastShotDetected = time()
    for i,v in ipairs(getconnections(Services.ReplicatedStorage.ReplicateEvent.OnClientEvent)) do
       local OldFunction = v.Function
       v.Function = function(BulletStats, IsTaser)
           if #BulletStats > 25 or time() - LastShotDetected > 0.02 then
               ToolTip.update("Bullet Overload: Removing...")
               return
           end
           LastShotDetected = time()
           OldFunction(BulletStats, IsTaser)
       end
    end
    
    local LastSoundDetected = time()
    for i,v in ipairs(getconnections(Services.ReplicatedStorage.SoundEvent.OnClientEvent)) do
       local OldFunction = v.Function
       v.Function = function(Sound)
           if time() - LastSoundDetected > 0.02 then
               ToolTip.update("Audio Overload: Removing...")
               return
           end
           LastSoundDetected = time()
           OldFunction(Sound)
       end
    end
    
    
    -- // KeyBinds \\ --
    Services.UserInputService.InputBegan:Connect(function(Input, GameProcessed)
       if _G.ArrestAssist == false or GameProcessed or LocalPlayer.Character:FindFirstChild("Handcuffs") == nil then
           return
       end
    
       local Delta = time() - LastArrest
       if Delta <= 15 then
           ToolTip.update("Wait " .. tostring(math.floor(Delta)) .. " seconds before arresting again!")
       end
    
       if Input.UserInputType == Enum.UserInputType.MouseButton1 then
           local Closest = ClosestPlayerToCursor(_G.FOV)
           if Closest then
               local Result = workspace.Remote.arrest:InvokeServer(Closest.Character.HumanoidRootPart)
               ToolTip.update(Result == true and "Successfully arrested!" or Result)
               if Result == true then
                   LastArrest = time()
               end
           end
       end
    end)
    
    Services.ContextActionService:BindAction("Switch Bind", function(actionName, InputState, inputObject)
    if InputState == Enum.UserInputState.End then
    return
       end
       pcall(SwitchGuns)
    end, false, Enum.KeyCode.Q)
    
    -- // Actions \\ --
    LocalPlayer.PlayerGui.Home.fadeFrame.Visible = false
    
    return {};   
end)


OtherSection:NewButton("Gui prison script", "it gives u fly and every commands for prison life", function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Denverrz/scripts/master/PRISONWARE_v1.3.txt"))()

end)
