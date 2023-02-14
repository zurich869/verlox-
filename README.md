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
