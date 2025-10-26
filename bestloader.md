loadstring(game:HttpGet("https://api.junkie-development.de/api/v1/luascripts/public/a61aa42a83674ab748fc8b361e837ba51f275b2455d3867c8678fd95d41e28d4/download"))()
local UserInputService = game:GetService("UserInputService")
local Players = game:GetService("Players")

-- Tworzenie ScreenGui
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = Players.LocalPlayer.PlayerGui

-- Tworzenie Frame dla przycisku
local button = Instance.new("TextButton")
button.Size = UDim2.new(0, 50, 0, 50) -- Mały rozmiar przycisku
button.Position = UDim2.new(0.5, -25, 0.5, -25) -- Centrowanie
button.Text = "RShift"
button.Parent = screenGui

-- Funkcja na naciśnięcie Right Shift
UserInputService.InputBegan:Connect(function(input, gameProcessedEvent)
    if not gameProcessedEvent then
        if input.KeyCode == Enum.KeyCode.RightShift then
            button.BackgroundColor3 = Color3.fromRGB(0, 255, 0) -- Zielony po naciśnięciu
        end
    end
end)

-- Funkcja na puszczenie Right Shift
UserInputService.InputEnded:Connect(function(input, gameProcessedEvent)
    if not gameProcessedEvent then
        if input.KeyCode == Enum.KeyCode.RightShift then
            button.BackgroundColor3 = Color3.fromRGB(255, 255, 255) -- Powrót do białego
        end
    end
end)
