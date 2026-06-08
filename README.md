-- Carrega a Fluent em segundo plano para enviar as notificações visuais bonitas
local Fluent = pcall(function()
    return loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
end)

-- CONFIGURAÇÃO DA KEY SECRETA DOS TESTERS
local CHAVE_TESTER_OFICIAL = "FLYSGASHPAIHSAFSJAKLSHFGHJKLKJHGFGSFGHAGFGGFY"

-- 1. VERIFICA SE O USUÁRIO É UM TESTER
if getgenv().KeyTester and getgenv().Keytester == CHAVE_TESTER_OFICIAL then
    
    -- Notificação opcional na tela avisando que o modo Beta foi ativado
    if type(Fluent) == "table" and Fluent.Notify then
        Fluent:Notify({
            Title = "Coelho Hub | Tester Mode",
            Content = "Chave Beta reconhecida! Carregando a versão de testes...",
            Duration = 4
        })
        task.wait(1)
    end
    
    -- EXECUTA O SCRIPT EXCLUSIVO DE TESTERS
    pcall(function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/af6094870-art/TesterCoelho-hub/refs/heads/main/README.md"))()
    end)

else
    -- 2. CASO NÃO HAJA A KEY (OU SEJA UM USUÁRIO COMUM), APENAS EXECUTA O SCRIPT NORMAL
    pcall(function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/af6094870-art/pos-TesterCoelho-hub/refs/heads/main/README.md"))()
    end)
end
