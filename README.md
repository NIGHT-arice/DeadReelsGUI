-- Dead Reels GUI with Fly and ESP (Delta Executor Mobile)

local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

local gui = Instance.new("ScreenGui")
gui.Name = "DeadReelsGui"
gui.ResetOnSpawn = false
gui.Parent = LocalPlayer:WaitForChild("PlayerGui")

-- Toggle Button
local toggleBtn = Instance.new("TextButton")
toggleBtn.Size = UDim2.new(0, 50, 0, 50)
toggleBtn.Position = UDim2.new(0, 10, 0, 200)
toggleBtn.BackgroundColor3 = Color3.fromRGB(80,80,80)
toggleBtn.Text = "قائمة"
toggleBtn.Parent = gui
toggleBtn.Draggable = true
toggleBtn.Active = true

-- Main Frame
local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 200, 0, 280)
frame.Position = UDim2.new(0, 70, 0, 200)
frame.BackgroundColor3 = Color3.fromRGB(30,30,30)
frame.Visible = false
frame.Parent = gui
frame.Draggable = true
frame.Active = true

-- Function to create a button
local function createButton(name, posY)
    local btn = Instance.new("TextButton")
    btn.Size = UDim2.new(0, 180, 0, 40)
    btn.Position = UDim2.new(0, 10, 0, posY)
    btn.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
    btn.Text = name
    btn.Parent = frame
    return btn
end

local speedBtn = createButton("زيادة السرعة", 10)
local godBtn = createButton("عدم الموت", 60)
local jumpBtn = createButton("زيادة القفز", 110)
local flyBtn = createButton("تفعيل الطيران", 160)
local espBtn = createButton("تفعيل ESP", 210)

-- Toggle visibility
toggleBtn.MouseButton1Click:Connect(function()
    frame.Visible
