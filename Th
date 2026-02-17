--[[
══════════════════════════════════════════════════════════════════
    GHZ MENU RP - Script para Roblox (VERSÃO CORRIGIDA)
    Desenvolvedor: ghzmenu_developer & atr3uss_
    
    ⚙️ CONTROLE DE TAMANHO DA GUI - AJUSTE AQUI! ⚙️
══════════════════════════════════════════════════════════════════
]]--

local GUI_SCALE = 0.4
local MINI_MENU_SCALE = 0.3

-- Configurações de cores
local COLORS = {
    Background = Color3.fromRGB(0, 0, 0),
    Primary = Color3.fromRGB(80, 50, 150),
    Secondary = Color3.fromRGB(60, 40, 100),
    Text = Color3.fromRGB(255, 255, 255),
    Accent = Color3.fromRGB(100, 70, 180),
    MinimizeButton = Color3.fromRGB(120, 80, 200),
}

local DISCORD_LINK = "https://discord.gg/JHmJCxyk2P"

local savedMainPosition = nil
local savedMiniPosition = nil

local player = game.Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

local screenGui = Instance.new("ScreenGui")
screenGui.Name = "GHZ_MENU_RP"
screenGui.ResetOnSpawn = false
screenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
screenGui.Parent = playerGui

-- ═══════════════��═══════════════════════════════════════════════
-- FRAME PRINCIPAL (MENU COMPLETO)
-- ═══════════════════════════════════════════════════════════════
local mainFrame = Instance.new("Frame")
mainFrame.Name = "MainFrame"
mainFrame.Size = UDim2.new(0, 1300 * GUI_SCALE, 0, 650 * GUI_SCALE)
mainFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
mainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
mainFrame.BackgroundColor3 = COLORS.Background
mainFrame.BorderSizePixel = 0
mainFrame.Active = true
mainFrame.Parent = screenGui

local mainCorner = Instance.new("UICorner")
mainCorner.CornerRadius = UDim.new(0, 20 * GUI_SCALE)
mainCorner.Parent = mainFrame

local mainStroke = Instance.new("UIStroke")
mainStroke.Color = COLORS.Primary
mainStroke.Thickness = 2 * GUI_SCALE
mainStroke.Parent = mainFrame

-- Título
local titleLabel = Instance.new("TextLabel")
titleLabel.Name = "Title"
titleLabel.Size = UDim2.new(0, 1100 * GUI_SCALE, 0, 60 * GUI_SCALE)
titleLabel.Position = UDim2.new(0, 30 * GUI_SCALE, 0, 20 * GUI_SCALE)
titleLabel.BackgroundTransparency = 1
titleLabel.Text = "GHZ MENU RP"
titleLabel.Font = Enum.Font.GothamBold
titleLabel.TextSize = 36 * GUI_SCALE
titleLabel.TextColor3 = COLORS.Primary
titleLabel.TextXAlignment = Enum.TextXAlignment.Left
titleLabel.Parent = mainFrame

-- Botão de menu
local menuButton = Instance.new("TextButton")
menuButton.Name = "MenuButton"
menuButton.Size = UDim2.new(0, 50 * GUI_SCALE, 0, 50 * GUI_SCALE)
menuButton.Position = UDim2.new(1, -130 * GUI_SCALE, 0, 25 * GUI_SCALE)
menuButton.BackgroundColor3 = COLORS.Secondary
menuButton.BorderSizePixel = 0
menuButton.Text = "☰"
menuButton.Font = Enum.Font.GothamBold
menuButton.TextSize = 28 * GUI_SCALE
menuButton.TextColor3 = COLORS.Text
menuButton.Parent = mainFrame

local menuButtonCorner = Instance.new("UICorner")
menuButtonCorner.CornerRadius = UDim.new(0, 10 * GUI_SCALE)
menuButtonCorner.Parent = menuButton

-- Botão minimizar
local minimizeButton = Instance.new("TextButton")
minimizeButton.Name = "MinimizeButton"
minimizeButton.Size = UDim2.new(0, 50 * GUI_SCALE, 0, 50 * GUI_SCALE)
minimizeButton.Position = UDim2.new(1, -70 * GUI_SCALE, 0, 25 * GUI_SCALE)
minimizeButton.BackgroundColor3 = COLORS.MinimizeButton
minimizeButton.BorderSizePixel = 0
minimizeButton.Text = "─"
minimizeButton.Font = Enum.Font.GothamBold
minimizeButton.TextSize = 32 * GUI_SCALE
minimizeButton.TextColor3 = COLORS.Text
minimizeButton.Parent = mainFrame

local minimizeCorner = Instance.new("UICorner")
minimizeCorner.CornerRadius = UDim.new(0, 10 * GUI_SCALE)
minimizeCorner.Parent = minimizeButton

-- Linha separadora
local separatorLine = Instance.new("Frame")
separatorLine.Name = "SeparatorLine"
separatorLine.Size = UDim2.new(1, -40 * GUI_SCALE, 0, 2 * GUI_SCALE)
separatorLine.Position = UDim2.new(0, 20 * GUI_SCALE, 0, 90 * GUI_SCALE)
separatorLine.BackgroundColor3 = COLORS.Primary
separatorLine.BorderSizePixel = 0
separatorLine.Parent = mainFrame

-- Menu lateral
local sideMenu = Instance.new("Frame")
sideMenu.Name = "SideMenu"
sideMenu.Size = UDim2.new(0, 300 * GUI_SCALE, 1, -120 * GUI_SCALE)
sideMenu.Position = UDim2.new(0, 20 * GUI_SCALE, 0, 110 * GUI_SCALE)
sideMenu.BackgroundTransparency = 1
sideMenu.Parent = mainFrame

-- Linha vertical
local verticalLine = Instance.new("Frame")
verticalLine.Name = "VerticalLine"
verticalLine.Size = UDim2.new(0, 2 * GUI_SCALE, 1, 0)
verticalLine.Position = UDim2.new(0, 340 * GUI_SCALE, 0, 110 * GUI_SCALE)
verticalLine.BackgroundColor3 = COLORS.Primary
verticalLine.BorderSizePixel = 0
verticalLine.Parent = mainFrame

-- Área de conteúdo
local contentFrame = Instance.new("Frame")
contentFrame.Name = "ContentFrame"
contentFrame.Size = UDim2.new(0, 900 * GUI_SCALE, 1, -120 * GUI_SCALE)
contentFrame.Position = UDim2.new(0, 370 * GUI_SCALE, 0, 110 * GUI_SCALE)
contentFrame.BackgroundTransparency = 1
contentFrame.Parent = mainFrame

-- ═══════════════════════════════════════════════════════════════
-- ELEMENTOS HOME (QUE APARECEM QUANDO INICIA)
-- ═══════════════════════════════════════════════════════════════

-- Foto de perfil
local imageFrame = Instance.new("ImageLabel")
imageFrame.Name = "ProfileImage"
imageFrame.Size = UDim2.new(0, 240 * GUI_SCALE, 0, 240 * GUI_SCALE)
imageFrame.Position = UDim2.new(0, 30 * GUI_SCALE, 0, 40 * GUI_SCALE)
imageFrame.BackgroundColor3 = Color3.fromRGB(200, 200, 200)
imageFrame.BorderSizePixel = 0
imageFrame.Image = "https://www.roblox.com/headshot-thumbnail/image?userId=" .. player.UserId .. "&width=420&height=420&format=png"
imageFrame.Parent = contentFrame

local imageCorner = Instance.new("UICorner")
imageCorner.CornerRadius = UDim.new(1, 0)
imageCorner.Parent = imageFrame

-- Nome do usuário
local usernameLabel = Instance.new("TextLabel")
usernameLabel.Size = UDim2.new(0, 240 * GUI_SCALE, 0, 40 * GUI_SCALE)
usernameLabel.Position = UDim2.new(0, 30 * GUI_SCALE, 0, 295 * GUI_SCALE)
usernameLabel.BackgroundTransparency = 1
usernameLabel.Text = player.Name
usernameLabel.Font = Enum.Font.GothamBold
usernameLabel.TextSize = 18 * GUI_SCALE
usernameLabel.TextColor3 = COLORS.Text
usernameLabel.TextXAlignment = Enum.TextXAlignment.Center
usernameLabel.Parent = contentFrame

-- Textos do lado direito
local welcomeText = Instance.new("TextLabel")
welcomeText.Size = UDim2.new(0, 580 * GUI_SCALE, 0, 40 * GUI_SCALE)
welcomeText.Position = UDim2.new(0, 290 * GUI_SCALE, 0, 30 * GUI_SCALE)
welcomeText.BackgroundTransparency = 1
welcomeText.Text = "Olá, seja bem-vindo ao GHZ MENU RP"
welcomeText.Font = Enum.Font.GothamBold
welcomeText.TextSize = 22 * GUI_SCALE
welcomeText.TextColor3 = COLORS.Text
welcomeText.TextXAlignment = Enum.TextXAlignment.Left
welcomeText.TextWrapped = true
welcomeText.Parent = contentFrame

local descriptionText = Instance.new("TextLabel")
descriptionText.Size = UDim2.new(0, 580 * GUI_SCALE, 0, 60 * GUI_SCALE)
descriptionText.Position = UDim2.new(0, 290 * GUI_SCALE, 0, 75 * GUI_SCALE)
descriptionText.BackgroundTransparency = 1
descriptionText.Text = "O script para roblox focado no mapa\nSINTONIA RP"
descriptionText.Font = Enum.Font.Gotham
descriptionText.TextSize = 20 * GUI_SCALE
descriptionText.TextColor3 = COLORS.Text
descriptionText.TextXAlignment = Enum.TextXAlignment.Left
descriptionText.TextWrapped = true
descriptionText.Parent = contentFrame

local devTitle = Instance.new("TextLabel")
devTitle.Size = UDim2.new(0, 580 * GUI_SCALE, 0, 40 * GUI_SCALE)
devTitle.Position = UDim2.new(0, 290 * GUI_SCALE, 0, 160 * GUI_SCALE)
devTitle.BackgroundTransparency = 1
devTitle.Text = "Desenvolvedor"
devTitle.Font = Enum.Font.GothamBold
devTitle.TextSize = 26 * GUI_SCALE
devTitle.TextColor3 = COLORS.Text
devTitle.TextXAlignment = Enum.TextXAlignment.Center
devTitle.Parent = contentFrame

local dev1 = Instance.new("TextLabel")
dev1.Size = UDim2.new(0, 580 * GUI_SCALE, 0, 35 * GUI_SCALE)
dev1.Position = UDim2.new(0, 290 * GUI_SCALE, 0, 205 * GUI_SCALE)
dev1.BackgroundTransparency = 1
dev1.Text = "By: ghzmenu_developer"
dev1.Font = Enum.Font.Gotham
dev1.TextSize = 19 * GUI_SCALE
dev1.TextColor3 = COLORS.Text
dev1.TextXAlignment = Enum.TextXAlignment.Center
dev1.Parent = contentFrame

local dev2 = Instance.new("TextLabel")
dev2.Size = UDim2.new(0, 580 * GUI_SCALE, 0, 35 * GUI_SCALE)
dev2.Position = UDim2.new(0, 290 * GUI_SCALE, 0, 240 * GUI_SCALE)
dev2.BackgroundTransparency = 1
dev2.Text = "By: atr3uss_"
dev2.Font = Enum.Font.Gotham
dev2.TextSize = 19 * GUI_SCALE
dev2.TextColor3 = COLORS.Text
dev2.TextXAlignment = Enum.TextXAlignment.Center
dev2.Parent = contentFrame

-- Botão Discord
local discordButton = Instance.new("TextButton")
discordButton.Size = UDim2.new(0, 300 * GUI_SCALE, 0, 70 * GUI_SCALE)
discordButton.Position = UDim2.new(0, 430 * GUI_SCALE, 0, 295 * GUI_SCALE)
discordButton.BackgroundColor3 = COLORS.Secondary
discordButton.BorderSizePixel = 0
discordButton.Text = "Discord.link"
discordButton.Font = Enum.Font.GothamBold
discordButton.TextSize = 26 * GUI_SCALE
discordButton.TextColor3 = COLORS.Text
discordButton.Parent = contentFrame

local discordCorner = Instance.new("UICorner")
discordCorner.CornerRadius = UDim.new(0, 35 * GUI_SCALE)
discordCorner.Parent = discordButton

discordButton.MouseEnter:Connect(function()
    discordButton.BackgroundColor3 = COLORS.Accent
end)

discordButton.MouseLeave:Connect(function()
    discordButton.BackgroundColor3 = COLORS.Secondary
end)

discordButton.MouseButton1Click:Connect(function()
    setclipboard(DISCORD_LINK)
    local originalText = discordButton.Text
    discordButton.Text = "✓ Link copiado!"
    discordButton.BackgroundColor3 = Color3.fromRGB(50, 200, 50)
    task.wait(1.5)
    discordButton.Text = originalText
    discordButton.BackgroundColor3 = COLORS.Secondary
end)

-- Texto bug report
local bugReportText = Instance.new("TextLabel")
bugReportText.Size = UDim2.new(0, 600 * GUI_SCALE, 0, 60 * GUI_SCALE)
bugReportText.Position = UDim2.new(0, 30 * GUI_SCALE, 0, 395 * GUI_SCALE)
bugReportText.BackgroundTransparency = 1
bugReportText.Text = "Deseja relatar algum bug?\nEntre em nosso servidor do discord!"
bugReportText.Font = Enum.Font.Gotham
bugReportText.TextSize = 18 * GUI_SCALE
bugReportText.TextColor3 = COLORS.Text
bugReportText.TextXAlignment = Enum.TextXAlignment.Center
bugReportText.TextYAlignment = Enum.TextYAlignment.Center
bugReportText.TextWrapped = true
bugReportText.Parent = contentFrame

-- ═══════════════════════════════════════════════════════════════
-- ESTADOS DOS TOGGLES
-- ═══════════════════════════════════════════════════════════════
local tg = {}

local fn = {
    fly=function(s) if s then print("FLY ON") else print("FLY OFF") end end,
    noclip=function(s) if s then print("NOCLIP ON") else print("OFF") end end,
    aimbot=function(s) if s then print("AIMBOT ON") else print("OFF") end end,
    cb1=function(s) print("COMBATE BREVE 1") end,
    cb2=function(s) print("COMBATE BREVE 2") end,
    cb3=function(s) print("COMBATE BREVE 3") end,
    cb4=function(s) print("COMBATE BREVE 4") end,
    espname=function(s) if s then print("ESP NAME ON") else print("OFF") end end,
    esptrace=function(s) if s then print("ESP TRACE ON") else print("OFF") end end,
    espbox=function(s) if s then print("ESP BOX ON") else print("OFF") end end,
    esphead=function(s) if s then print("ESP HEAD ON") else print("OFF") end end,
    espdist=function(s) if s then print("ESP DIST ON") else print("OFF") end end,
    espbag=function(s) if s then print("ESP BAG ON") else print("OFF") end end,
    esplife=function(s) if s then print("ESP LIFE ON") else print("OFF") end end,
    espstaff=function(s) if s then print("ESP STAFF ON") else print("OFF") end end,
    f1=function(s) print("FARM 1") end,
    f2=function(s) print("FARM 2") end,
    f3=function(s) print("FARM 3") end,
    f4=function(s) print("FARM 4") end,
    f5=function(s) print("FARM 5") end,
    f6=function(s) print("FARM 6") end,
    f7=function(s) print("FARM 7") end,
    f8=function(s) print("FARM 8") end,
    c1=function(s) print("CFG 1") end,
    c2=function(s) print("CFG 2") end,
    c3=function(s) print("CFG 3") end,
    c4=function(s) print("CFG 4") end,
    c5=function(s) print("CFG 5") end,
    c6=function(s) print("CFG 6") end,
    c7=function(s) print("CFG 7") end,
    c8=function(s) print("CFG 8") end,
}

-- ═══════════════════════════════════════════════════════════════
-- FUNÇÕES AUXILIARES
-- ═══════════════════════════════════════════════════════════════

-- Criar toggle
local function mkT(p, txt, k, x, y)
    local f = Instance.new("Frame")
    f.Size = UDim2.new(0, 420 * GUI_SCALE, 0, 50 * GUI_SCALE)
    f.Position = UDim2.new(0, x, 0, y)
    f.BackgroundTransparency = 1
    f.Parent = p
    
    local l = Instance.new("TextLabel")
    l.Size = UDim2.new(0, 280 * GUI_SCALE, 1, 0)
    l.BackgroundTransparency = 1
    l.Text = txt
    l.Font = Enum.Font.GothamBold
    l.TextSize = 24 * GUI_SCALE
    l.TextColor3 = COLORS.Text
    l.TextXAlignment = Enum.TextXAlignment.Left
    l.Parent = f
    
    local b = Instance.new("TextButton")
    b.Size = UDim2.new(0, 110 * GUI_SCALE, 0, 45 * GUI_SCALE)
    b.Position = UDim2.new(1, -110 * GUI_SCALE, 0.5, 0)
    b.AnchorPoint = Vector2.new(0, 0.5)
    b.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
    b.BorderSizePixel = 0
    b.Text = ""
    b.Parent = f
    
    local bc = Instance.new("UICorner")
    bc.CornerRadius = UDim.new(1, 0)
    bc.Parent = b
    
    local c = Instance.new("Frame")
    c.Size = UDim2.new(0, 37 * GUI_SCALE, 0, 37 * GUI_SCALE)
    c.Position = UDim2.new(0, 4 * GUI_SCALE, 0.5, 0)
    c.AnchorPoint = Vector2.new(0, 0.5)
    c.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    c.BorderSizePixel = 0
    c.Parent = b
    
    local cc = Instance.new("UICorner")
    cc.CornerRadius = UDim.new(1, 0)
    cc.Parent = c
    
    tg[k] = false
    
    b.MouseButton1Click:Connect(function()
        tg[k] = not tg[k]
        if tg[k] then
            b.BackgroundColor3 = COLORS.Primary
            c.Position = UDim2.new(1, -41 * GUI_SCALE, 0.5, 0)
        else
            b.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
            c.Position = UDim2.new(0, 4 * GUI_SCALE, 0.5, 0)
        end
        if fn[k] then
            fn[k](tg[k])
        end
    end)
end

-- Criar botão teleport
local function mkB(p, txt, x, y)
    local b = Instance.new("TextButton")
    b.Size = UDim2.new(0, 260 * GUI_SCALE, 0, 60 * GUI_SCALE)
    b.Position = UDim2.new(0, x, 0, y)
    b.BackgroundColor3 = COLORS.Secondary
    b.BorderSizePixel = 0
    b.Text = txt
    b.Font = Enum.Font.GothamBold
    b.TextSize = 24 * GUI_SCALE
    b.TextColor3 = COLORS.Text
    b.Parent = p
    
    local bc = Instance.new("UICorner")
    bc.CornerRadius = UDim.new(0, 30 * GUI_SCALE)
    bc.Parent = b
    
    b.MouseEnter:Connect(function()
        b.BackgroundColor3 = COLORS.Accent
    end)
    
    b.MouseLeave:Connect(function()
        b.BackgroundColor3 = COLORS.Secondary
    end)
    
    b.MouseButton1Click:Connect(function()
        print("TP: " .. txt)
    end)
end

-- Limpar conteúdo
local function clr()
    for _, v in pairs(contentFrame:GetChildren()) do
        if v.Name ~= "ProfileImage" and v.Name ~= "UsernameLabel" and v.Name ~= "WelcomeText" and v.Name ~= "DescriptionText" and v.Name ~= "DevTitle" and v.Name ~= "Dev1" and v.Name ~= "Dev2" and v.Name ~= "DiscordButton" and v.Name ~= "BugReportText" then
            v:Destroy()
        end
    end
end

-- ══════════════════════════════��════════════════════════════════
-- FUNÇÕES DAS ABAS
-- ═══════════════════════════════════════════════════════════════

if input.UserInputState == Enum.UserInputState.End then
                miniDragging = false
            end
        end)
    end
end)

miniFrame.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
        miniDragInput = input
    end
end)

game:GetService("UserInputService").InputChanged:Connect(function(input)
    if miniDragging and input == miniDragInput then
        updateMiniDrag(input)
    end
end)

-- ═══════════════════════════════════════════════════════════════
-- MINIMIZAR E EXPANDIR
-- ════════════════════════════════════════════════════════════��══

minimizeButton.MouseButton1Click:Connect(function()
    savedMainPosition = mainFrame.Position
    
    if savedMiniPosition then
        miniFrame.Position = savedMiniPosition
    else
        miniFrame.Position = mainFrame.Position
    end
    
    mainFrame.Visible = false
    miniFrame.Visible = true
end)

expandButton.MouseButton1Click:Connect(function()
    savedMiniPosition = miniFrame.Position
    
    if savedMainPosition then
        mainFrame.Position = savedMainPosition
    end
    
    miniFrame.Visible = false
    mainFrame.Visible = true
end)

expandButton.MouseEnter:Connect(function()
    expandButton.BackgroundColor3 = COLORS.Accent
end)

expandButton.MouseLeave:Connect(function()
    expandButton.BackgroundColor3 = COLORS.Secondary
end)

-- Mensagem de inicialização
print("═══════════════════════════════════════════════════")
print("✅ GHZ MENU RP carregado com sucesso!")
print("📏 Escala: " .. GUI_SCALE)
print("👤 Usuário: " .. player.Name)
print("🎨 Desenvolvido por: ghzmenu_developer & atr3uss_")
print("═══════════════════════════════════════════════════")
