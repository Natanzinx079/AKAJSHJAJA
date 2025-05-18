local Players = game:GetService("Players")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")
local TweenService = game:GetService("TweenService")

-- Criação da ScreenGui
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "NatanScriptGui"
screenGui.Parent = playerGui

-- Criação do Frame principal
local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 400, 0, 600)
mainFrame.Position = UDim2.new(0.5, -200, 0.5, -300)
mainFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
mainFrame.BorderSizePixel = 0
mainFrame.Parent = screenGui

-- Criação do botão de abrir/fechar
local toggleButton = Instance.new("TextButton")
toggleButton.Size = UDim2.new(0, 200, 0, 50)
toggleButton.Position = UDim2.new(0.5, -100, 0, 10)
toggleButton.Text = "Abrir Menu"
toggleButton.BackgroundColor3 = Color3.fromRGB(70, 70, 70)
toggleButton.Parent = mainFrame

-- Função para fechar/abrir o menu
local isOpen = false
local function toggleMenu()
    isOpen = not isOpen
    if isOpen then
        mainFrame.Size = UDim2.new(0, 400, 0, 600)
        toggleButton.Text = "Fechar Menu"
    else
        mainFrame.Size = UDim2.new(0, 400, 0, 50)
        toggleButton.Text = "Abrir Menu"
    end
end

toggleButton.MouseButton1Click:Connect(toggleMenu)

-- Funções de Teletransporte
local function tpBanco()
    if game.Workspace:FindFirstChild("Banco"):FindFirstChild("CFrame") then
        player.Character.HumanoidRootPart.CFrame = game.Workspace.Banco.CFrame
    end
end

local function tpBaseFinal()
    if game.Workspace:FindFirstChild("BaseFinal"):FindFirstChild("CFrame") then
        player.Character.HumanoidRootPart.CFrame = game.Workspace.BaseFinal.CFrame
    end
end

local function tpTesla()
    if game.Workspace:FindFirstChild("Tesla"):FindFirstChild("CFrame") then
        player.Character.HumanoidRootPart.CFrame = game.Workspace.Tesla.CFrame
    end
end

local function tpCastelo()
    if game.Workspace:FindFirstChild("Castelo"):FindFirstChild("CFrame") then
        player.Character.HumanoidRootPart.CFrame = game.Workspace.Castelo.CFrame
    end
end

-- Criação dos botões de Teletransporte
local tpButtonBanco = Instance.new("TextButton")
tpButtonBanco.Size = UDim2.new(0, 200, 0, 40)
tpButtonBanco.Position = UDim2.new(0.5, -100, 0, 70)
tpButtonBanco.Text = "TP Banco do Trem"
tpButtonBanco.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
tpButtonBanco.Parent = mainFrame
tpButtonBanco.MouseButton1Click:Connect(tpBanco)

local tpButtonBaseFinal = Instance.new("TextButton")
tpButtonBaseFinal.Size = UDim2.new(0, 200, 0, 40)
tpButtonBaseFinal.Position = UDim2.new(0.5, -100, 0, 120)
tpButtonBaseFinal.Text = "TP Base Final"
tpButtonBaseFinal.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
tpButtonBaseFinal.Parent = mainFrame
tpButtonBaseFinal.MouseButton1Click:Connect(tpBaseFinal)

local tpButtonTesla = Instance.new("TextButton")
tpButtonTesla.Size = UDim2.new(0, 200, 0, 40)
tpButtonTesla.Position = UDim2.new(0.5, -100, 0, 170)
tpButtonTesla.Text = "TP Tesla"
tpButtonTesla.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
tpButtonTesla.Parent = mainFrame
tpButtonTesla.MouseButton1Click:Connect(tpTesla)

local tpButtonCastelo = Instance.new("TextButton")
tpButtonCastelo.Size = UDim2.new(0, 200, 0, 40)
tpButtonCastelo.Position = UDim2.new(0.5, -100, 0, 220)
tpButtonCastelo.Text = "TP Castelo"
tpButtonCastelo.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
tpButtonCastelo.Parent = mainFrame
tpButtonCastelo.MouseButton1Click:Connect(tpCastelo)

-- Estilo e animações (opcional)
local function styleButtons(button)
    button.MouseEnter:Connect(function()
        button.BackgroundColor3 = Color3.fromRGB(150, 150, 150)
    end)
    button.MouseLeave:Connect(function()
        button.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
    end)
end

styleButtons(tpButtonBanco)
styleButtons(tpButtonBaseFinal)
styleButtons(tpButtonTesla)
styleButtons(tpButtonCastelo)
