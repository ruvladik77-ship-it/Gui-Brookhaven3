local Players = game:GetService("Players")
local player = Players.LocalPlayer
local mouse = player:GetMouse()

-- Создание интерфейса
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "BrookhavenGUI"
ScreenGui.Parent = game.CoreGui

local MainFrame = Instance.new("Frame")
MainFrame.Size = UDim2.new(0, 200, 0, 330)  -- Увеличили высоту для восьмой кнопки
MainFrame.Position = UDim2.new(0.5, -100, 0.5, -165)
MainFrame.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
MainFrame.BorderSizePixel = 0
MainFrame.Parent = ScreenGui

local Title = Instance.new("TextLabel")
Title.Size = UDim2.new(1, 0, 0, 30)
Title.Position = UDim2.new(0, 0, 0, 0)
Title.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.Text = "Brookhaven GUI"
Title.Font = Enum.Font.GothamBold
Title.Parent = MainFrame

-- Кнопка закрытия
local CloseButton = Instance.new("TextButton")
CloseButton.Size = UDim2.new(0, 25, 0, 25)
CloseButton.Position = UDim2.new(1, -25, 0, 0)
CloseButton.BackgroundColor3 = Color3.fromRGB(200, 50, 50)
CloseButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CloseButton.Text = "X"
CloseButton.Font = Enum.Font.GothamBold
CloseButton.Parent = Title

CloseButton.MouseButton1Click:Connect(function()
    ScreenGui:Destroy()
end)

-- Первая кнопка
local Button1 = Instance.new("TextButton")
Button1.Size = UDim2.new(0.9, 0, 0, 30)
Button1.Position = UDim2.new(0.05, 0, 0.11, 0)
Button1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
Button1.TextColor3 = Color3.fromRGB(255, 255, 255)
Button1.Text = "Смена тела 1"
Button1.Font = Enum.Font.Gotham
Button1.Parent = MainFrame

Button1.MouseButton1Click:Connect(function()
    local __V0C0N_1 = game:GetService("ReplicatedStorage")
    local __V0C0N_2 = {81881085814072,79115019295211,106740492797177,81153927159685,88668275797583,115379341593655}
    local __V0C0N_3 = __V0C0N_1.Remotes
    local __V0C0N_4 = "ChangeCharacterBody"
    __V0C0N_3[__V0C0N_4]:InvokeServer(__V0C0N_2)
end)

-- Вторая кнопка
local Button2 = Instance.new("TextButton")
Button2.Size = UDim2.new(0.9, 0, 0, 30)
Button2.Position = UDim2.new(0.05, 0, 0.22, 0)
Button2.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
Button2.TextColor3 = Color3.fromRGB(255, 255, 255)
Button2.Text = "Смена тела 2"
Button2.Font = Enum.Font.Gotham
Button2.Parent = MainFrame

Button2.MouseButton1Click:Connect(function()
    local function WEAR(id)
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Wear"):InvokeServer(id)
    end

    local cooldown = false

    local function AvatarChanges(torso, rarm, larm, rleg, lleg, head)
        if cooldown then
            return
        end

        cooldown = true

        pcall(function()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("ChangeCharacterBody"):InvokeServer({torso, rarm, larm, rleg, lleg, head})
        end)

        task.delay(1, function()
            cooldown = false
        end)
    end

    AvatarChanges(
        77511372110162,     -- Torso
        136003410970495,    -- Right Arm
        122289109987160,    -- Left Arm
        105216940798112,    -- Right Leg
        110431485579564,    -- Left Leg
        0                 
    )

    task.wait(1)
    WEAR(118654804220494)
    wait(1)
    WEAR(88432101086369)
end)

-- Третья кнопка
local Button3 = Instance.new("TextButton")
Button3.Size = UDim2.new(0.9, 0, 0, 30)
Button3.Position = UDim2.new(0.05, 0, 0.33, 0)
Button3.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
Button3.TextColor3 = Color3.fromRGB(255, 255, 255)
Button3.Text = "Аудио скрипт"
Button3.Font = Enum.Font.Gotham
Button3.Parent = MainFrame

Button3.MouseButton1Click:Connect(function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/nmalka01/nmalka01/refs/heads/main/Brookhaven_audio"))()
end)

-- Четвертая кнопка
local Button4 = Instance.new("TextButton")
Button4.Size = UDim2.new(0.9, 0, 0, 30)
Button4.Position = UDim2.new(0.05, 0, 0.44, 0)
Button4.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
Button4.TextColor3 = Color3.fromRGB(255, 255, 255)
Button4.Text = "SP Hub"
Button4.Font = Enum.Font.Gotham
Button4.Parent = MainFrame

Button4.MouseButton1Click:Connect(function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/as6cd0/SP_Hub/refs/heads/main/Brookhaven"))()
end)

-- Пятая кнопка (r6)
local Button5 = Instance.new("TextButton")
Button5.Size = UDim2.new(0.9, 0, 0, 30)
Button5.Position = UDim2.new(0.05, 0, 0.55, 0)
Button5.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
Button5.TextColor3 = Color3.fromRGB(255, 255, 255)
Button5.Text = "R6 Тело"
Button5.Font = Enum.Font.Gotham
Button5.Parent = MainFrame

Button5.MouseButton1Click:Connect(function()
    local function WEAR(id)
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Wear"):InvokeServer(id)
    end

    local cooldown = false

    local function AvatarChanges(torso, rarm, larm, rleg, lleg, head)
        if cooldown then
            return
        end

        cooldown = true

        pcall(function()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("ChangeCharacterBody"):InvokeServer({torso, rarm, larm, rleg, lleg, head})
        end)

        task.delay(1, function()
            cooldown = false
        end)
    end

    AvatarChanges(
        93957172573915,     -- Torso
        98264324846024,    -- Right Arm
        138497770019687,    -- Left Arm
        126460010436708,    -- Right Leg
        75728348199721,    -- Left Leg
        0                 
    )

    task.wait(1)
    WEAR(118654804220494)
    wait(1)
    WEAR(88432101086369)
end)

-- Шестая кнопка (R15 эмоции)
local Button6 = Instance.new("TextButton")
Button6.Size = UDim2.new(0.9, 0, 0, 30)
Button6.Position = UDim2.new(0.05, 0, 0.66, 0)
Button6.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
Button6.TextColor3 = Color3.fromRGB(255, 255, 255)
Button6.Text = "R15 эмоции"
Button6.Font = Enum.Font.Gotham
Button6.Parent = MainFrame

Button6.MouseButton1Click:Connect(function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Gazer-Ha/Gaze-stuff/refs/heads/main/Silly%20emote"))()
end)

-- Седьмая кнопка (Габби)
local Button7 = Instance.new("TextButton")
Button7.Size = UDim2.new(0.9, 0, 0, 30)
Button7.Position = UDim2.new(0.05, 0, 0.77, 0)
Button7.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
Button7.TextColor3 = Color3.fromRGB(255, 255, 255)
Button7.Text = "Габби"
Button7.Font = Enum.Font.Gotham
Button7.Parent = MainFrame

Button7.MouseButton1Click:Connect(function()
    local function WEAR(id)
        game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Wear"):InvokeServer(id)
    end

    local cooldown = false

    local function AvatarChanges(torso, rarm, larm, rleg, lleg, head)
        if cooldown then
            return
        end

        cooldown = true

        pcall(function()
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("ChangeCharacterBody"):InvokeServer({torso, rarm, larm, rleg, lleg, head})
        end)

        task.delay(1, function()
            cooldown = false
        end)
    end

    AvatarChanges(
        77511372110162,     -- Torso
        136003410970495,    -- Right Arm
        122289109987160,    -- Left Arm
        105216940798112,    -- Right Leg
        110431485579564,    -- Left Leg
        0                 
    )

    task.wait(1)
    WEAR(118654804220494)
    wait(1)
    WEAR(88432101086369)
end)

-- Восьмая кнопка (Конец)
local Button8 = Instance.new("TextButton")
Button8.Size = UDim2.new(0.9, 0, 0, 30)
Button8.Position = UDim2.new(0.05, 0, 0.88, 0)
Button8.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
Button8.TextColor3 = Color3.fromRGB(255, 255, 255)
Button8.Text = "Конец"
Button8.Font = Enum.Font.Gotham
Button8.Parent = MainFrame

Button8.MouseButton1Click:Connect(function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/v0c0n1337/scripts/refs/heads/main/snooby12345678v0c0n1337buadamlarbizisker.lua"))()
end)

-- Перетаскивание окна
local dragToggle = nil
local dragSpeed = 0.25
local dragStart = nil
local startPos = nil

local function updateInput(input)
    local delta = input.Position - dragStart
    local position = UDim2.new(
        startPos.X.Scale, 
        startPos.X.Offset + delta.X, 
        startPos.Y.Scale, 
        startPos.Y.Offset + delta.Y
    )
    game:GetService("TweenService"):Create(
        MainFrame, 
        TweenInfo.new(dragSpeed), 
        {Position = position}
    ):Play()
end

Title.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        dragToggle = true
        dragStart = input.Position
        startPos = MainFrame.Position
        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                dragToggle = false
            end
        end)
    end
end)

Title.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement then
        if dragToggle then
            updateInput(input)
        end
    end
end)
