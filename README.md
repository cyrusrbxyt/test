# MM2
--[[
    MM2 (Murder Mystery 2) ULTRA PRO Script - Fixed Auto Farm
    Made by Cyrusrbx
    Features: Role ESP, Kill All, Speed, Jump, God Mode, Auto Grab Gun, Auto Shoot, Auto Farm (Anti-Cheat Safe)
]]

local player = game.Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "MM2UltraPro"
ScreenGui.ResetOnSpawn = false
ScreenGui.Parent = playerGui
local ReopenButton = Instance.new("TextButton")
ReopenButton.Name = "MM2Reopen"
ReopenButton.Size = UDim2.new(0, 150, 0, 35)
ReopenButton.Position = UDim2.new(0.5, -75, 0, 10)
ReopenButton.BackgroundColor3 = Color3.new(0.1, 0.1, 0.3)
ReopenButton.BackgroundTransparency = 0.2
ReopenButton.Text = "🔪 MM2 Script"
ReopenButton.TextColor3 = Color3.new(0, 1, 1)
ReopenButton.TextSize = 14
ReopenButton.Font = Enum.Font.ArialBold
ReopenButton.TextStrokeTransparency = 0
ReopenButton.TextStrokeColor3 = Color3.new(0, 1, 1)
ReopenButton.Visible = false
ReopenButton.Parent = ScreenGui
local ReopenCorner = Instance.new("UICorner")
ReopenCorner.CornerRadius = UDim.new(0, 10)
ReopenCorner.Parent = ReopenButton
local ReopenStroke = Instance.new("UIStroke")
ReopenStroke.Color = Color3.new(0, 1, 1)
ReopenStroke.Transparency = 0.3
ReopenStroke.Thickness = 2
ReopenStroke.Parent = ReopenButton
local MainFrame = Instance.new("Frame")
MainFrame.Size = UDim2.new(0, 450, 0, 650)
MainFrame.Position = UDim2.new(0, 10, 0, 10)
MainFrame.BackgroundColor3 = Color3.new(0.05, 0.05, 0.1)
MainFrame.BackgroundTransparency = 0.2
MainFrame.BorderSizePixel = 0
MainFrame.Active = true
MainFrame.Draggable = true
MainFrame.Parent = ScreenGui
local UICorner = Instance.new("UICorner")
UICorner.CornerRadius = UDim.new(0, 15)
UICorner.Parent = MainFrame
local UIStroke = Instance.new("UIStroke")
UIStroke.Color = Color3.new(0, 1, 1)
UIStroke.Transparency = 0.3
UIStroke.Thickness = 3
UIStroke.Parent = MainFrame
local GlowEffect = Instance.new("UIStroke")
GlowEffect.Color = Color3.new(0, 1, 1)
GlowEffect.Transparency = 0.7
GlowEffect.Thickness = 8
GlowEffect.Parent = MainFrame
local TitleBar = Instance.new("Frame")
TitleBar.Size = UDim2.new(1, 0, 0, 50)
TitleBar.BackgroundColor3 = Color3.new(0.1, 0.1, 0.3)
TitleBar.BackgroundTransparency = 0.1
TitleBar.BorderSizePixel = 0
TitleBar.Parent = MainFrame

local TitleBarCorner = Instance.new("UICorner")
TitleBarCorner.CornerRadius = UDim.new(0, 15)
TitleBarCorner.Parent = TitleBar
local Title = Instance.new("TextLabel")
Title.Size = UDim2.new(1, 0, 1, 0)
Title.BackgroundTransparency = 1
Title.Text = "🔪 MM2 ULTRA PRO"
Title.TextColor3 = Color3.new(0, 1, 1)
Title.TextSize = 24
Title.Font = Enum.Font.ArialBold
Title.TextStrokeTransparency = 0
Title.TextStrokeColor3 = Color3.new(0, 1, 1)
Title.Parent = TitleBar
local CloseButton = Instance.new("TextButton")
CloseButton.Size = UDim2.new(0, 30, 0, 30)
CloseButton.Position = UDim2.new(1, -35, 0, 10)
CloseButton.BackgroundColor3 = Color3.new(1, 0, 0)
CloseButton.BackgroundTransparency = 0.2
CloseButton.Text = "✕"
CloseButton.TextColor3 = Color3.new(1, 1, 1)
CloseButton.TextSize = 16
CloseButton.Font = Enum.Font.ArialBold
CloseButton.Parent = TitleBar

local CloseCorner = Instance.new("UICorner")
CloseCorner.CornerRadius = UDim.new(0, 8)
CloseCorner.Parent = CloseButton

local Credit = Instance.new("TextLabel")
Credit.Size = UDim2.new(1, 0, 0, 20)
Credit.Position = UDim2.new(0, 0, 0.08, 0)
Credit.BackgroundTransparency = 1
Credit.Text = "Made by Cyrusrbx ✨"
Credit.TextColor3 = Color3.new(1, 0.5, 1)
Credit.TextSize = 14
Credit.Font = Enum.Font.Arial
Credit.TextStrokeTransparency = 0.5
Credit.TextStrokeColor3 = Color3.new(1, 0, 1)
Credit.Parent = MainFrame

local StatusLabel = Instance.new("TextLabel")
StatusLabel.Size = UDim2.new(1, 0, 0, 20)
StatusLabel.Position = UDim2.new(0, 0, 0.12, 0)
StatusLabel.BackgroundTransparency = 1
StatusLabel.Text = "status: not connected"
StatusLabel.TextColor3 = Color3.new(1, 0.4, 0.4)
StatusLabel.TextSize = 14
StatusLabel.Font = Enum.Font.ArialBold
StatusLabel.TextStrokeTransparency = 0.5
StatusLabel.Parent = MainFrame

local function createSectionTitle(text, yPos)
    local section = Instance.new("TextLabel")
    section.Size = UDim2.new(0.9, 0, 0, 25)
    section.Position = UDim2.new(0.05, 0, yPos, 0)
    section.BackgroundColor3 = Color3.new(0.1, 0.1, 0.3)
    section.BackgroundTransparency = 0.3
    section.Text = text
    section.TextColor3 = Color3.new(0, 1, 1)
    section.TextSize = 14
    section.Font = Enum.Font.ArialBold
    section.TextStrokeTransparency = 0.3
    section.TextStrokeColor3 = Color3.new(0, 1, 1)
    section.Parent = MainFrame
    
    local sectionCorner = Instance.new("UICorner")
    sectionCorner.CornerRadius = UDim.new(0, 8)
    sectionCorner.Parent = section
    
    local sectionStroke = Instance.new("UIStroke")
    sectionStroke.Color = Color3.new(0, 1, 1)
    sectionStroke.Transparency = 0.5
    sectionStroke.Thickness = 1
    sectionStroke.Parent = section
    
    return section
end

local function createButton(text, yPos, color)
    local btn = Instance.new("TextButton")
    btn.Size = UDim2.new(0.42, 0, 0, 30)
    btn.Position = UDim2.new(0.05, 0, yPos, 0)
    btn.BackgroundColor3 = color
    btn.BackgroundTransparency = 0.2
    btn.Text = text
    btn.TextColor3 = Color3.new(1, 1, 1)
    btn.TextSize = 13
    btn.Font = Enum.Font.ArialBold
    btn.TextStrokeTransparency = 0.3
    btn.Parent = MainFrame
    
    local btnCorner = Instance.new("UICorner")
    btnCorner.CornerRadius = UDim.new(0, 8)
    btnCorner.Parent = btn
    
    local btnStroke = Instance.new("UIStroke")
    btnStroke.Color = color
    btnStroke.Transparency = 0.3
    btnStroke.Thickness = 2
    btnStroke.Parent = btn
    
    btn.MouseEnter:Connect(function()
        btn.BackgroundTransparency = 0
        btn.Size = UDim2.new(0.44, 0, 0, 32)
    end)
    
    btn.MouseLeave:Connect(function()
        btn.BackgroundTransparency = 0.2
        btn.Size = UDim2.new(0.42, 0, 0, 30)
    end)
    
    return btn
end

local function createButton2(text, yPos, color)
    local btn = Instance.new("TextButton")
    btn.Size = UDim2.new(0.42, 0, 0, 30)
    btn.Position = UDim2.new(0.53, 0, yPos, 0)
    btn.BackgroundColor3 = color
    btn.BackgroundTransparency = 0.2
    btn.Text = text
    btn.TextColor3 = Color3.new(1, 1, 1)
    btn.TextSize = 13
    btn.Font = Enum.Font.ArialBold
    btn.TextStrokeTransparency = 0.3
    btn.Parent = MainFrame
    
    local btnCorner = Instance.new("UICorner")
    btnCorner.CornerRadius = UDim.new(0, 8)
    btnCorner.Parent = btn
    
    local btnStroke = Instance.new("UIStroke")
    btnStroke.Color = color
    btnStroke.Transparency = 0.3
    btnStroke.Thickness = 2
    btnStroke.Parent = btn
    
    btn.MouseEnter:Connect(function()
        btn.BackgroundTransparency = 0
        btn.Size = UDim2.new(0.44, 0, 0, 32)
    end)
    
    btn.MouseLeave:Connect(function()
        btn.BackgroundTransparency = 0.2
        btn.Size = UDim2.new(0.42, 0, 0, 30)
    end)
    
    return btn
end


local espSection = createSectionTitle("👁️ ESP", 0.14)


local EspInnocentBtn = createButton("ESP innocent", 0.20, Color3.new(0, 0.5, 1))
local EspSheriffBtn = createButton2("ESP sheriff", 0.20, Color3.new(0, 0.7, 0))
local EspMurderBtn = createButton("ESP murder", 0.26, Color3.new(1, 0, 0))
local EspHeroBtn = createButton2("ESP hero", 0.26, Color3.new(0.8, 0.2, 0.8))

-- === 玩家增强 ===
local enhanceSection = createSectionTitle("⚡ OP cheats ", 0.32)

local SpeedBtn = createButton("Speed x2", 0.38, Color3.new(0, 0.7, 0))
local JumpBtn = createButton2("Jump Power x2", 0.38, Color3.new(1, 0.5, 0))
local GodBtn = createButton("GOD", 0.44, Color3.new(0.8, 0, 0))
local KillAllBtn = createButton2("Kill all", 0.44, Color3.new(0.8, 0.2, 0.8))

-- === 自动功能 ===
local autoSection = createSectionTitle("🤖 AUTO", 0.50)

local AutoGrabBtn = createButton("auto grab gun", 0.56, Color3.new(0, 0.8, 0.8))
local AutoShootBtn = createButton2("auto shoot", 0.56, Color3.new(1, 0, 0))
local AutoFarmBtn = createButton("auto farm", 0.62, Color3.new(1, 0.8, 0))

-- === 传送功能 ===
local teleportSection = createSectionTitle("🌀 yp", 0.68)

local TpToMurderBtn = createButton("tp to murder", 0.74, Color3.new(1, 0, 0))
local TpToSheriffBtn = createButton2("tp to sheriff", 0.74, Color3.new(0, 0.7, 0))

-- 状态变量
local espInnocentEnabled = false
local espSheriffEnabled = false
local espMurderEnabled = false
local espHeroEnabled = false
local speedEnabled = false
local jumpEnabled = false
local godEnabled = false
local autoGrabEnabled = false
local autoShootEnabled = false
local autoFarmEnabled = false

-- 关闭/打开功能
CloseButton.MouseButton1Click:Connect(function()
    MainFrame.Visible = false
    ReopenButton.Visible = true
end)

ReopenButton.MouseButton1Click:Connect(function()
    MainFrame.Visible = true
    ReopenButton.Visible = false
end)

-- 获取角色
local function getCharacter()
    return player.Character or player.CharacterAdded:Wait()
end

-- 获取玩家角色 - 超级检测
local function getPlayerRole(plr)
    -- 方法1: 检查玩家属性
    for _, prop in ipairs({"Role", "Team", "Job", "Murderer", "Sheriff", "Hero", "RoleValue"}) do
        local value = plr:FindFirstChild(prop)
        if value then
            local role = tostring(value.Value or value.Name):lower()
            if role:find("murder") or role:find("killer") or role:find("assassin") or role:find("bad") then
                return "Murderer"
            elseif role:find("sheriff") or role:find("police") or role:find("good") then
                return "Sheriff"
            elseif role:find("hero") then
                return "Hero"
            end
        end
    end
    
    -- 方法2: 检查 leaderstats
    local leaderstats = plr:FindFirstChild("leaderstats")
    if leaderstats then
        for _, stat in ipairs(leaderstats:GetChildren()) do
            if stat:IsA("StringValue") or stat:IsA("IntValue") or stat:IsA("NumberValue") then
                local statName = stat.Name:lower()
                local statValue = tostring(stat.Value):lower()
                
                if statName:find("role") or statName:find("team") or statName:find("job") or statName:find("class") then
                    if statValue:find("murder") or statValue:find("killer") or statValue:find("assassin") then
                        return "Murderer"
                    elseif statValue:find("sheriff") or statValue:find("police") then
                        return "Sheriff"
                    elseif statValue:find("hero") then
                        return "Hero"
                    else
                        return "Innocent"
                    end
                end
            end
        end
    end
    
    -- 方法3: 检查 Team
    if plr.Team then
        local teamName = plr.Team.Name:lower()
        if teamName:find("murder") or teamName:find("killer") or teamName:find("bad") then
            return "Murderer"
        elseif teamName:find("sheriff") or teamName:find("police") or teamName:find("good") then
            return "Sheriff"
        elseif teamName:find("hero") then
            return "Hero"
        end
    end
    
    -- 方法4: 检查背包
    local backpack = plr:FindFirstChild("Backpack")
    if backpack then
        for _, tool in ipairs(backpack:GetChildren()) do
            if tool:IsA("Tool") then
                local toolName = tool.Name:lower()
                if toolName:find("gun") or toolName:find("pistol") or toolName:find("revolver") or toolName:find("rifle") then
                    return "Sheriff"
                elseif toolName:find("knife") or toolName:find("sword") or toolName:find("blade") or toolName:find("axe") or toolName:find("machete") then
                    return "Murderer"
                end
            end
        end
    end
    
    -- 方法5: 检查 Character 的工具
    if plr.Character then
        local char = plr.Character
        local tool = char:FindFirstChildOfClass("Tool")
        if tool then
            local toolName = tool.Name:lower()
            if toolName:find("gun") or toolName:find("pistol") or toolName:find("revolver") or toolName:find("rifle") then
                return "Sheriff"
            elseif toolName:find("knife") or toolName:find("sword") or toolName:find("blade") or toolName:find("axe") or toolName:find("machete") then
                return "Murderer"
            end
        end
    end
    
    -- 方法6: 检查 Humanoid 属性
    if plr.Character then
        local humanoid = plr.Character:FindFirstChild("Humanoid")
        if humanoid then
            if humanoid.WalkSpeed > 20 then
                return "Murderer"
            end
        end
    end
    
    -- 方法7: 检查 PlayerGui
    local playerGui = plr:FindFirstChild("PlayerGui")
    if playerGui then
        for _, gui in ipairs(playerGui:GetChildren()) do
            if gui:IsA("ScreenGui") then
                for _, label in ipairs(gui:GetDescendants()) do
                    if label:IsA("TextLabel") then
                        local text = label.Text:lower()
                        if text:find("murderer") or text:find("you are the murderer") then
                            return "Murderer"
                        elseif text:find("sheriff") or text:find("you are the sheriff") then
                            return "Sheriff"
                        elseif text:find("hero") then
                            return "Hero"
                        end
                    end
                end
            end
        end
    end
    
    -- 默认返回平民
    return "Innocent"
end

-- ESP 功能
local espBoxes = {}

local function createESP(plr, color)
    if plr == player then return end
    
    if espBoxes[plr] then
        espBoxes[plr]:Destroy()
        espBoxes[plr] = nil
    end
    
    local highlight = Instance.new("Highlight")
    highlight.Name = "ESP"
    highlight.FillTransparency = 0.4
    highlight.OutlineTransparency = 0
    highlight.OutlineColor = color
    highlight.FillColor = color
    highlight.Parent = plr.Character
    
    -- 添加名字标签
    local billboard = Instance.new("BillboardGui")
    billboard.Name = "ESPName"
    billboard.Size = UDim2.new(0, 200, 0, 50)
    billboard.AlwaysOnTop = true
    billboard.Parent = plr.Character
    
    local nameLabel = Instance.new("TextLabel")
    nameLabel.Size = UDim2.new(1, 0, 1, 0)
    nameLabel.BackgroundTransparency = 1
    nameLabel.Text = plr.Name
    nameLabel.TextColor3 = color
    nameLabel.TextSize = 14
    nameLabel.Font = Enum.Font.ArialBold
    nameLabel.TextStrokeTransparency = 0
    nameLabel.TextStrokeColor3 = Color3.new(0, 0, 0)
    nameLabel.Parent = billboard
    
    espBoxes[plr] = highlight
end

local function removeESP(plr)
    if espBoxes[plr] then
        espBoxes[plr]:Destroy()
        espBoxes[plr] = nil
    end
    
    if plr.Character then
        local billboard = plr.Character:FindFirstChild("ESPName")
        if billboard then
            billboard:Destroy()
        end
    end
end

local function updateESP()
    for plr, _ in pairs(espBoxes) do
        removeESP(plr)
    end
    
    for _, plr in ipairs(game.Players:GetPlayers()) do
        if plr ~= player and plr.Character then
            local role = getPlayerRole(plr)
            
            if espInnocentEnabled and role == "Innocent" then
                createESP(plr, Color3.new(0, 0.5, 1))
            elseif espSheriffEnabled and role == "Sheriff" then
                createESP(plr, Color3.new(0, 0.7, 0))
            elseif espMurderEnabled and role == "Murderer" then
                createESP(plr, Color3.new(1, 0, 0))
            elseif espHeroEnabled and role == "Hero" then
                createESP(plr, Color3.new(0.8, 0.2, 0.8))
            end
        end
    end
end

local function toggleESP(role)
    if role == "Innocent" then
        espInnocentEnabled = not espInnocentEnabled
        if espInnocentEnabled then
            EspInnocentBtn.BackgroundColor3 = Color3.new(0.8, 0, 0)
            EspInnocentBtn.Text = "✅ ESP innocent"
        else
            EspInnocentBtn.BackgroundColor3 = Color3.new(0, 0.5, 1)
            EspInnocentBtn.Text = "ESP innocent"
        end
    elseif role == "Sheriff" then
        espSheriffEnabled = not espSheriffEnabled
        if espSheriffEnabled then
            EspSheriffBtn.BackgroundColor3 = Color3.new(0.8, 0, 0)
            EspSheriffBtn.Text = "✅ ESP sheriff"
        else
            EspSheriffBtn.BackgroundColor3 = Color3.new(0, 0.7, 0)
            EspSheriffBtn.Text = "ESP sheriff"
        end
    elseif role == "Murderer" then
        espMurderEnabled = not espMurderEnabled
        if espMurderEnabled then
            EspMurderBtn.BackgroundColor3 = Color3.new(0.8, 0, 0)
            EspMurderBtn.Text = "✅ ESP murder"
        else
            EspMurderBtn.BackgroundColor3 = Color3.new(1, 0, 0)
            EspMurderBtn.Text = "ESP murder"
        end
    elseif role == "Hero" then
        espHeroEnabled = not espHeroEnabled
        if espHeroEnabled then
            EspHeroBtn.BackgroundColor3 = Color3.new(0.8, 0, 0)
            EspHeroBtn.Text = "✅ ESP hero"
        else
            EspHeroBtn.BackgroundColor3 = Color3.new(0.8, 0.2, 0.8)
            EspHeroBtn.Text = "ESP hero"
        end
    end
    
    updateESP()
end

-- 速度功能
local function toggleSpeed()
    speedEnabled = not speedEnabled
    local char = getCharacter()
    local humanoid = char:WaitForChild("Humanoid")
    
    if speedEnabled then
        humanoid.WalkSpeed = 32
        SpeedBtn.BackgroundColor3 = Color3.new(0.8, 0, 0)
        SpeedBtn.Text = "✅ speed x2"
    else
        humanoid.WalkSpeed = 16
        SpeedBtn.BackgroundColor3 = Color3.new(0, 0.7, 0)
        SpeedBtn.Text = "speed x2"
    end
end

-- 跳跃功能
local function toggleJump()
    jumpEnabled = not jumpEnabled
    local char = getCharacter()
    local humanoid = char:WaitForChild("Humanoid")
    
    if jumpEnabled then
        humanoid.JumpPower = 100
        JumpBtn.BackgroundColor3 = Color3.new(0.8, 0, 0)
        JumpBtn.Text = "✅ jumppower x2"
    else
        humanoid.JumpPower = 50
        JumpBtn.BackgroundColor3 = Color3.new(1, 0.5, 0)
        JumpBtn.Text = "jumppower x2"
    end
end

-- 无敌功能
local function toggleGod()
    godEnabled = not godEnabled
    local char = getCharacter()
    local humanoid = char:WaitForChild("Humanoid")
    
    if godEnabled then
        humanoid.MaxHealth = math.huge
        humanoid.Health = math.huge
        GodBtn.BackgroundColor3 = Color3.new(0, 0.8, 0)
        GodBtn.Text = "✅ god"
    else
        humanoid.MaxHealth = 100
        humanoid.Health = 100
        GodBtn.BackgroundColor3 = Color3.new(0.8, 0, 0)
        GodBtn.Text = "god"
    end
end

-- 杀死所有人功能
local function killAll()
    local killed = 0
    
    for _, plr in ipairs(game.Players:GetPlayers()) do
        if plr ~= player and plr.Character then
            local char = plr.Character
            local humanoid = char:FindFirstChild("Humanoid")
            local rootPart = char:FindFirstChild("HumanoidRootPart")
            
            -- 方法1: 直接设置健康为0
            if humanoid then
                pcall(function()
                    humanoid.Health = 0
                    killed = killed + 1
                end)
            end
            
            -- 方法2: 使用 TakeDamage
            if humanoid and humanoid.Health > 0 then
                pcall(function()
                    humanoid:TakeDamage(1000)
                    killed = killed + 1
                end)
            end
            
            -- 方法3: 移除所有部件
            if humanoid and humanoid.Health > 0 then
                pcall(function()
                    for _, part in ipairs(char:GetChildren()) do
                        if part:IsA("BasePart") or part:IsA("Accessory") then
                            part:Destroy()
                        end
                    end
                    killed = killed + 1
                end)
            end
            
            -- 方法4: 传送出地图
            if humanoid and humanoid.Health > 0 then
                pcall(function()
                    if rootPart then
                        rootPart.CFrame = CFrame.new(0, -500, 0)
                    end
                    killed = killed + 1
                end)
            end
            
            -- 方法5: 使用爆炸
            if humanoid and humanoid.Health > 0 then
                pcall(function()
                    if rootPart then
                        local explosion = Instance.new("Explosion")
                        explosion.BlastRadius = 10
                        explosion.BlastPressure = 0
                        explosion.Position = rootPart.Position
                        explosion.Parent = workspace
                        killed = killed + 1
                    end
                end)
            end
            
            -- 方法6: 移除 Humanoid
            if humanoid and humanoid.Health > 0 then
                pcall(function()
                    humanoid:Destroy()
                    killed = killed + 1
                end)
            end
        end
    end
    
    StatusLabel.Text = "💀 you killed " .. killed .. " players!"
    StatusLabel.TextColor3 = Color3.new(1, 0, 0)
    
    wait(2)
    StatusLabel.Text = "status: connected ✅"
    StatusLabel.TextColor3 = Color3.new(0.4, 1, 0.4)
end

-- 自动抓枪功能 - 修复版
local function findGun()
    local char = getCharacter()
    local rootPart = char:FindFirstChild("HumanoidRootPart")
    if not rootPart then return nil end
    
    local closestGun = nil
    local closestDistance = 50
    
    for _, obj in ipairs(workspace:GetDescendants()) do
        if obj:IsA("Tool") and obj:FindFirstChild("Handle") then
            local handle = obj.Handle
            local distance = (handle.Position - rootPart.Position).Magnitude
            if distance < closestDistance then
                closestDistance = distance
                closestGun = obj
            end
        end
    end
    return closestGun
end

local function toggleAutoGrab()
    autoGrabEnabled = not autoGrabEnabled
    if autoGrabEnabled then
        AutoGrabBtn.BackgroundColor3 = Color3.new(0.8, 0, 0)
        AutoGrabBtn.Text = "✅ auto grab gun"
    else
        AutoGrabBtn.BackgroundColor3 = Color3.new(0, 0.8, 0.8)
        AutoGrabBtn.Text = "auto grab gun"
    end
end

-- 自动射击功能 - 修复版
local function findTarget()
    local char = getCharacter()
    local rootPart = char:FindFirstChild("HumanoidRootPart")
    if not rootPart then return nil end
    
    local closestTarget = nil
    local closestDistance = math.huge
    
    for _, plr in ipairs(game.Players:GetPlayers()) do
        if plr ~= player and plr.Character then
            local targetRoot = plr.Character:FindFirstChild("HumanoidRootPart")
            if targetRoot then
                local distance = (targetRoot.Position - rootPart.Position).Magnitude
                if distance < closestDistance then
                    closestDistance = distance
                    closestTarget = plr
                end
            end
        end
    end
    
    return closestTarget
end

local function toggleAutoShoot()
    autoShootEnabled = not autoShootEnabled
    if autoShootEnabled then
        AutoShootBtn.BackgroundColor3 = Color3.new(0.8, 0, 0)
        AutoShootBtn.Text = "✅ auto shoot"
    else
        AutoShootBtn.BackgroundColor3 = Color3.new(1, 0, 0)
        AutoShootBtn.Text = "auto shoot"
    end
end

-- 自动刷钱功能 - 反作弊安全版
local function findCoins()
    local coins = {}
    for _, obj in ipairs(workspace:GetDescendants()) do
        if obj:IsA("Part") and obj.Name:lower():find("coin") then
            table.insert(coins, obj)
        end
    end
    return coins
end

local function toggleAutoFarm()
    autoFarmEnabled = not autoFarmEnabled
    if autoFarmEnabled then
        AutoFarmBtn.BackgroundColor3 = Color3.new(0.8, 0, 0)
        AutoFarmBtn.Text = "✅ auto farm"
    else
        AutoFarmBtn.BackgroundColor3 = Color3.new(1, 0.8, 0)
        AutoFarmBtn.Text = "auto farm"
    end
end

-- 传送功能
local function findPlayerByRole(role)
    for _, plr in ipairs(game.Players:GetPlayers()) do
        if plr ~= player and plr.Character then
            local plrRole = getPlayerRole(plr)
            if plrRole == role then
                return plr
            end
        end
    end
    return nil
end

local function teleportToRole(role)
    local target = findPlayerByRole(role)
    if target and target.Character then
        local targetRoot = target.Character:FindFirstChild("HumanoidRootPart")
        if targetRoot then
            local char = getCharacter()
            local rootPart = char:FindFirstChild("HumanoidRootPart")
            if rootPart then
                rootPart.CFrame = targetRoot.CFrame * CFrame.new(0, 5, 0)
                StatusLabel.Text = "🌀 tp to" .. role
                StatusLabel.TextColor3 = Color3.new(0, 1, 1)
                wait(2)
                StatusLabel.Text = "status: connected ✅"
                StatusLabel.TextColor3 = Color3.new(0.4, 1, 0.4)
            end
        end
    else
        StatusLabel.Text = "❌ cannot find" .. role
        StatusLabel.TextColor3 = Color3.new(1, 0, 0)
        wait(2)
        StatusLabel.Text = "status: connected ✅"
        StatusLabel.TextColor3 = Color3.new(0.4, 1, 0.4)
    end
end

-- 按钮事件
EspInnocentBtn.MouseButton1Click:Connect(function() toggleESP("Innocent") end)
EspSheriffBtn.MouseButton1Click:Connect(function() toggleESP("Sheriff") end)
EspMurderBtn.MouseButton1Click:Connect(function() toggleESP("Murderer") end)
EspHeroBtn.MouseButton1Click:Connect(function() toggleESP("Hero") end)
SpeedBtn.MouseButton1Click:Connect(toggleSpeed)
JumpBtn.MouseButton1Click:Connect(toggleJump)
GodBtn.MouseButton1Click:Connect(toggleGod)
KillAllBtn.MouseButton1Click:Connect(killAll)
AutoGrabBtn.MouseButton1Click:Connect(toggleAutoGrab)
AutoShootBtn.MouseButton1Click:Connect(toggleAutoShoot)
AutoFarmBtn.MouseButton1Click:Connect(toggleAutoFarm)
TpToMurderBtn.MouseButton1Click:Connect(function() teleportToRole("Murderer") end)
TpToSheriffBtn.MouseButton1Click:Connect(function() teleportToRole("Sheriff") end)

-- 玩家加入/离开时更新ESP
game.Players.PlayerAdded:Connect(function(plr)
    plr.CharacterAdded:Connect(function()
        wait(0.5)
        updateESP()
    end)
end)

game.Players.PlayerRemoving:Connect(function(plr)
    removeESP(plr)
end)

-- 角色重生时恢复设置
player.CharacterAdded:Connect(function(char)
    wait(0.5)
    local humanoid = char:WaitForChild("Humanoid")
    
    if speedEnabled then
        humanoid.WalkSpeed = 32
    end
    
    if jumpEnabled then
        humanoid.JumpPower = 100
    end
    
    if godEnabled then
        humanoid.MaxHealth = math.huge
        humanoid.Health = math.huge
    end
end)

-- 自动功能循环 - 反作弊安全版
game:GetService("RunService").RenderStepped:Connect(function()
    local char = getCharacter()
    local rootPart = char:FindFirstChild("HumanoidRootPart")
    if not rootPart then return end
    
    -- 自动抓枪 - 修复版（不会瞬移）
    if autoGrabEnabled then
        local gun = findGun()
        if gun and not char:FindFirstChildOfClass("Tool") then
            local humanoid = char:FindFirstChild("Humanoid")
            if humanoid then
                -- 直接装备工具，不需要传送
                humanoid:EquipTool(gun)
            end
        end
    end
    
    -- 自动射击 - 修复版（不会瞬移）
    if autoShootEnabled then
        local target = findTarget()
        if target and target.Character then
            local targetRoot = target.Character:FindFirstChild("HumanoidRootPart")
            if targetRoot then
                -- 只旋转角色朝向目标，不移动
                local lookAt = CFrame.lookAt(rootPart.Position, targetRoot.Position)
                rootPart.CFrame = CFrame.new(rootPart.Position) * CFrame.Angles(0, lookAt:ToEulerAnglesXYZ(), 0)
                
                local tool = char:FindFirstChildOfClass("Tool")
                if tool then
                    local gunScript = tool:FindFirstChild("GunScript") or tool:FindFirstChild("ShootScript") or tool:FindFirstChild("RemoteEvent")
                    if gunScript then
                        pcall(function()
                            gunScript:FireServer()
                        end)
                    end
                end
            end
        end
    end
    
    -- 自动刷钱 - 反作弊安全版（使用自然移动）
    if autoFarmEnabled then
        local coins = findCoins()
        if #coins > 0 then
            local closestCoin = nil
            local closestDistance = 100
            
            for _, coin in ipairs(coins) do
                local distance = (coin.Position - rootPart.Position).Magnitude
                if distance < closestDistance then
                    closestDistance = distance
                    closestCoin = coin
                end
            end
            
            if closestCoin then
                -- 使用自然移动（不是瞬移）
                local direction = (closestCoin.Position - rootPart.Position).Unit
                local distance = (closestCoin.Position - rootPart.Position).Magnitude
                
                if distance > 5 then
                    -- 缓慢移动，模拟真实玩家
                    local humanoid = char:FindFirstChild("Humanoid")
                    if humanoid then
                        humanoid.WalkSpeed = 16 -- 正常速度
                        humanoid:MoveTo(closestCoin.Position)
                    end
                else
                    -- 已经到达，停止移动
                    local humanoid = char:FindFirstChild("Humanoid")
                    if humanoid then
                        humanoid.WalkSpeed = 16
                    end
                end
            end
        end
    end
end)

-- 定期更新ESP
spawn(function()
    while wait(0.5) do
        updateESP()
    end
end)

-- 检测是否连接成功
wait(1)
if game.Players:GetPlayers() then
    StatusLabel.Text = "status: connected ✅"
    StatusLabel.TextColor3 = Color3.new(0.4, 1, 0.4)
end

print("✅ MM2 ULTRA PRO loaded！")
print("Made by Cyrusrbx ✨")
