local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("verlox", "BloodTheme")
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


