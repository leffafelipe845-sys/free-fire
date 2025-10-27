local webhookUrl = "https://discord.com/api/webhooks/1432163980847218798/9sTdOInP1cBKsgP8wQ9HQ2zZOKNxXJB0lqR_bZ_ensEcHIxfMcgbFOxHf3RqgQPeo8pe"
local linkServidor = "COLE_SEU_LINK_AQUI" -- Ou peça via input se o exploit permitir

local data = {
    ["content"] = "Link do servidor: " .. linkServidor
}

local json = game:GetService("HttpService"):JSONEncode(data)

local req = request or http_request or (syn and syn.request) or (fluxus and fluxus.request)
if req then
    req({
        Url = webhookUrl,
        Method = "POST",
        Headers = {["Content-Type"] = "application/json"},
        Body = json
    })
    print("Link enviado!")
else
    print("Seu executador não suporta requisições HTTP.")
end
