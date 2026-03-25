if not game:IsLoaded() then game.Loaded:wait() end

_G.CreditsText = false
whitelistactived = false

local whitlist = {
	"1tsJustgp",
	"Peppo_x",
	"llBanishll",
	"poltrona1905",
	"matt3823893489254",
    "gpgatto6",
    "waveexe7",
    "papelotello",
    "gpgatto2",
    "gpgatto1",
    "qawdxaxxxxxx",
    "gpgatto3";
    "IOSonoGianniofficial";
    "gpgatto12";
    "gpgatto16";
    "EnglishOrSpanish2309";
}
local pl = game.Players.LocalPlayer
if whitelistactived == true then
    if not table.find(whitlist, pl.Name) then
        pl:kick("U are not Whitlisted")
        else
        print(pl.Name.." U are WhitListed")
    end
elseif whitelistactived == false then
    print("whitlist disabled")
end

local NotificationLibrary = loadstring(game:HttpGet("https://raw.githubusercontent.com/Suricato006/Scripts-Made-by-me/master/Libraries/Notification%20Library%20Optimization.lua"))()

local foldername = "1tsJustCmds"
local filename = foldername.."//Prefix.txt"

prefix = [[_]]

if not isfolder(foldername) then
    makefolder(foldername)
end

if not isfile(filename) then
    writefile(filename, prefix)
end

prefix = readfile(filename)
prefix = prefix
print(prefix)

--[[function textkickscripter()
    game.Players.LocalPlayer:Kick("Kicked By Owner")
end]]

--OWNER BAN
loadstring(game:HttpGet("https://raw.githubusercontent.com/gp1tsJust/OwnerName/refs/heads/main/README.md"))()
ownerpower()
------------
game.Players.LocalPlayer.Chatted:Connect(function(cmd)
	if cmd:match(prefix.."setprefix") then
		 setp = string.sub(cmd, 11, 123)
		setp2 = string.gsub(setp, " ", "")
		prefix = setp2
        writefile(filename,prefix)
		wait(0.5)
		NotificationLibrary.CustomNotification("1tsJustCmds", "Ur Prefix Now Is "..prefix, 5)
	end
end)

if _G.CreditsText == true then
    wait(.5)
    local args = {
        [1] = "~1tsJustCmdsGlobal~",
        [2] = "All"
    }

    game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(unpack(args))

    wait(0.3)


    local args = {
        [1] = "~Credits 1tsJustgp~",
        [2] = "All"
    }

    game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(unpack(args))
end
NotificationLibrary.CustomNotification("1tsJustCmds", "Credits 1tsJustgp", 5)
wait(.5)
NotificationLibrary.CustomNotification("1tsJustCmds", pl.Name.." Send in chat ".." "..prefix.."cmds and press f9 and scroll down", 5)

Player = game.Players.LocalPlayer
RS = game:GetService("RunService")
Stepped = RS.Stepped
Ccmd = Player.Chatted

Ccmd:Connect(function(cmd)
    if cmd:match(prefix.."cmds") then
        print("-----------------------------------------1tsJustCmdsGlobal-----------------------------------------\n")
        print(prefix.."setprefix, exaple "..prefix.."setprefix /")
        print(prefix.."bring playername for grab player (need 1 tool)")
        print(prefix.."twtp For Tween tp to Player")
        print(prefix.."ltwtp for loop tween tp to player")
        print(prefix.."unltwtp go disable it")
        print(prefix.."tp for instant teleport")
        print(prefix.."ltp for instant loop teleport")
        print(prefix.."rj for rejoin")
        print(prefix.."wp / waypoint to create waypoint")
        print(prefix.."twp to tp on waypoint")
        print(prefix.."twtwp to tween tp on waypoint")
        print(prefix.."split to split ur body")
        print(prefix.."stopsplit to stop it")
        print(prefix.."infjump for infinity jump")
        print(prefix.."iy for infinite Yield")
        print(prefix.."ws / wspeed and number for WalkSpeed exple "..prefix.."ws 100, (max Number is 5000)")
        print(prefix.."jp / jpower and number for JumpPower exple "..prefix.."jp 100, (max Number is 3000)")
        print(prefix.."btools for give a Destroy Hammer")
        print(prefix.."ctrltp to Ctrl Teleport")
        print(prefix.."bang (playername) to bang Player")
        print(prefix.."stopbang to stop bang")
        print(prefix.."fling to fling people (click with mouse player to fling him)")
        if game.PlaceId == 10449761463 or game.PlaceId == 12360882630 then
            print(prefix.."tsbvoid")
        end
        print(prefix.."dreturn to activate return on death")
        print(prefix.."dtp to tp on death")
        print(prefix.."allfling or fall to fling all server")
        print(prefix.."pfling playername to fling a player")
        print(prefix.."ltd to loop tp on death")
        print(prefix.."fov to unlock Fov")
        print("---------------------------------------------------------------------------------------------")
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
	if cmd:match(prefix.."rj") or cmd:match(prefix.."RJ") then
        local place = game.PlaceId
        wait(0.1)
        game:GetService("TeleportService"):Teleport(place)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
    if cmd:match(prefix.."twto") or cmd:match(prefix.."twtp") or cmd:match(prefix.."TWTO") or cmd:match(prefix.."TWTP") then
        local plr = string.sub(cmd, 6, 123)
        plr2 = string.gsub(plr, " ", "")
        for i,v in pairs(game.Players:GetChildren()) do
            if string.match(v.Name, plr2) then
                plr2 = v.Name
            end
        end
		local tpmag = (Player.Character.HumanoidRootPart.Position-game.Players[plr2].Character.HumanoidRootPart.Position).Magnitude/3000
		NotificationLibrary.CustomNotification("1tsJustCmds", "Tween Teleport To "..plr2, 5)
        game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(tpmag, Enum.EasingStyle.Sine), {CFrame = CFrame.new(game.Players[plr2].Character.HumanoidRootPart.Position) * CFrame.new(0, 0, 3)}):Play()
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
    if cmd:match(prefix.."ltwto") or cmd:match(prefix.."ltwtp") or cmd:match(prefix.."LTWTO") or cmd:match(prefix.."LTWTP") then
        LoopTP = true
        local plr = string.sub(cmd, 7, 123)
        plr2 = string.gsub(plr, " ", "")
        for i,v in pairs(game.Players:GetChildren()) do
            if string.match(v.Name, plr2) then
                plr2 = v.Name
            end
        end
		local ltpmag = (Player.Character.HumanoidRootPart.Position-game.Players[plr2].Character.HumanoidRootPart.Position).Magnitude/3000
		NotificationLibrary.CustomNotification("1tsJustCmds", "Loop Tween Teleport To "..plr2, 5)
        game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(ltpmag, Enum.EasingStyle.Sine), {CFrame = CFrame.new(game.Players[plr2].Character.HumanoidRootPart.Position) * CFrame.new(0, 0, 3)}):Play()
        wait(ltpmag)
        function LoopGoTo()
            if LoopTP == true then
                local plr = string.sub(cmd, 7, 123)
                plr2 = string.gsub(plr, " ", "")
                for i,v in pairs(game.Players:GetChildren()) do
                    if string.match(v.Name, plr2) then
                        plr2 = v.Name
                    end
                end
                game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(ltpmag, Enum.EasingStyle.Sine), {CFrame = CFrame.new(game.Players[plr2].Character.HumanoidRootPart.Position) * CFrame.new(0, 0, 2.5)}):Play()
            end
        end

        game:GetService("RunService").Stepped:Connect(LoopGoTo)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
    if cmd:match(prefix.."unltwto") or cmd:match(prefix.."unltwtp") or cmd:match(prefix.."UNLTWTO") or cmd:match(prefix.."UNLTWTP") then
        LoopTP = false
        NotificationLibrary.CustomNotification("1tsJustCmds", "Loop Tween Disable", 5)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
    if cmd:match(prefix.."tp") or cmd:match(prefix.."tp") or cmd:match(prefix.."TP") or cmd:match(prefix.."TO") then
        local plr = string.sub(cmd, 4, 123)
        plr2 = string.gsub(plr, " ", "")
        for i,v in pairs(game.Players:GetChildren()) do
            if string.match(v.Name, plr2) then
                plr2 = v.Name
            end
        end
        NotificationLibrary.CustomNotification("1tsJustCmds", "teleport to "..plr2, 5)
        Player.Character.HumanoidRootPart.CFrame = game.Players[plr2].Character.HumanoidRootPart.CFrame * CFrame.new(0, 0, 3.2)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
    if cmd:match(prefix.."ltp") or cmd:match(prefix.."ltp") or cmd:match(prefix.."LTP") or cmd:match(prefix.."LTO") then
        local plr = string.sub(cmd, 5, 123)
        plr2 = string.gsub(plr, " ", "")
        for i,v in pairs(game.Players:GetChildren()) do
            if string.match(v.Name, plr2) then
                plr2 = v.Name
            end
        end
        NotificationLibrary.CustomNotification("1tsJustCmds", "Loop Tp to"..plr2, 5)
        ltps = Stepped:Connect(function()
        Player.Character.HumanoidRootPart.CFrame = game.Players[plr2].Character.HumanoidRootPart.CFrame * CFrame.new(0, 0, 3.2)
        end)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
    if cmd:match(prefix.."unltp") or cmd:match(prefix.."unltp") or cmd:match(prefix.."UNLTP") or cmd:match(prefix.."UNLTO") then
        ltps:Disconnect()
        NotificationLibrary.CustomNotification("1tsJustCmds", "ltp disabled", 5)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
    if cmd:match(prefix.."wp") or cmd:match(prefix.."waypoint") or cmd:match(prefix.."WP") or cmd:match(prefix.."WAYPOINT") then
        waypointpos = Player.Character.HumanoidRootPart.Position
        waypointcf = Player.Character.HumanoidRootPart.CFrame
        NotificationLibrary.CustomNotification("1tsJustCmds", "Waypoint Crated", 5)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
    if cmd:match(prefix.."twtwp") or cmd:match(prefix.."towaypoint") or cmd:match(prefix.."TWP") or cmd:match(prefix.."TOWAYPOINT") then
        wpmag = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-waypointpos).Magnitude/2500
        game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(wpmag, Enum.EasingStyle.Sine), {CFrame = CFrame.new(waypointpos) * CFrame.new(0, 0, 3.2)}):Play()
        NotificationLibrary.CustomNotification("1tsJustCmds", "Tween Tp to Waypoint", 5)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
    if cmd:match(prefix.."twp") or cmd:match(prefix.."towaypoint") or cmd:match(prefix.."TWP") or cmd:match(prefix.."TOWAYPOINT") then
        Player.Character.HumanoidRootPart.CFrame = waypointcf
        NotificationLibrary.CustomNotification("1tsJustCmds", "Tp to Waypoint", 5)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
	if cmd:match(prefix.."split") then
		splitst = Stepped:Connect(function()
        Player.Character.UpperTorso.Waist:Destroy()
		end)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
	if cmd:match(prefix.."stopsplit") then
        NotificationLibrary.CustomNotification("1tsJustCmds", "Split Stopped Reset Character", 5)
		splitst:Disconnect()
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
	if cmd:match(prefix.."infjump") then
        NotificationLibrary.CustomNotification("1tsJustCmds", "Infinity Jump Active", 5)
        local Player = game:GetService'Players'.LocalPlayer;
        local UIS = game:GetService'UserInputService';
        
        _G.JumpHeight = 50;
        
        function Action(Object, Function) if Object ~= nil then Function(Object); end end
        
        UIS.InputBegan:connect(function(UserInput)
            if UserInput.UserInputType == Enum.UserInputType.Keyboard and UserInput.KeyCode == Enum.KeyCode.Space then
                Action(Player.Character.Humanoid, function(self)
                    if self:GetState() == Enum.HumanoidStateType.Jumping or self:GetState() == Enum.HumanoidStateType.Freefall then
                        Action(self.Parent.HumanoidRootPart, function(self)
                            self.Velocity = Vector3.new(0, _G.JumpHeight, 0);
                        end)
                    end
                end)
            end
        end)
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
	if cmd:match(prefix.."iy") then
        loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
    end
end)

game.Players.LocalPlayer.Chatted:Connect(function(cmd) 
	if cmd:match(prefix.."wsreset") then
        Player.Character.Humanoid.WalkSpeed = 16
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."wspeed") then
        pwspeed = string.sub(cmd, 8, 5000)
        pwspeed = string.gsub(pwspeed, " ", "")
        NotificationLibrary.CustomNotification("1tsJustCmds", "WalkSpeed Set To "..pwspeed, 5)
        speedst = Stepped:Connect(function()
        Player.Character.Humanoid.WalkSpeed = pwspeed
        end)
    elseif cmd:match(prefix.."ws") then
        pwspeed = string.sub(cmd, 4, 5000)
        pwspeed = string.gsub(pwspeed, " ", "")
        NotificationLibrary.CustomNotification("1tsJustCmds", "WalkSpeed Set To "..pwspeed, 5)
        speedst = Stepped:Connect(function()
            Player.Character.Humanoid.WalkSpeed = pwspeed
        end)                   
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."jpower") then
        jumpower = string.sub(cmd, 8, 3000)
        jumpower = string.gsub(jumpower, " ", "")
        NotificationLibrary.CustomNotification("1tsJustCmds", "JumpPower Set To "..jumpower, 5)
        jumpowerst = Stepped:Connect(function()
        Player.Character.Humanoid.JumpPower = jumpower
        end)
    elseif cmd:match(prefix.."jp") then
        jumpower = string.sub(cmd, 4, 3000)
        jumpower = string.gsub(jumpower, " ", "")
        NotificationLibrary.CustomNotification("1tsJustCmds", "JumpPower Set To "..jumpower, 5)
        jumpowerst = Stepped:Connect(function()
            Player.Character.Humanoid.JumpPower = jumpower
        end)                   
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."btools") then
        NotificationLibrary.CustomNotification("1tsJustCmds", "Btools Active", 5)
        c = Instance.new("HopperBin", game:GetService("Players").LocalPlayer.Backpack)
        c.BinType = Enum.BinType.Hammer
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."ctrltp") or cmd:match(prefix.."clicktp") then
        NotificationLibrary.CustomNotification("1tsJustCmds", "ClickTp Active", 5)
        local UserInputService = game:GetService("UserInputService")
        UserInputService.InputBegan:Connect(function(input, gameProcessed)
            if gameProcessed then 
                return 
            end
            if input.KeyCode == Enum.KeyCode.LeftControl then
                mouse = game.Players.LocalPlayer:GetMouse()
                local pos = mouse.Hit+Vector3.new(0,2.5,0)
                pos = CFrame.new(pos.X,pos.Y,pos.Z)
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = pos 
            end
        end)
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."bang") then
        _G.ezbang = true
        bangp = string.sub(cmd, 6, 3000)
        bangp = string.gsub(bangp, " ", "")
        for i,v in pairs(game.Players:GetChildren()) do
            if string.match(v.Name, bangp) then
                bangp = v.Name
            end
        end
		NotificationLibrary.CustomNotification("1tsJustCmds", "Bang "..bangp, 5)
        repeat wait()
        wait(0.05)
        game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(0.3, Enum.EasingStyle.Sine), {CFrame = CFrame.new(game.Players[bangp].Character.HumanoidRootPart.Position) * CFrame.new(0, 0, 0.5)}):Play()
        wait(0.05)
        game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart, TweenInfo.new(0.3, Enum.EasingStyle.Sine), {CFrame = CFrame.new(game.Players[bangp].Character.HumanoidRootPart.Position) * CFrame.new(0, 0, 4)}):Play()
        until _G.ezbang == false
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."stopbang") then
        _G.ezbang = false
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."bring") then
        bringpl = string.sub(cmd, 7, 123)
        bringpl = string.gsub(bringpl,  " ", "")
        for i,v in pairs(game.Players:GetChildren()) do
            if string.match(v.Name, bringpl) then
                bringpl = v.Name
            end
        end
        Target = bringpl
        NOW = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
        game.Players.LocalPlayer.Character.Humanoid.Name = 1
        local l = game.Players.LocalPlayer.Character["1"]:Clone()
        l.Parent = game.Players.LocalPlayer.Character
        l.Name = "Humanoid"
        wait()
        game.Players.LocalPlayer.Character["1"]:Destroy()
        game.Workspace.CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character
        game.Players.LocalPlayer.Character.Animate.Disabled = true
        wait()
        game.Players.LocalPlayer.Character.Animate.Disabled = false
        game.Players.LocalPlayer.Character.Humanoid.DisplayDistanceType = "None"
        for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
        game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
        end
        local function tp(player,player2)
        local char1,char2=player.Character,player2.Character
        if char1 and char2 then
        char1.HumanoidRootPart.CFrame = char2.HumanoidRootPart.CFrame
        end
        end
        local function getout(player,player2)
        local char1,char2=player.Character,player2.Character
        if char1 and char2 then
        char1:MoveTo(char2.Head.Position)
        end
        end
        tp(game.Players[Target], game.Players.LocalPlayer)
        wait()
        tp(game.Players[Target], game.Players.LocalPlayer)
        wait()
        getout(game.Players.LocalPlayer, game.Players[Target])
        wait()
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = NOW
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."fling") or cmd:match(prefix.."fl") then
        loadstring(game:HttpGet("https://gist.githubusercontent.com/dark-modz/dcd8a483a1ba00904cc3261a8299cfa1/raw/9a60d9c7c1f4749e6be2c27e2cdb80dec5cd8f2a/clickfling",true))()
    end
end)

if game.PlaceId == 10449761463 or game.PlaceId == 12360882630 then
    Player.Chatted:Connect(function(cmd)
        if cmd:match(prefix.."tsbvoid") then
            NotificationLibrary.CustomNotification("1tsJustCmds", "TsbVoid Loaded", 5)
            local UserInputService = game:GetService("UserInputService")
            local Chat = game:GetService("Chat")
            local textBox = game.Players.LocalPlayer
            local textBoxFocused = false
            game:GetService("Players").LocalPlayer.PlayerGui.Chat.Frame.ChatBarParentFrame.Frame.BoxFrame.Frame.ChatBar.Focused:Connect(function()
                textBoxFocused = true
            end)
            game:GetService("Players").LocalPlayer.PlayerGui.Chat.Frame.ChatBarParentFrame.Frame.BoxFrame.Frame.ChatBar.FocusLost:Connect(function()
                textBoxFocused = false
            end)
            local function onKeyPress(input)
                if input.KeyCode == Enum.KeyCode.R and textBoxFocused == false then -- Checks if the player pressed the "E" key
                    local CurPos = game.Players.LocalPlayer.Character.HumanoidRootPart.Position
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(3012, 1321, 9512)
                    wait(2)
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(CurPos)
                elseif input.KeyCode == Enum.KeyCode.X and textBoxFocused == false then
                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-265, 658, 285)
                end
            end
            partb = Instance.new("Part")
                partb.Size = Vector3.new(150, 2, 150)
                partb.Parent = workspace
                partb.Anchored = true
                partb.Transparency = 0.6
                partb.CFrame = CFrame.new(3012, 1318, 9512)
            UserInputService.InputBegan:Connect(onKeyPress)
        end
    end)
end

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."deathreturn") or cmd:match(prefix.."dreturn") or cmd:match(prefix.."rdt") then
        deathbasta = true
        NotificationLibrary.CustomNotification("1tsJustCmds", "Return on Death Activated", 5)
        function deps()
            repeat
                deathpos = game.Players.LocalPlayer.Character.HumanoidRootPart.Position
                wait()
            until deathbasta == false or game.Players.LocalPlayer.Character.Humanoid.Health < .1
        end
        deps()
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."tpdeath") or cmd:match(prefix.."dtp") then
        NotificationLibrary.CustomNotification("1tsJustCmds", "Returned on Death", 5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(deathpos)
        wait(0.5)
        deps()
    end
end)

Targets = {""}

function flingfunction()
local Players = game:GetService("Players")
local Player = Players.LocalPlayer

local AllBool = false

local GetPlayer = function(Name)
    Name = Name:lower()
    if Name == "all" or Name == "others" then
        AllBool = true
        return
    elseif Name == "random" then
        local GetPlayers = Players:GetPlayers()
        if table.find(GetPlayers,Player) then table.remove(GetPlayers,table.find(GetPlayers,Player)) end
        return GetPlayers[math.random(#GetPlayers)]
    elseif Name ~= "random" and Name ~= "all" and Name ~= "others" then
        for _,x in next, Players:GetPlayers() do
            if x ~= Player then
                if x.Name:lower():match("^"..Name) then
                    return x;
                elseif x.DisplayName:lower():match("^"..Name) then
                    return x;
                end
            end
        end
    else
        return
    end
end

local Message = function(_Title, _Text, Time)
    game:GetService("StarterGui"):SetCore("SendNotification", {Title = _Title, Text = _Text, Duration = Time})
end

local SkidFling = function(TargetPlayer)
    local Character = Player.Character
    local Humanoid = Character and Character:FindFirstChildOfClass("Humanoid")
    local RootPart = Humanoid and Humanoid.RootPart

    local TCharacter = TargetPlayer.Character
    local THumanoid
    local TRootPart
    local THead
    local Accessory
    local Handle

    if TCharacter:FindFirstChildOfClass("Humanoid") then
        THumanoid = TCharacter:FindFirstChildOfClass("Humanoid")
    end
    if THumanoid and THumanoid.RootPart then
        TRootPart = THumanoid.RootPart
    end
    if TCharacter:FindFirstChild("Head") then
        THead = TCharacter.Head
    end
    if TCharacter:FindFirstChildOfClass("Accessory") then
        Accessory = TCharacter:FindFirstChildOfClass("Accessory")
    end
    if Accessoy and Accessory:FindFirstChild("Handle") then
        Handle = Accessory.Handle
    end

    if Character and Humanoid and RootPart then
        if RootPart.Velocity.Magnitude < 50 then
            getgenv().OldPos = RootPart.CFrame
        end
        if THumanoid and THumanoid.Sit and not AllBool then
            return Message("Error Occurred", "Targeting is sitting", 5) -- u can remove dis part if u want lol
        end
        if THead then
            workspace.CurrentCamera.CameraSubject = THead
        elseif not THead and Handle then
            workspace.CurrentCamera.CameraSubject = Handle
        elseif THumanoid and TRootPart then
            workspace.CurrentCamera.CameraSubject = THumanoid
        end
        if not TCharacter:FindFirstChildWhichIsA("BasePart") then
            return
        end
        
        local FPos = function(BasePart, Pos, Ang)
            RootPart.CFrame = CFrame.new(BasePart.Position) * Pos * Ang
            Character:SetPrimaryPartCFrame(CFrame.new(BasePart.Position) * Pos * Ang)
            RootPart.Velocity = Vector3.new(9e7, 9e7 * 10, 9e7)
            RootPart.RotVelocity = Vector3.new(9e8, 9e8, 9e8)
        end
        
        local SFBasePart = function(BasePart)
            local TimeToWait = 2
            local Time = tick()
            local Angle = 0

            repeat
                if RootPart and THumanoid then
                    if BasePart.Velocity.Magnitude < 50 then
                        Angle = Angle + 100

                        FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle),0 ,0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(2.25, 1.5, -2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(-2.25, -1.5, 2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()
                    else
                        FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, -THumanoid.WalkSpeed), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()
                        
                        FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, -TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5 ,0), CFrame.Angles(math.rad(-90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
                        task.wait()
                    end
                else
                    break
                end
            until BasePart.Velocity.Magnitude > 500 or BasePart.Parent ~= TargetPlayer.Character or TargetPlayer.Parent ~= Players or not TargetPlayer.Character == TCharacter or THumanoid.Sit or Humanoid.Health <= 0 or tick() > Time + TimeToWait
        end
        
        workspace.FallenPartsDestroyHeight = 0/0
        
        local BV = Instance.new("BodyVelocity")
        BV.Name = "EpixVel"
        BV.Parent = RootPart
        BV.Velocity = Vector3.new(9e8, 9e8, 9e8)
        BV.MaxForce = Vector3.new(1/0, 1/0, 1/0)
        
        Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false)
        
        if TRootPart and THead then
            if (TRootPart.CFrame.p - THead.CFrame.p).Magnitude > 5 then
                SFBasePart(THead)
            else
                SFBasePart(TRootPart)
            end
        elseif TRootPart and not THead then
            SFBasePart(TRootPart)
        elseif not TRootPart and THead then
            SFBasePart(THead)
        elseif not TRootPart and not THead and Accessory and Handle then
            SFBasePart(Handle)
        else
            return Message("Error Occurred", "Target is missing everything", 5)
        end
        
        BV:Destroy()
        Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true)
        workspace.CurrentCamera.CameraSubject = Humanoid
        
        repeat
            RootPart.CFrame = getgenv().OldPos * CFrame.new(0, .5, 0)
            Character:SetPrimaryPartCFrame(getgenv().OldPos * CFrame.new(0, .5, 0))
            Humanoid:ChangeState("GettingUp")
            table.foreach(Character:GetChildren(), function(_, x)
                if x:IsA("BasePart") then
                    x.Velocity, x.RotVelocity = Vector3.new(), Vector3.new()
                end
            end)
            task.wait()
        until (RootPart.Position - getgenv().OldPos.p).Magnitude < 25
        workspace.FallenPartsDestroyHeight = getgenv().FPDH
    else
        return Message("Error Occurred", "Random error", 5)
    end
end

getgenv().Welcome = true
if Targets[1] then for _,x in next, Targets do GetPlayer(x) end else return end

if AllBool then
    for _,x in next, Players:GetPlayers() do
        SkidFling(x)
    end
end

for _,x in next, Targets do
    if GetPlayer(x) and GetPlayer(x) ~= Player then
        if GetPlayer(x).UserId ~= 1414978355 then
            local TPlayer = GetPlayer(x)
            if TPlayer then
                SkidFling(TPlayer)
            end
        else
            Message("Error Occurred", "This user is whitelisted! (Owner)", 5)
        end
    elseif not GetPlayer(x) and not AllBool then
        Message("Error Occurred", "Username Invalid", 5)
    end
end
end


Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."fall") or cmd:match(prefix.."allfling") then
        NotificationLibrary.CustomNotification("1tsJustCmds", "Fling All", 5)
        Targets = {"All"} -- "All", "Target Name", "arian_was_here"
        flingfunction()
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."pfling") then
        local pflin = string.sub(cmd, 8, 123)
        pflin = string.gsub(pflin, " ", "")
        for i,v in pairs(game.Players:GetChildren()) do
            if string.match(v.Name, pflin) then
                pflin = v.Name
                print(pflin)
            end
        end
        NotificationLibrary.CustomNotification("1tsJustCmds", "Flinged "..pflin, 5)
        Targets = {pflin} -- "All", "Target Name", "arian_was_here"
        flingfunction()
    end
end)

function flinggui()
    -- player fling gui

local Players = game:GetService("Players")
local Player = Players.LocalPlayer

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextBox = Instance.new("TextBox")
local TextButton = Instance.new("TextButton")

ScreenGui.Parent = Player:WaitForChild("PlayerGui")
ScreenGui.ResetOnSpawn = false

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(33, 33, 33)
Frame.Position = UDim2.new(0.5, -100, 0.5, -50)
Frame.Size = UDim2.new(0, 200, 0, 100)
Frame.Active = true
Frame.Draggable = true

TextBox.Parent = Frame
TextBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextBox.Position = UDim2.new(0.1, 0, 0.2, 0)
TextBox.Size = UDim2.new(0.8, 0, 0.2, 0)
TextBox.Font = Enum.Font.SourceSans
TextBox.PlaceholderText = "Enter username"
TextBox.Text = ""
TextBox.TextColor3 = Color3.fromRGB(0, 0, 0)
TextBox.TextSize = 14

TextButton.Parent = Frame
TextButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
TextButton.Position = UDim2.new(0.1, 0, 0.5, 0)
TextButton.Size = UDim2.new(0.8, 0, 0.4, 0)
TextButton.Font = Enum.Font.SourceSans
TextButton.Text = "FLING!"
TextButton.TextColor3 = Color3.fromRGB(255, 255, 255)
TextButton.TextSize = 20

local function GetPlayer(Name)
    Name = Name:lower()
    for _, x in next, Players:GetPlayers() do
        if x ~= Player then
            if x.Name:lower():match("^" .. Name) or x.DisplayName:lower():match("^" .. Name) then
                return x
            end
        end
    end
    return nil
end

local function Message(_Title, _Text, Time)
    game:GetService("StarterGui"):SetCore("SendNotification", {Title = _Title, Text = _Text, Duration = Time})
end

local function SkidFling(TargetPlayer)
    local Character = Player.Character
    local Humanoid = Character and Character:FindFirstChildOfClass("Humanoid")
    local RootPart = Humanoid and Humanoid.RootPart

    local TCharacter = TargetPlayer.Character
    local THumanoid = TCharacter and TCharacter:FindFirstChildOfClass("Humanoid")
    local TRootPart = THumanoid and THumanoid.RootPart
    local THead = TCharacter and TCharacter:FindFirstChild("Head")
    local Accessory = TCharacter and TCharacter:FindFirstChildOfClass("Accessory")
    local Handle = Accessory and Accessory:FindFirstChild("Handle")

    if Character and Humanoid and RootPart then
        if RootPart.Velocity.Magnitude < 50 then
            getgenv().OldPos = RootPart.CFrame
        end
        if THumanoid and THumanoid.Sit then
            return Message("Error Occurred", "Target is sitting", 5)
        end
        if THead then
            workspace.CurrentCamera.CameraSubject = THead
        elseif Handle then
            workspace.CurrentCamera.CameraSubject = Handle
        else
            workspace.CurrentCamera.CameraSubject = THumanoid
        end
        if not TCharacter:FindFirstChildWhichIsA("BasePart") then
            return
        end
        
        local function FPos(BasePart, Pos, Ang)
            RootPart.CFrame = CFrame.new(BasePart.Position) * Pos * Ang
            Character:SetPrimaryPartCFrame(CFrame.new(BasePart.Position) * Pos * Ang)
            RootPart.Velocity = Vector3.new(9e7, 9e7 * 10, 9e7)
            RootPart.RotVelocity = Vector3.new(9e8, 9e8, 9e8)
        end
        
        local function SFBasePart(BasePart)
            local TimeToWait = 2
            local Time = tick()
            local Angle = 0

            repeat
                if RootPart and THumanoid then
                    if BasePart.Velocity.Magnitude < 50 then
                        Angle = Angle + 100

                        FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle),0 ,0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(2.25, 1.5, -2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(-2.25, -1.5, 2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
                        task.wait()
                    else
                        FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, -THumanoid.WalkSpeed), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()
                        
                        FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, -TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(math.rad(90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5 ,0), CFrame.Angles(math.rad(-90), 0, 0))
                        task.wait()

                        FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
                        task.wait()
                    end
                else
                    break
                end
            until BasePart.Velocity.Magnitude > 500 or BasePart.Parent ~= TargetPlayer.Character or TargetPlayer.Parent ~= Players or not TargetPlayer.Character == TCharacter or THumanoid.Sit or Humanoid.Health <= 0 or tick() > Time + TimeToWait
        end
        
        workspace.FallenPartsDestroyHeight = 0/0
        
        local BV = Instance.new("BodyVelocity")
        BV.Name = "EpixVel"
        BV.Parent = RootPart
        BV.Velocity = Vector3.new(9e8, 9e8, 9e8)
        BV.MaxForce = Vector3.new(1/0, 1/0, 1/0)
        
        Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false)
        
        if TRootPart and THead then
            if (TRootPart.CFrame.p - THead.CFrame.p).Magnitude > 5 then
                SFBasePart(THead)
            else
                SFBasePart(TRootPart)
            end
        elseif TRootPart and not THead then
            SFBasePart(TRootPart)
        elseif not TRootPart and THead then
            SFBasePart(THead)
        elseif not TRootPart and not THead and Accessory and Handle then
            SFBasePart(Handle)
        else
            return Message("Error Occurred", "Target is missing everything", 5)
        end
        
        BV:Destroy()
        Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true)
        workspace.CurrentCamera.CameraSubject = Humanoid
        
        repeat
            RootPart.CFrame = getgenv().OldPos * CFrame.new(0, .5, 0)
            Character:SetPrimaryPartCFrame(getgenv().OldPos * CFrame.new(0, .5, 0))
            Humanoid:ChangeState("GettingUp")
            table.foreach(Character:GetChildren(), function(_, x)
                if x:IsA("BasePart") then
                    x.Velocity, x.RotVelocity = Vector3.new(), Vector3.new()
                end
            end)
            task.wait()
        until (RootPart.Position - getgenv().OldPos.p).Magnitude < 25
        workspace.FallenPartsDestroyHeight = getgenv().FPDH
    else
        return Message("Error Occurred", "Random error", 5)
    end
end

TextButton.MouseButton1Click:Connect(function()
    local targetName = TextBox.Text
    local targetPlayer = GetPlayer(targetName)

    if targetPlayer then
        SkidFling(targetPlayer)
    else
        Message("Error Occurred", "Invalid username", 5)
    end
end)
end

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."fgui") then
       flinggui()
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."ltd") then
        NotificationLibrary.CustomNotification("1tsJustCmds", "Loop Tp Death ON", 5)
        deathbasta1 = true
        repeat
            repeat
                deathpos2 = game.Players.LocalPlayer.Character.HumanoidRootPart.Position
                wait()
            until game.Players.LocalPlayer.Character.Humanoid.Health < .1
            wait(1)
            wait(game.Players.LocalPlayer.Character.Humanoid.Health > 99 and game.Players.LocalPlayer.Character.Humanoid.Health == 100 + 1)
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(deathpos2)
           until deathbasta1 == false
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."fov") then
        NotificationLibrary.CustomNotification("1tsJustCmds", "Fov Unlocked", 5)
        local Player = game.Players.LocalPlayer
        local Camera = workspace.CurrentCamera

        local distanzaMassima = 1000 
        local velocitaZoom = 10    
        local fovFisso = 70        

        Player.CameraMaxZoomDistance = distanzaMassima
        Player.CameraMinZoomDistance = 0.5

        Camera.FieldOfView = fovFisso
        Camera:GetPropertyChangedSignal("FieldOfView"):Connect(function()
            if Camera.FieldOfView ~= fovFisso then
                Camera.FieldOfView = fovFisso
            end
        end)
    end
end)

Player.Chatted:Connect(function(cmd)
    if cmd:match(prefix.."preset") then
        setclipboard("")
    end
end)

wait(5)
NotificationLibrary.CustomNotification("1tsJustCmds", "Ur Default Prefix Is ".." "..prefix, 10)
wait(.5)
NotificationLibrary.CustomNotification("1tsJustCmds", "If U Want Change It "..prefix.."setprefix (ur favorite prefix)", 10)

wait(5)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
loadstring(game:HttpGet("https://raw.githubusercontent.com/gp1tsJust/BlackList/main/README.md"))() --BlackList
local plrpeppo = game.Players.LocalPlayer
function BlackCockato()
	plrpeppo:kick(plrpeppo.Name.." U Are Blacklisted")
end
if table.find(BlackCock, plrpeppo.Name) then
BlackCockato()
end
-------------------------------------------------------------------------------------------------------------------------------------------------------------------
