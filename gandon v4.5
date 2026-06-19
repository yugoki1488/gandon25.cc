-- gandon_v4.5 — Added Fly & Anti-Ragdoll (Based on v4.4)
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")

local lp = Players.LocalPlayer
local camera = workspace.CurrentCamera
local mouse = lp:GetMouse()

-- Цветовая палитра
local MainPurple = Color3.fromRGB(157, 100, 255)   
local BGColor = Color3.fromRGB(24, 22, 28)         
local BtnOffColor = Color3.fromRGB(40, 38, 45)     
local TextOffColor = Color3.fromRGB(255, 120, 120) 

-- Состояния функций
local flingEnabled = false
local noclipEnabled = false
local espEnabled = false
local infJumpEnabled = false
local speedEnabled = false
local speedValue = 16
local tpToolEnabled = false
local aimbotEnabled = false
local chamsEnabled = false
local flyEnabled = false
local flySpeed = 50
local antiRagdollEnabled = false

local flingConnection, noclipConnection, aimbotConnection, flyConnection, ragdollConnection
local espObjects = {}
local tpTool = nil

-- Функция для быстрого создания анимаций
local function uiTween(obj, duration, props)
    local tweenInfo = TweenInfo.new(duration, Enum.EasingStyle.Quart, Enum.EasingDirection.Out)
    TweenService:Create(obj, tweenInfo, props):Play()
end

-- ====================== GUI (gandon_v4.5) ======================
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "gandon_v4"
ScreenGui.ResetOnSpawn = false
ScreenGui.Parent = lp:WaitForChild("PlayerGui")

-- Главный контейнер (МАКСИМАЛЬНО ВВЕРХ — Y: 0.01)
local MainFrame = Instance.new("Frame")
MainFrame.Size = UDim2.new(0, 230, 0, 320)
MainFrame.Position = UDim2.new(0.4, 0, 0.01, 0) -- Вплотную к верхнему краю экрана
MainFrame.BackgroundColor3 = BGColor
MainFrame.BorderSizePixel = 0
MainFrame.Active = true
MainFrame.Draggable = true
MainFrame.Visible = true 
MainFrame.Parent = ScreenGui

Instance.new("UICorner", MainFrame).CornerRadius = UDim.new(0, 14)

local Title = Instance.new("TextLabel")
Title.Size = UDim2.new(1, 0, 0, 40)
Title.BackgroundColor3 = MainPurple
Title.Text = "gandon_v4.5"
Title.TextColor3 = Color3.new(1,1,1)
Title.Font = Enum.Font.GothamBold
Title.TextSize = 18
Title.Parent = MainFrame
Instance.new("UICorner", Title).CornerRadius = UDim.new(0, 14)

-- Скролл-зона для кнопок (Увеличили CanvasSize до 580)
local ScrollPage = Instance.new("ScrollingFrame")
ScrollPage.Size = UDim2.new(1, 0, 1, -45)
ScrollPage.Position = UDim2.new(0, 0, 0, 42)
ScrollPage.BackgroundTransparency = 1
ScrollPage.BorderSizePixel = 0
ScrollPage.CanvasSize = UDim2.new(0, 0, 0, 580) 
ScrollPage.ScrollBarThickness = 3
ScrollPage.ScrollBarImageColor3 = MainPurple
ScrollPage.Parent = MainFrame

local function createBtn(text, y)
    local btn = Instance.new("TextButton")
    btn.Size = UDim2.new(0.85, 0, 0, 38) 
    btn.Position = UDim2.new(0.075, 0, 0, y)
    btn.BackgroundColor3 = BtnOffColor
    btn.Text = text .. ": OFF"
    btn.TextColor3 = TextOffColor
    btn.Font = Enum.Font.GothamSemibold
    btn.TextSize = 14
    btn.Parent = ScrollPage
    Instance.new("UICorner", btn).CornerRadius = UDim.new(0, 8)
    return btn
end

-- Кнопки внутри скролла
local FlingBtn       = createBtn("Touch Fling", 10)
local NoclipBtn      = createBtn("Noclip", 55)
local EspBtn         = createBtn("ESP Box", 100)
local ChamsBtn       = createBtn("Chams (Wallhack)", 145)
local SpeedBtn       = createBtn("Speedhack", 190)

-- ПОЛЗУНОК СКОРОСТИ
local SliderFrame = Instance.new("Frame")
SliderFrame.Size = UDim2.new(0.85, 0, 0, 20)
SliderFrame.Position = UDim2.new(0.075, 0, 0, 233)
SliderFrame.BackgroundColor3 = Color3.fromRGB(30, 28, 35)
SliderFrame.Parent = ScrollPage
Instance.new("UICorner", SliderFrame).CornerRadius = UDim.new(0, 6)

local SliderFill = Instance.new("Frame")
SliderFill.Size = UDim2.new(0.16, 0, 1, 0) 
SliderFill.BackgroundColor3 = MainPurple
SliderFill.Parent = SliderFrame
Instance.new("UICorner", SliderFill).CornerRadius = UDim.new(0, 6)

local SliderText = Instance.new("TextLabel")
SliderText.Size = UDim2.new(1, 0, 1, 0)
SliderText.BackgroundTransparency = 1
SliderText.Text = "Speed: 16"
SliderText.TextColor3 = Color3.new(1,1,1)
SliderText.Font = Enum.Font.GothamBold
SliderText.TextSize = 11
SliderText.Parent = SliderFrame

local TpBtn          = createBtn("Click TP Tool", 265)
local AimbotBtn      = createBtn("Aimbot Mobile", 310)
local FlyBtn         = createBtn("Fly (Полет)", 355)
local AntiRagdollBtn = createBtn("Anti-Ragdoll", 400)
local InfJumpBtn     = createBtn("Inf Jump", 445)

-- Сворачивание
local MinimizeBtn = Instance.new("TextButton")
MinimizeBtn.Size = UDim2.new(0, 30, 0, 30)
MinimizeBtn.Position = UDim2.new(1, -35, 0, 5)
MinimizeBtn.BackgroundColor3 = MainPurple
MinimizeBtn.Text = "−"
MinimizeBtn.TextColor3 = Color3.new(1,1,1)
MinimizeBtn.Font = Enum.Font.GothamBold
MinimizeBtn.TextSize = 18
MinimizeBtn.Parent = MainFrame
Instance.new("UICorner", MinimizeBtn).CornerRadius = UDim.new(1,0)

-- КРУГЛЯШОК ДЛЯ ВЫЗОВА МЕНЮ (Y: 0.23)
local CircleBtn = Instance.new("TextButton")
CircleBtn.Size = UDim2.new(0, 55, 0, 55) 
CircleBtn.Position = UDim2.new(0, 30, 0.23, 0) 
CircleBtn.BackgroundColor3 = MainPurple
CircleBtn.Text = "G"
CircleBtn.TextColor3 = Color3.new(1,1,1)
CircleBtn.Font = Enum.Font.GothamBold
CircleBtn.TextSize = 24
CircleBtn.Visible = false 
CircleBtn.Draggable = true
CircleBtn.Parent = ScreenGui
Instance.new("UICorner", CircleBtn).CornerRadius = UDim.new(1,0)

-- КНОПКА AIMБOТA (ПРАВЫЙ ВЕРХНИЙ УГОЛ)
local MobileAimBtn = Instance.new("TextButton")
MobileAimBtn.Size = UDim2.new(0, 85, 0, 85) 
MobileAimBtn.Position = UDim2.new(0.8, -40, 0.2, 0) 
MobileAimBtn.BackgroundColor3 = MainPurple
MobileAimBtn.Text = "AIM"
MobileAimBtn.TextColor3 = Color3.new(1,1,1)
MobileAimBtn.Font = Enum.Font.GothamBold
MobileAimBtn.TextSize = 20
MobileAimBtn.Visible = false 
MobileAimBtn.Draggable = true
MobileAimBtn.Parent = ScreenGui
Instance.new("UICorner", MobileAimBtn).CornerRadius = UDim.new(1,0)

-- Анимация разворота меню
local isAnimating = false
local function openMenu()
    if isAnimating then return end
    isAnimating = true
    uiTween(CircleBtn, 0.2, {Size = UDim2.new(0, 0, 0, 0)})
    task.wait(0.2)
    CircleBtn.Visible = false
    MainFrame.Visible = true
    uiTween(MainFrame, 0.3, {Size = UDim2.new(0, 230, 0, 320)})
    task.wait(0.3)
    isAnimating = false
end

local function closeMenu()
    if isAnimating then return end
    isAnimating = true
    uiTween(MainFrame, 0.3, {Size = UDim2.new(0, 230, 0, 0)})
    task.wait(0.3)
    MainFrame.Visible = false
    CircleBtn.Visible = true
    uiTween(CircleBtn, 0.3, {Size = UDim2.new(0, 55, 0, 55)})
    task.wait(0.3)
    isAnimating = false
end

MinimizeBtn.MouseButton1Click:Connect(closeMenu)
CircleBtn.MouseButton1Click:Connect(openMenu)

local function toggleBtnStyle(btn, state, text)
    if state then
        uiTween(btn, 0.3, {BackgroundColor3 = Color3.fromRGB(60, 40, 90)})
        btn.TextColor3 = Color3.fromRGB(200, 160, 255) 
        btn.Text = text .. ": ON"
    else
        uiTween(btn, 0.3, {BackgroundColor3 = BtnOffColor})
        btn.TextColor3 = TextOffColor
        btn.Text = text .. ": OFF"
    end
end

-- Логика ползунка (Slider)
local isSliding = false
local function updateSlider(input)
    local mousePos = input.Position.X
    local sliderPos = SliderFrame.AbsolutePosition.X
    local sliderWidth = SliderFrame.AbsoluteSize.X
    local percentage = math.clamp((mousePos - sliderPos) / sliderWidth, 0, 1)
    
    SliderFill.Size = UDim2.new(percentage, 0, 1, 0)
    speedValue = math.round(percentage * 100)
    SliderText.Text = "Speed: " .. tostring(speedValue)
    
    if speedEnabled then
        local char = lp.Character
        local hum = char and char:FindFirstChildOfClass("Humanoid")
        if hum then hum.WalkSpeed = speedValue end
    end
end

SliderFrame.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
        isSliding = true
        updateSlider(input)
    end
end)

UserInputService.InputChanged:Connect(function(input)
    if isSliding and (input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch) then
        updateSlider(input)
    end
end)

UserInputService.InputEnded:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
        isSliding = false
    end
end)

-- ====================== ФУНКЦИОНАЛ ======================

-- FLY (ПОЛЕТ)
local function startFly()
    if flyConnection then flyConnection:Disconnect() end
    local char = lp.Character
    local hrp = char and (char:FindFirstChild("HumanoidRootPart") or char:FindFirstChild("Torso"))
    if not hrp then return end
    
    local bv = Instance.new("BodyVelocity")
    bv.Velocity = Vector3.new(0, 0, 0)
    bv.MaxForce = Vector3.new(9e9, 9e9, 9e9)
    bv.Parent = hrp

    flyConnection = RunService.RenderStepped:Connect(function()
        if not flyEnabled or not hrp or not hrp.Parent then 
            bv:Destroy() 
            if flyConnection then flyConnection:Disconnect() end 
            return 
        end
        local dir = Vector3.new(0, 0, 0)
        local hum = lp.Character:FindFirstChildOfClass("Humanoid")
        if hum and hum.MoveDirection.Magnitude > 0 then 
            dir = hum.MoveDirection * flySpeed 
        end
        bv.Velocity = dir
    end)
end

-- ANTI-RAGDOLL
local function startAntiRagdoll()
    if ragdollConnection then ragdollConnection:Disconnect() end
    ragdollConnection = RunService.Stepped:Connect(function()
        if not antiRagdollEnabled then return end
        local char = lp.Character
        local hum = char and char:FindFirstChildOfClass("Humanoid")
        if hum then
            hum:SetStateEnabled(Enum.HumanoidStateType.Ragdoll, false)
            hum:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
            if hum:GetState() == Enum.HumanoidStateType.Ragdoll or hum:GetState() == Enum.HumanoidStateType.FallingDown then
                hum:ChangeState(Enum.HumanoidStateType.GettingUp)
            end
        end
    end)
end

-- TOUCH FLING
local function startFling()
    if flingConnection then flingConnection:Disconnect() end
    flingConnection = RunService.Heartbeat:Connect(function()
        if not flingEnabled then return end
        local char = lp.Character
        local hrp = char and char:FindFirstChild("HumanoidRootPart")
        if hrp then
            local vel = hrp.Velocity
            hrp.Velocity = vel * 10000 + Vector3.new(0, 10000, 0)
            RunService.RenderStepped:Wait()
            if hrp and hrp.Parent then hrp.Velocity = vel end
            RunService.Stepped:Wait()
            if hrp and hrp.Parent then hrp.Velocity = vel + Vector3.new(0, 0.1, 0) end
        end
    end)
end

-- NOCLIP
local function startNoclip()
    if noclipConnection then noclipConnection:Disconnect() end
    noclipConnection = RunService.Stepped:Connect(function()
        if not noclipEnabled then return end
        local char = lp.Character
        if char then
            for _, part in pairs(char:GetDescendants()) do
                if part:IsA("BasePart") then part.CanCollide = false end
            end
        end
    end)
end

-- БЕЗОПАСНЫЙ ИНФ ДЖАМП
UserInputService.JumpRequest:Connect(function()
    if infJumpEnabled then
        local char = lp.Character
        local hum = char and char:FindFirstChildOfClass("Humanoid")
        if hum then hum:ChangeState(Enum.HumanoidStateType.Jumping) end
    end
end)

-- CLICK TP TOOL
local function updateTPTool()
    if tpToolEnabled then
        if not tpTool or tpTool.Parent ~= lp.Backpack then
            tpTool = Instance.new("Tool")
            tpTool.Name = "🔥 TP Tool"
            tpTool.RequiresHandle = false
            tpTool.Activated:Connect(function()
                local char = lp.Character
                local hrp = char and char:FindFirstChild("HumanoidRootPart")
                if hrp and mouse.Hit then
                    hrp.CFrame = CFrame.new(mouse.Hit.Position + Vector3.new(0, 3, 0))
                end
            end)
            tpTool.Parent = lp.Backpack
        end
    else
        if tpTool then tpTool:Destroy() tpTool = nil end
    end
end

-- AIMBOT ЛОГИКА
local function getClosestPlayer()
    local closestPlayer = nil
    local shortestDistance = math.huge
    for _, player in pairs(Players:GetPlayers()) do
        if player ~= lp and player.Character and player.Character:FindFirstChild("Head") then
            local head = player.Character.Head
            local pos, onScreen = camera:WorldToViewportPoint(head.Position)
            if onScreen then
                local mousePos = Vector2.new(mouse.X, mouse.Y)
                local playerPos = Vector2.new(pos.X, pos.Y)
                local distance = (mousePos - playerPos).Magnitude
                if distance < shortestDistance then
                    closestPlayer = player
                    shortestDistance = distance
                end
            end
        end
    end
    return closestPlayer
end

local isAiming = false
MobileAimBtn.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then isAiming = true end
end)
MobileAimBtn.InputEnded:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then isAiming = false end
end)
UserInputService.InputBegan:Connect(function(input, processed)
    if processed then return end
    if aimbotEnabled and input.KeyCode == Enum.KeyCode.E then isAiming = true end
end)
UserInputService.InputEnded:Connect(function(input)
    if input.KeyCode == Enum.KeyCode.E then isAiming = false end
end)

aimbotConnection = RunService.RenderStepped:Connect(function()
    if aimbotEnabled and isAiming then
        local target = getClosestPlayer()
        if target and target.Character and target.Character:FindFirstChild("Head") then
            camera.CFrame = CFrame.new(camera.CFrame.Position, target.Character.Head.Position)
        end
    end
end)

-- ФУНКЦИЯ БЕЗОПАСНОГО УДАЛЕНИЯ ЭЛЕМЕНТОВ ESP ДЛЯ КОНКРЕТНОГО ИГРОКА
local function removeSingleESP(player)
    if espObjects[player] then
        pcall(function()
            if espObjects[player].Box then espObjects[player].Box:Remove() end
            if espObjects[player].Name then espObjects[player].Name:Remove() end
        end)
        espObjects[player] = nil
    end
end

-- ПОЛНАЯ ОЧИСТКА ВСЕГО ESP
local function removeAllESP()
    for player, _ in pairs(espObjects) do
        removeSingleESP(player)
    end
end

-- УЛУЧШЕННЫЕ CHAMS (РАБОТАЮТ НА ВСЕХ ПЛЕЙСАХ)
local function updateChams()
    for _, player in pairs(Players:GetPlayers()) do
        if player == lp then continue end
        local char = player.Character
        if char and char:IsDescendantOf(workspace) then
            local hl = char:FindFirstChild("GComboChams")
            if chamsEnabled then
                if not hl then
                    hl = Instance.new("Highlight")
                    hl.Name = "GComboChams"
                    hl.FillColor = MainPurple
                    hl.FillTransparency = 0.4 
                    hl.OutlineColor = Color3.new(1,1,1)
                    hl.OutlineTransparency = 0
                    hl.DepthMode = Enum.HighlightDepthMode.AlwaysOnTop 
                    hl.Adornee = char
                    hl.Parent = char
                end
            else
                if hl then hl:Destroy() end
            end
        end
    end
end

-- ИСПРАВЛЕННАЯ СИСТЕМА ESP И УДАЛЕНИЯ ПРИЗРАКОВ
RunService.RenderStepped:Connect(function()
    updateChams()
    
    -- Очистка "призраков", если игрок ливнул из игры
    for player, _ in pairs(espObjects) do
        if not Players:FindFirstChild(player.Name) then
            removeSingleESP(player)
        end
    end

    if not espEnabled then removeAllESP() return end

    for _, player in pairs(Players:GetPlayers()) do
        if player == lp then continue end
        
        local char = player.Character
        -- Если игрок мертв или ресетнулся, убираем его зависший бокс
        if not char or not char:IsDescendantOf(workspace) or not char:FindFirstChild("Humanoid") or char.Humanoid.Health <= 0 then
            removeSingleESP(player)
            continue
        end

        local root = char:FindFirstChild("HumanoidRootPart") or char:FindFirstChild("Torso") or char:FindFirstChild("UpperTorso")
        if not root then continue end

        local rootPos, onScreen = camera:WorldToViewportPoint(root.Position)
        
        -- Если игрок за спиной, скрываем бокс (чтобы не зависал в центре)
        if not onScreen or rootPos.Z < 0 then 
            if espObjects[player] then
                if espObjects[player].Box then espObjects[player].Box.Visible = false end
                if espObjects[player].Name then espObjects[player].Name.Visible = false end
            end
            continue 
        end

        -- Создаем бокс, если его еще нет
        if not espObjects[player] then
            espObjects[player] = {}
            local box = Drawing.new("Square")
            box.Thickness = 1.4
            box.Color = MainPurple
            box.Filled = false
            espObjects[player].Box = box

            local name = Drawing.new("Text")
            name.Text = player.Name
            name.Color = Color3.fromRGB(255, 255, 255)
            name.Size = 13
            name.Center = true
            name.Outline = true
            espObjects[player].Name = name
        end

        local obj = espObjects[player]
        local head = char:FindFirstChild("Head") or root
        local headPos = camera:WorldToViewportPoint(head.Position + Vector3.new(0, 1.6, 0))   
        local feetPos = camera:WorldToViewportPoint(root.Position - Vector3.new(0, 3.6, 0))  

        local height = math.abs(headPos.Y - feetPos.Y)
        local width = height * 0.6

        if obj.Box then
            obj.Box.Size = Vector2.new(width, height)
            obj.Box.Position = Vector2.new(headPos.X - width/2, headPos.Y)
            obj.Box.Visible = true
        end

        if obj.Name then
            obj.Name.Position = Vector2.new(headPos.X, headPos.Y - 15)
            obj.Name.Visible = true
        end
    end
end)

-- Очистка при выходе игрока (дополнительная страховка)
Players.PlayerRemoving:Connect(function(player)
    removeSingleESP(player)
end)

lp.CharacterAdded:Connect(function(char)
    if speedEnabled then
        local hum = char:WaitForChild("Humanoid", 5)
        if hum then hum.WalkSpeed = speedValue end
    end
    if antiRagdollEnabled then
        startAntiRagdoll()
    end
end)

-- ====================== НАЖАТИЯ КНОПОК ======================
FlingBtn.MouseButton1Click:Connect(function()
    flingEnabled = not flingEnabled
    toggleBtnStyle(FlingBtn, flingEnabled, "Touch Fling")
    if flingEnabled then startFling() else if flingConnection then flingConnection:Disconnect() end end
end)

NoclipBtn.MouseButton1Click:Connect(function()
    noclipEnabled = not noclipEnabled
    toggleBtnStyle(NoclipBtn, noclipEnabled, "Noclip")
    if noclipEnabled then startNoclip() else if noclipConnection then noclipConnection:Disconnect() end end
end)

EspBtn.MouseButton1Click:Connect(function()
    espEnabled = not espEnabled
    toggleBtnStyle(EspBtn, espEnabled, "ESP Box")
    if not espEnabled then removeAllESP() end
end)

ChamsBtn.MouseButton1Click:Connect(function()
    chamsEnabled = not chamsEnabled
    toggleBtnStyle(ChamsBtn, chamsEnabled, "Chams (Wallhack)")
    if not chamsEnabled then
        for _, player in pairs(Players:GetPlayers()) do
            if player.Character then
                local hl = player.Character:FindFirstChild("GComboChams"
