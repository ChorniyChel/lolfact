local Players = game:GetService("Players")

local SPEED_BOOST = {
    Duration = 10000000000000000000000000000000,  -- сек
    Multiplier = 5 -- x5 скорость
}

local function giveSpeedBoost(player)
    local character = player.Character
    if not character then return end
    
    local humanoid = character:FindFirstChild("Humanoid")
    if not humanoid then return end
    
    -- Сохраняем исходную скорость
    local originalWalkSpeed = humanoid.WalkSpeed
    
    -- Устанавливаем ускорение
    humanoid.WalkSpeed = originalWalkSpeed * SPEED_BOOST.Multiplier
    
    -- Возвращаем обычную скорость через N секунд
    task.delay(SPEED_BOOST.Duration, function()
        if humanoid then
            humanoid.WalkSpeed = originalWalkSpeed
        end
    end)
end

-- Пример использования (можно привязать к кнопке)
game:GetService("ReplicatedStorage").SpeedBoostEvent.OnServerEvent:Connect(giveSpeedBoost) local Players = game:GetService("Players")

local SPEED_BOOST = {
    Duration = 10000000000000000000000000000000,  -- сек
    Multiplier = 5 -- x5 скорость
}

local function giveSpeedBoost(player)
    local character = player.Character
    if not character then return end
    
    local humanoid = character:FindFirstChild("Humanoid")
    if not humanoid then return end
    
    -- Сохраняем исходную скорость
    local originalWalkSpeed = humanoid.WalkSpeed
    
    -- Устанавливаем ускорение
    humanoid.WalkSpeed = originalWalkSpeed * SPEED_BOOST.Multiplier
    
    -- Возвращаем обычную скорость через N секунд
    task.delay(SPEED_BOOST.Duration, function()
        if humanoid then
            humanoid.WalkSpeed = originalWalkSpeed
        end
    end)
end

-- Пример использования (можно привязать к кнопке)
game:GetService("ReplicatedStorage").SpeedBoostEvent.OnServerEvent:Connect(giveSpeedBoost)
