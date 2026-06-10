-- Criando a interface principal
local Player = game.Players.LocalPlayer
local PlayerGui = Player:WaitForChild("PlayerGui")

local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "CoelhoHubFarewell"
ScreenGui.ResetOnSpawn = false
ScreenGui.Parent = PlayerGui

-- Fundo da janela (Frame)
local Frame = Instance.new("Frame")
Frame.Size = UDim2.new(0, 400, 0, 250)
Frame.Position = UDim2.new(0.5, -200, 0.5, -125)
Frame.BackgroundColor3 = Color3.fromRGB(25, 25, 25) -- Fundo escuro elegante
Frame.BorderSizePixel = 0
Frame.Parent = ScreenGui

-- Cantos arredondados para o Frame
local FrameCorner = Instance.new("UICorner")
FrameCorner.CornerRadius = UDim.new(0, 12)
FrameCorner.Parent = Frame

-- Título / Mensagem em Inglês
local MessageLabel = Instance.new("TextLabel")
MessageLabel.Size = UDim2.new(1, -40, 0, 100)
MessageLabel.Position = UDim2.new(0, 20, 0, 30)
MessageLabel.BackgroundTransparency = 1
MessageLabel.Text = "Hey bro, it's over.\nI have no plans to work on the script anytime soon. Thanks for everything."
MessageLabel.TextColor3 = Color3.fromRGB(240, 240, 240)
MessageLabel.Font = Enum.Font.SourceSansProBold
MessageLabel.TextSize = 20
MessageLabel.TextWrapped = true
MessageLabel.TextYAlignment = Enum.TextYAlignment.Top
MessageLabel.Parent = Frame

-- Botão de Copiar Discord
local CopyButton = Instance.new("TextButton")
CopyButton.Size = UDim2.new(1, -80, 0, 45)
CopyButton.Position = UDim2.new(0, 40, 1, -75)
CopyButton.BackgroundColor3 = Color3.fromRGB(88, 101, 242) -- Cor Blurple do Discord
CopyButton.Text = "Copy Discord"
CopyButton.TextColor3 = Color3.fromRGB(255, 255, 255)
CopyButton.Font = Enum.Font.SourceSansProBold
CopyButton.TextSize = 18
CopyButton.Parent = Frame

-- Cantos arredondados para o Botão
local ButtonCorner = Instance.new("UICorner")
ButtonCorner.CornerRadius = UDim.new(0, 8)
ButtonCorner.Parent = CopyButton

-- Função para copiar o link (Usa a API do Executor do usuário)
CopyButton.MouseButton1Click:Connect(function()
    local discordLink = "https://discord.gg/yMUAgp5Zw"
    
    -- Verifica se o executor do jogador tem a função padrão de cópia
    if toclipboard then
        toclipboard(discordLink)
        CopyButton.Text = "Copied to Clipboard!"
        CopyButton.BackgroundColor3 = Color3.fromRGB(46, 204, 113) -- Muda para verde
    elseif setclipboard then
        setclipboard(discordLink)
        CopyButton.Text = "Copied to Clipboard!"
        CopyButton.BackgroundColor3 = Color3.fromRGB(46, 204, 113)
    else
        CopyButton.Text = "Error! Copy manually."
        CopyButton.BackgroundColor3 = Color3.fromRGB(231, 76, 60) -- Vermelho se falhar
    end
    
    -- Reseta o botão depois de 3 segundos
    task.wait(3)
    CopyButton.Text = "Copy Discord"
    CopyButton.BackgroundColor3 = Color3.fromRGB(88, 101, 242)
end)
