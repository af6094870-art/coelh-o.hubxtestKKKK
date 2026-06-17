repeat task.wait() until game:IsLoaded()

local PlaceIds = {
    [2753915549] = "World 1",
    [4442272183] = "World 2",
    [7449423635] = "World 3",
    [79091703265657] = "Sea 2",
    [996949360] = "Sea 2",
    [100117331123089] = "World 3",
    [994732206] = "World 3",
    [7326934954] = "99 nights in the florest"
}

local currentPlaceId = game.PlaceId
local CurrentWorld = PlaceIds[currentPlaceId] or "Desconhecido"

print("Mundo atual detectado: " .. CurrentWorld .. " (ID: " .. currentPlaceId .. ")")

-- Verifica se é o mapa "99 nights in the florest"
if currentPlaceId == 7326934954 then
    print("Carregando Script: 99 nights in the florest...")
    loadstring(game:HttpGet("https://raw.githubusercontent.com/af6094870-art/99-nights-in-the-florest/refs/heads/main/README.md"))()

-- Se for qualquer um dos outros mundos da lista (Blox Fruits)
elseif PlaceIds[currentPlaceId] and CurrentWorld ~= "Desconhecido" then
    print("Carregando Script: TesterCoelho Hub (Blox Fruits)...")
    loadstring(game:HttpGet("https://raw.githubusercontent.com/af6094870-art/pos-TesterCoelho-hub/refs/heads/main/README.md"))()

else
    print("Aviso: Jogo atual não está na lista de IDs permitidos. Nada foi executado.")
end
