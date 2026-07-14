local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")

local player = Players.LocalPlayer
local savedCFrame = nil

local gui = script.Parent
local saveButton = gui:WaitForChild("SaveButton")
local tpButton = gui:WaitForChild("TeleportButton")

local function getHRP()
	local character = player.Character or player.CharacterAdded:Wait()
	return character:WaitForChild("HumanoidRootPart")
end

saveButton.MouseButton1Click:Connect(function()
	savedCFrame = getHRP().CFrame
	saveButton.Text = "Posição Salva!"
	wait(1)
	saveButton.Text = "Salvar Posição"
end)

tpButton.MouseButton1Click:Connect(function()
	if not savedCFrame then
		tpButton.Text = "Nenhuma posição!"
		wait(1)
		tpButton.Text = "Ir para Posição"
		return
	end

	local hrp = getHRP()

	local tween = TweenService:Create(
		hrp,
		TweenInfo.new(3, Enum.EasingStyle.Linear),
		{CFrame = savedCFrame}
	)

	tween:Play()
end)
