local player = game.Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

local screenGui = Instance.new("ScreenGui")
screenGui.Name = "AvisoDiscordGui"
screenGui.ResetOnSpawn = false
screenGui.Parent = playerGui

local frame = Instance.new("Frame")
frame.Size = UUDim2.new(0, 400, 0, 200)
frame.Position = UDim2.new(0.5, -200, 0.5, -100) -- Centralizado na tela
frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30) -- Fundo escuro
frame.BorderSizePixel = 0
frame.Parent = screenGui

local uiCorner = Instance.new("UICorner")
uiCorner.CornerRadius = UDim.new(0, 12)
uiCorner.Parent = frame

local textLabel = Instance.new("TextLabel")
textLabel.Size = UDim2.new(1, -40, 0, 80)
textLabel.Position = UDim2.new(0, 20, 0, 20)
textLabel.Text = "This script is inactive, please look for others. If you want to join our Discord server:"
textLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
textLabel.TextSize = 18
textLabel.TextWrapped = true
textLabel.Font = Enum.Font.SourceSansMedium
textLabel.BackgroundTransparency = 1
textLabel.Parent = frame

local copyButton = Instance.new("TextButton")
copyButton.Size = UDim2.new(0, 200, 0, 45)
copyButton.Position = UDim2.new(0.5, -100, 1, -65) -- Posicionado embaixo
copyButton.BackgroundColor3 = Color3.fromRGB(88, 101, 242) -- Cor padrão do Discord
copyButton.Text = "Copy Discord"
copyButton.TextColor3 = Color3.fromRGB(255, 255, 255)
copyButton.TextSize = 18
copyButton.Font = Enum.Font.SourceSansBold
copyButton.Parent = frame

local buttonCorner = Instance.new("UICorner")
buttonCorner.CornerRadius = UDim.new(0, 8)
buttonCorner.Parent = copyButton

-- Função para copiar o link ao clicar
local discordLink = "https://discord.gg/QH4vbmq29"

copyButton.MouseButton1Click:Connect(function()

    setclipboard(discordLink)
    
    -- Feedback visual de que foi copiado
    copyButton.Text = "Copied!"
    copyButton.BackgroundColor3 = Color3.fromRGB(46, 204, 113) -- Muda para verde
    
    task.wait(2)
    
    -- Restaura o botão ao estado original
    copyButton.Text = "Copy Discord"
    copyButton.BackgroundColor3 = Color3.fromRGB(88, 101, 242)
end)
