# Zenith Library
This library isnt fully finished.


## Starting the Library

```lua
UIS = game:GetService('UserInputService')
local players = game:GetService("Players")
local tweenService = game:GetService("TweenService")
local runService = game:GetService("RunService")
local coreGui = game:GetService("CoreGui")

local zenith = Instance.new("ScreenGui")
local TopBar = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local Main = Instance.new("Frame")
local UICorner_2 = Instance.new("UICorner")
local Cover1 = Instance.new("Frame")
local Frame = Instance.new("Frame")
local UICorner_3 = Instance.new("UICorner")
local Cover1_2 = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local Background = Instance.new("Frame")
local UICorner_4 = Instance.new("UICorner")
local Cover = Instance.new("Frame")
local Cover2 = Instance.new("Frame")
local Button = Instance.new("Frame")
local UICorner_5 = Instance.new("UICorner")
local UIPadding = Instance.new("UIPadding")
local TextLabel = Instance.new("TextLabel")
local Section = Instance.new("TextLabel")
local ToggleActive = Instance.new("Frame")
local UICorner_13 = Instance.new("UICorner")
local UIPadding_5 = Instance.new("UIPadding")
local TextLabel_4 = Instance.new("TextLabel")
local Frame_5 = Instance.new("Frame")
local UICorner_14 = Instance.new("UICorner")
local Frame_6 = Instance.new("Frame")
local UICorner_15 = Instance.new("UICorner")
local Cover_2 = Instance.new("Frame")
local line = Instance.new("Frame")
local Close = Instance.new("TextButton")
local Minimise = Instance.new("TextButton")
local layouttab = Instance.new("UIListLayout")
local tabframe = Instance.new("ScrollingFrame")

local Closed = false
local ToggleActive = false


local viewport = workspace.CurrentCamera.ViewportSize

local Library = {}
GUI = {}

function Library:validate(defaults, options)
	for i,v in pairs(defaults) do
		if options[i] == nil then
			options[i] = v
		end
	end
	return options
end

local tweenInfo = TweenInfo.new(
	1.5,
	Enum.EasingStyle.Linear,
	Enum.EasingDirection.Out,
	0,
	false,
	0
)

function Library:Init(options) 
	options = Library:validate({
		name = "ZENITH"
	}, options or {})

	local GUI = {}

	zenith.Name = "zenith"
	zenith.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
	zenith.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

	TopBar.Name = "TopBar"
	TopBar.Parent = zenith
	TopBar.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	TopBar.BorderColor3 = Color3.fromRGB(0, 0, 0)
	TopBar.BorderSizePixel = 0
	TopBar.Position = UDim2.new(0.400000006, 0, 0.25, 0)
	TopBar.Size = UDim2.new(0, 501, 0, 50)

	UICorner.Parent = TopBar

	Main.Name = "Main"
	Main.Parent = TopBar
	Main.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
	Main.BackgroundTransparency = 0.200
	Main.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Main.BorderSizePixel = 0
	Main.Position = UDim2.new(-0.383233547, 0, 0, 0)
	Main.Size = UDim2.new(0, 200, 0, 550)

	UICorner_2.Parent = Main

	Cover1.Name = "Cover1"
	Cover1.Parent = Main
	Cover1.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	Cover1.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Cover1.BorderSizePixel = 0
	Cover1.Position = UDim2.new(0.959285557, 0, 0, 0)
	Cover1.Size = UDim2.new(0, 8, 0, 50)

	Frame.Parent = Main
	Frame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Frame.BorderSizePixel = 0
	Frame.Position = UDim2.new(0, 0, 0.9087376, 0)
	Frame.Size = UDim2.new(0, 209, 0, 50)

	UICorner_3.Parent = Frame

	Cover1_2.Name = "Cover1"
	Cover1_2.Parent = Frame
	Cover1_2.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	Cover1_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Cover1_2.BorderSizePixel = 0
	Cover1_2.Size = UDim2.new(0, 14, 0, 7)

	Title.Name = "Title"
	Title.Parent = Main
	Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Title.BackgroundTransparency = 1.000
	Title.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Title.BorderSizePixel = 0
	Title.Position = UDim2.new(0.200000003, 0, 0.0102040814, 0)
	Title.Size = UDim2.new(0.920000017, 0, 0, 40)
	Title.Font = Enum.Font.SourceSansBold
	Title.Text = options.Title
	Title.TextColor3 = Color3.fromRGB(255, 255, 255)
	Title.TextSize = 40.000
	Title.TextWrapped = true
	Title.TextXAlignment = Enum.TextXAlignment.Left

	Background.Name = "Background"
	Background.Parent = TopBar
	Background.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	Background.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Background.BorderSizePixel = 0
	Background.Position = UDim2.new(0, 0, 1, 0)
	Background.Size = UDim2.new(0, 501, 0, 500)

	UICorner_4.Parent = Background

	Cover.Name = "Cover"
	Cover.Parent = Background
	Cover.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	Cover.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Cover.BorderSizePixel = 0
	Cover.Position = UDim2.new(0, 0, -0.00100746448, 0)
	Cover.Size = UDim2.new(0, 8, 0, 8)

	Cover2.Name = "Cover2"
	Cover2.Parent = Background
	Cover2.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	Cover2.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Cover2.BorderSizePixel = 0
	Cover2.Position = UDim2.new(0.984031916, 0, -0.00100746448, 0)
	Cover2.Size = UDim2.new(0, 8, 0, 8)

	Cover_2.Name = "Cover"
	Cover_2.Parent = TopBar
	Cover_2.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	Cover_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Cover_2.BorderSizePixel = 0
	Cover_2.Position = UDim2.new(0.984032035, 0, 0.839999974, 0)
	Cover_2.Size = UDim2.new(0, 8, 0, 8)

	Cover_2.Name = "Cover"
	Cover_2.Parent = TopBar
	Cover_2.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	Cover_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Cover_2.BorderSizePixel = 0
	Cover_2.Position = UDim2.new(0.984032035, 0, 0.839999974, 0)
	Cover_2.Size = UDim2.new(0, 8, 0, 8)

	line.Name = "line"
	line.Parent = TopBar
	line.BackgroundColor3 = Color3.fromRGB(70, 70, 70)
	line.BorderColor3 = Color3.fromRGB(0, 0, 0)
	line.BorderSizePixel = 0
	line.Position = UDim2.new(0, 0, 1, 0)
	line.Size = UDim2.new(1, 0, -0.0500000007, 1)
	
	tabframe.Parent = Main
	tabframe.Active = true
	tabframe.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	tabframe.BackgroundTransparency = 1.000
	tabframe.BorderColor3 = Color3.fromRGB(0, 0, 0)
	tabframe.BorderSizePixel = 0
	tabframe.Position = UDim2.new(0, 0, 0.114545457, 0)
	tabframe.Size = UDim2.new(0, 192, 0, 436)
	tabframe.ScrollBarThickness = 0


	layouttab.Parent = tabframe
	layouttab.SortOrder = Enum.SortOrder.LayoutOrder
	layouttab.Padding = UDim.new(0, 10)

	Close.Name = "Close"
	Close.Parent = TopBar
	Close.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Close.BackgroundTransparency = 1.000
	Close.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Close.BorderSizePixel = 0
	Close.Position = UDim2.new(0.900199711, 0, 0, 0)
	Close.Size = UDim2.new(0, 50, 0, 50)
	Close.Font = Enum.Font.Ubuntu
	Close.Text = "X"
	Close.TextColor3 = Color3.fromRGB(255, 255, 255)
	Close.TextSize = 25.000
	Close.TextWrapped = true
	Close.MouseButton1Down:Connect(function()
		zenith:Destroy()
	end)

	Minimise.Name = "Minimise"
	Minimise.Parent = TopBar
	Minimise.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Minimise.BackgroundTransparency = 1.000
	Minimise.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Minimise.BorderSizePixel = 0
	Minimise.Position = UDim2.new(0.820359409, 0, 0, 0)
	Minimise.Size = UDim2.new(0, 50, 0, 50)
	Minimise.Font = Enum.Font.Ubuntu
	Minimise.Text = "_"
	Minimise.TextColor3 = Color3.fromRGB(255, 255, 255)
	Minimise.TextSize = 25.000
	Minimise.TextWrapped = true
	Minimise.MouseButton1Click:Connect(function()
		if Closed == false then
			Main:TweenSize(UDim2.new(0,200,0,50), Enum.EasingDirection.In, Enum.EasingStyle.Linear, 0.2)
			Background:TweenSize(UDim2.new(0,501,0,0), Enum.EasingDirection.In, Enum.EasingStyle.Linear, 0.25)
			Closed = true
			wait(0.25)
			Background.Visible = false
			Frame.Visible = false
			tabframe.Visible = false
		else
			Main:TweenSize(UDim2.new(0,200,0,550), Enum.EasingDirection.In, Enum.EasingStyle.Linear, 0.25)
			Background:TweenSize(UDim2.new(0,501,0,500), Enum.EasingDirection.In, Enum.EasingStyle.Linear, 0.25)
			Background.Visible = true
			Frame.Visible = true
			tabframe.Visible = true

			Closed = false
		end
	end)
end






function GUI:CreateTab(options)
	options = Library:validate({
		name = "Home",
		icon = "rbxassetid://2790547157"
	}, options or {})

	local tab = {}

	local Tab = Instance.new("TextButton")
	Tab.Name = "Tab"
	Tab.Parent = tabframe
	Tab.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Tab.BackgroundTransparency = 1.000
	Tab.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Tab.BorderSizePixel = 0
	Tab.Position = UDim2.new(0, 0, 0, 0)
	Tab.Size = UDim2.new(0, 191, 0, 30)
	Tab.Font = Enum.Font.SourceSansBold
	Tab.Text = ""
	Tab.TextColor3 = Color3.fromRGB(255, 255, 255)
	Tab.TextSize = 20.000
	Tab.TextWrapped = true

	local Icon = Instance.new("ImageLabel")
	Icon.Name = "Icon"
	Icon.Parent = Tab
	Icon.BackgroundTransparency = 1.000
	Icon.BorderColor3 = Color3.fromRGB(27, 42, 53)
	Icon.Position = UDim2.new(0, 15, 0, 2)
	Icon.Size = UDim2.new(0, 25, 0, 25)
	Icon.Image = options.icon
	Icon.ImageColor3 = Color3.fromRGB(200,200,200)

	local title = Instance.new("TextLabel")
	title.Name = "title"
	title.Parent = Tab
	title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	title.BackgroundTransparency = 1.000
	title.BorderColor3 = Color3.fromRGB(0, 0, 0)
	title.BorderSizePixel = 0
	title.Position = UDim2.new(0.261780113, 0, 0, 0)
	title.Size = UDim2.new(0.738219917, 0, 1, 0)
	title.Font = Enum.Font.SourceSansBold
	title.Text = options.Text
	title.TextColor3 = Color3.fromRGB(200, 200, 200)
	title.TextSize = 20.000
	title.TextXAlignment = Enum.TextXAlignment.Left

	local Contentbox = Instance.new("Frame")
	Contentbox.Name = "Contentbox"
	Contentbox.Parent = Background
	Contentbox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Contentbox.BackgroundTransparency = 1.000
	Contentbox.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Contentbox.BorderSizePixel = 0
	Contentbox.Size = UDim2.new(1, 0, 1, 0)

	local ContentContainer = Instance.new("ScrollingFrame")
	ContentContainer.Name = "ContentContainer"
	ContentContainer.Parent = Contentbox
	ContentContainer.Active = true
	ContentContainer.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	ContentContainer.BackgroundTransparency = 1.000
	ContentContainer.BorderColor3 = Color3.fromRGB(0, 0, 0)
	ContentContainer.BorderSizePixel = 0
	ContentContainer.Position = UDim2.new(0.0500000007, 0, 0.0500000007, 0)
	ContentContainer.Size = UDim2.new(0.899999976, 0, 0.899999976, 0)
	ContentContainer.ScrollBarThickness = 0
	ContentContainer.Visible = false

	local UIPadding_2 = Instance.new("UIPadding")
	UIPadding_2.Parent = ContentContainer
	UIPadding_2.PaddingBottom = UDim.new(0, 1)
	UIPadding_2.PaddingLeft = UDim.new(0, 1)
	UIPadding_2.PaddingRight = UDim.new(0, 1)
	UIPadding_2.PaddingTop = UDim.new(0, 1)

	local UIListLayout = Instance.new("UIListLayout")
	UIListLayout.Parent = ContentContainer
	UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
	UIListLayout.Padding = UDim.new(0, 6)
	
	Tab.MouseButton1Click:Connect(function()

		for _, container in pairs(Background:GetChildren()) do
			if container:IsA("Frame") and container.Name == "Contentbox" then
				for _, child in pairs(container:GetChildren()) do
					if child:IsA("ScrollingFrame") then
						child.Visible = false  
					end
				end
			end
		end


		ContentContainer.Visible = true
	end)
	
	Tab.MouseButton1Click:Connect(function()

		for _, container in pairs(tabframe:GetChildren()) do
			if container:IsA("TextButton") and container.Name == "Tab" then
				for _, child in pairs(container:GetChildren()) do
					if child:IsA("TextLabel") then
						child.TextColor3 = Color3.fromRGB(200, 200, 200)
					end
				end
			end
		end
		
		title.TextColor3 = Color3.fromRGB(255, 255, 255)
	end)
	
	Tab.MouseButton1Click:Connect(function()

		for _, container in pairs(tabframe:GetChildren()) do
			if container:IsA("TextButton") and container.Name == "Tab" then
				for _, child in pairs(container:GetChildren()) do
					if child:IsA("ImageLabel") then
						child.ImageColor3 = Color3.fromRGB(200, 200, 200)
					end
				end
			end
		end

		Icon.ImageColor3 = Color3.fromRGB(255, 255, 255)
	end)

	return ContentContainer


end

function GUI:Button(options, parentFrame)
	options = Library:validate({
		text = "Button",
		Callback = function() end,
		initialPosition = nil  
	}, options or {})


	local buttonParent = parentFrame

	-- Calculate the Y position based on the number of existing buttons
	local buttonCount = #buttonParent:GetChildren()
	local buttonYPosition = -40 + buttonCount * 40  -- Base Y position for subsequent buttons
	if buttonCount == 0 then
		buttonYPosition = 0  -- Adjust Y position for the first button
	end

	local button = Instance.new("TextButton")
	button.Name = "Button"
	button.Parent = buttonParent
	button.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
	button.BorderColor3 = Color3.fromRGB(0, 0, 0)
	button.Font = Enum.Font.Ubuntu
	button.Text = options.text
	button.TextSize = 15
	button.TextColor3 = Color3.fromRGB(255, 255, 255)
	button.BorderSizePixel = 0
	button.Position = UDim2.new(0.02, 0, 0, buttonYPosition)
	button.Size = UDim2.new(0.96, 0, 0, 35)

	local UICorner = Instance.new("UICorner")
	UICorner.CornerRadius = UDim.new(0, 4)
	UICorner.Parent = button

	-- Connect the callback function to the button click event
	button.MouseButton1Click:Connect(options.Callback)

	return button
end








function GUI:Toggle(options, parentFrame)
	options = options or {}
	local text = options.text or "Toggle"
	local callback = options.callback or function(state) end


	local toggleParent = parentFrame

	local toggleCount = #toggleParent:GetChildren()
	local toggleYPosition = -40 + toggleCount * 40  -- Base Y position for subsequent buttons
	if toggleCount == 0 then
		toggleYPosition = 0  -- Adjust Y position for the first button
	end

	local ToggleInactive = Instance.new("Frame")
	ToggleInactive.Name = "ToggleInactive"
	ToggleInactive.Parent = toggleParent
	ToggleInactive.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
	ToggleInactive.BorderColor3 = Color3.fromRGB(0, 0, 0)
	ToggleInactive.BorderSizePixel = 0
	ToggleInactive.Position = UDim2.new(0.02, 0, 0, toggleYPosition)
	ToggleInactive.Size = UDim2.new(0.96, 0, 0, 35)

	local UICorner_10 = Instance.new("UICorner")
	UICorner_10.CornerRadius = UDim.new(0, 4)
	UICorner_10.Parent = ToggleInactive

	local UIPadding_4 = Instance.new("UIPadding")
	UIPadding_4.Parent = ToggleInactive
	UIPadding_4.PaddingBottom = UDim.new(0, 6)
	UIPadding_4.PaddingLeft = UDim.new(0, 6)
	UIPadding_4.PaddingRight = UDim.new(0, 6)
	UIPadding_4.PaddingTop = UDim.new(0, 6)

	local TextLabel_3 = Instance.new("TextLabel")
	TextLabel_3.Parent = ToggleInactive
	TextLabel_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel_3.BackgroundTransparency = 1.000
	TextLabel_3.BorderColor3 = Color3.fromRGB(0, 0, 0)
	TextLabel_3.BorderSizePixel = 0
	TextLabel_3.Position = UDim2.new(0, 0, -0.300000012, 0)
	TextLabel_3.Size = UDim2.new(1, 0, 0, 35)
	TextLabel_3.Font = Enum.Font.Ubuntu
	TextLabel_3.Text = text
	TextLabel_3.TextColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel_3.TextSize = 14.000
	TextLabel_3.TextXAlignment = Enum.TextXAlignment.Left

	local Frame_3 = Instance.new("Frame")
	Frame_3.Parent = ToggleInactive
	Frame_3.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
	Frame_3.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Frame_3.BorderSizePixel = 0
	Frame_3.Position = UDim2.new(0.869976342, 0, 0.157510504, 0)
	Frame_3.Size = UDim2.new(0, 50, 0, 15)

	local UICorner_11 = Instance.new("UICorner")
	UICorner_11.CornerRadius = UDim.new(1, 0)
	UICorner_11.Parent = Frame_3

	local Frame_4 = Instance.new("TextButton")
	Frame_4.Parent = Frame_3
	Frame_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Frame_4.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Frame_4.Text = ""
	Frame_4.BorderSizePixel = 0
	Frame_4.Position = UDim2.new(0, 0, -0.222924799, 0)
	Frame_4.Size = UDim2.new(0, 20, 0, 20)

	local UICorner_12 = Instance.new("UICorner")
	UICorner_12.CornerRadius = UDim.new(1, 0)
	UICorner_12.Parent = Frame_4

	local originalYScale = Frame_4.Position.Y.Scale
	local originalYOffset = Frame_4.Position.Y.Offset

	local ToggleActive = false -- Initialize ToggleActive

	Frame_4.MouseButton1Click:Connect(function()
		if ToggleActive == false then
			Frame_4:TweenPosition(UDim2.new(1, -Frame_4.Size.X.Offset, originalYScale, originalYOffset), Enum.EasingDirection.Out, Enum.EasingStyle.Back, 0.2, true)
			ToggleActive = true
		else
			ToggleActive = false
			Frame_4:TweenPosition(UDim2.new(0, 0, originalYScale, originalYOffset), Enum.EasingDirection.Out, Enum.EasingStyle.Back, 0.2)
		end
	end)

	Frame_4.MouseButton1Click:Connect(function()
		callback(ToggleActive) -- Pass the current state of the toggle button to the callback


	end)
end




function GUI:Slider(options, parentFrame)
	options = Library:validate({
		text = options.text or "Slider",
		min = options.min or 0,
		max = options.max or 100,
		default = options.default or 16,
		callback = options.callback or function(v) print(v) end
	}, options or {})

	local slider = {}

	-- Calculate the Y position based on the number of existing sliders
	local sliderCount = #parentFrame:GetChildren()
	local sliderYPosition = -27 + sliderCount * 37
	if sliderCount == 0 then
		sliderYPosition = 0  -- Adjust Y position for the first slider
	end
	
	
	local Slider = Instance.new("Frame")
	Slider.Name = "Slider"
	Slider.Parent = parentFrame
	Slider.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
	Slider.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Slider.BorderSizePixel = 0
	Slider.Position = UDim2.new(0.02, 0, 0, sliderYPosition)
	Slider.Size = UDim2.new(0.96, 0, 0, 55)

	local UICorner_6 = Instance.new("UICorner")
	UICorner_6.CornerRadius = UDim.new(0, 4)
	UICorner_6.Parent = Slider

	local UIPadding_3 = Instance.new("UIPadding")
	UIPadding_3.Parent = Slider
	UIPadding_3.PaddingBottom = UDim.new(0, 6)
	UIPadding_3.PaddingLeft = UDim.new(0, 6)
	UIPadding_3.PaddingRight = UDim.new(0, 6)
	UIPadding_3.PaddingTop = UDim.new(0, 6)

	local TextLabel_2 = Instance.new("TextLabel")
	TextLabel_2.Parent = Slider
	TextLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel_2.BackgroundTransparency = 1.000
	TextLabel_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
	TextLabel_2.BorderSizePixel = 0
	TextLabel_2.Position = UDim2.new(0, 0, -0.300000101, 0)
	TextLabel_2.Size = UDim2.new(0.921985805, 0, 0, 35)
	TextLabel_2.Font = Enum.Font.Ubuntu
	TextLabel_2.Text = "Slider"
	TextLabel_2.TextColor3 = Color3.fromRGB(255, 255, 255)
	TextLabel_2.TextSize = 14.000
	TextLabel_2.TextWrapped = true
	TextLabel_2.TextXAlignment = Enum.TextXAlignment.Left

	local Value = Instance.new("TextLabel")
	Value.Name = "Value"
	Value.Parent = Slider
	Value.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Value.BackgroundTransparency = 1.000
	Value.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Value.BorderSizePixel = 0
	Value.Position = UDim2.new(0.955082715, 0, -0.157719657, 0)
	Value.Size = UDim2.new(0, 25, 0, 25)
	Value.Font = Enum.Font.Ubuntu
	Value.Text = "0"
	Value.TextColor3 = Color3.fromRGB(255, 255, 255)
	Value.TextSize = 15.000
	Value.TextWrapped = true

	local SliderBack = Instance.new("Frame")
	SliderBack.Name = "SliderBack"
	SliderBack.Parent = Slider
	SliderBack.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
	SliderBack.BorderColor3 = Color3.fromRGB(0, 0, 0)
	SliderBack.BorderSizePixel = 0
	SliderBack.Position = UDim2.new(0, 0, 0.788598299, 0)
	SliderBack.Size = UDim2.new(1, 0, 0, 5)

	local UICorner_7 = Instance.new("UICorner")
	UICorner_7.Parent = SliderBack

	local Draggable = Instance.new("Frame")
	Draggable.Name = "Draggable"
	Draggable.Parent = SliderBack
	Draggable.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Draggable.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Draggable.BorderSizePixel = 0
	Draggable.Size = UDim2.new(0.5, 0, 0, 5)

	local UICorner_8 = Instance.new("UICorner")
	UICorner_8.Parent = Draggable

	local Frame_2 = Instance.new("Frame")
	Frame_2.Parent = Draggable
	Frame_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Frame_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Frame_2.BorderSizePixel = 0
	Frame_2.Position = UDim2.new(0.98, 0, -0.5, 0)
	Frame_2.Size = UDim2.new(0, 0, 2, 0)

	local UISizeConstraint = Instance.new("UISizeConstraint")
	UISizeConstraint.Parent = Frame_2
	UISizeConstraint.MinSize = Vector2.new(10, 10)

	local UICorner_9 = Instance.new("UICorner")
	UICorner_9.Parent = Frame_2
	
	local dragging = false
	local startSize = nil
	local startMousePosition = nil
	local sliderValue = options.default

	-- Methods
	function slider:SetValue(value)
		sliderValue = value
		Value.Text = tostring(sliderValue)
		options.callback(sliderValue)
	end

	function slider:GetValue()
		return sliderValue
	end

	Draggable.InputBegan:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 then
			dragging = true
			startSize = Draggable.Size.X.Scale  -- Store initial size
			startMousePosition = input.Position.X  -- Store initial mouse position
		end
	end)
	
	Frame_2.InputBegan:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 then
			dragging = true
			startSize = Draggable.Size.X.Scale  -- Store initial size
			startMousePosition = input.Position.X  -- Store initial mouse position
		end
	end)

	local UIS = game:GetService("UserInputService")

	UIS.InputChanged:Connect(function(value)
		if dragging and value.UserInputType == Enum.UserInputType.MouseMovement then
			local sliderWidth = SliderBack.AbsoluteSize.X
			local delta = value.Position.X - startMousePosition
			local newSize = math.clamp(startSize + (delta / sliderWidth), 0.01, 1)  -- Adjust size based on delta
			Draggable.Size = UDim2.new(newSize, 0, 1, 0)  -- Set new size
			local newValue = math.floor(options.min + (newSize * (options.max - options.min) + 0.5))  -- Calculate value based on position
			Value.Text = tostring(newValue)
			options.callback(newValue)  -- Call the callback with the new value
			sliderValue = newValue  -- Update slider value
		end
	end)

	UIS.InputEnded:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 then
			dragging = false
		end
	end)

	return slider
end






function GUI:Section(options, tab)
	options = Library:validate({
		text = "Section"  -- Change 'name' to 'text'
	}, options or {})

	local SectionFrame = Instance.new("Frame")
	SectionFrame.Name = "SectionFrame"
	SectionFrame.Parent = tab
	SectionFrame.BackgroundColor3 = Color3.fromRGB(22, 22, 22)
	SectionFrame.BorderColor3 = Color3.fromRGB(0, 0, 0)
	SectionFrame.BorderSizePixel = 0

	local UICorner_2 = Instance.new("UICorner")
	UICorner_2.CornerRadius = UDim.new(0, 5)
	UICorner_2.Parent = SectionFrame

	local Section = Instance.new("TextLabel")
	Section.Name = "Section"
	Section.Parent = SectionFrame
	Section.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Section.BackgroundTransparency = 1.000
	Section.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Section.BorderSizePixel = 0
	Section.Size = UDim2.new(1, 0, 0, 35) -- Adjusted size to fit the text
	Section.Font = Enum.Font.GothamBold
	Section.Text = options.text  -- Change from options.name to options.text
	Section.TextColor3 = Color3.fromRGB(255, 255, 255)
	Section.TextSize = 15.000
	Section.TextXAlignment = Enum.TextXAlignment.Left

	local sectionPadding = Instance.new("UIPadding")
	sectionPadding.Parent = Section
	sectionPadding.PaddingLeft = UDim.new(0, 5)  -- Adjust this value to move the text to the right

	local function updateSectionSize()
		local totalHeight = Section.Size.Y.Offset + 5
		for _, child in ipairs(SectionFrame:GetChildren()) do
			if child:IsA("TextLabel") or child:IsA("TextButton") or child:IsA("Frame") then
				totalHeight = totalHeight + child.Size.Y.Offset + 5 -- Add 5 pixels of padding between elements
			end
			if child.Name == "SliderFrame" then
				totalHeight = totalHeight + 20 -- Adjust height for sliders
			end
		end
		SectionFrame.Size = UDim2.new(1, 0, 0, totalHeight)
	end

	SectionFrame.ChildAdded:Connect(updateSectionSize)
	SectionFrame.ChildRemoved:Connect(updateSectionSize)

	return SectionFrame
end


function GUI:Notification(options)
	options = Library:validate({
		Title = options.Title or "Title",
		Description = options.Description or "Description",
		Time = tonumber(options.Time) or 3  -- Convert Time to a number
	}, options or {})

	local NotificationsGUI = game.Players.LocalPlayer:WaitForChild("PlayerGui"):FindFirstChild("Notifications")
	if not NotificationsGUI then
		NotificationsGUI = Instance.new("ScreenGui")
		NotificationsGUI.Name = "Notifications"
		NotificationsGUI.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
		NotificationsGUI.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
	end

	-- Calculate the position of the new notification frame
	local existingNotifications = NotificationsGUI:GetChildren()
	local yOffset = -105 * #existingNotifications  -- Adjust this value to increase the space between notifications
	local position = UDim2.new(1, 0, 0.8, yOffset)  -- Starting position for new notification frame

	local NotificationFrame = Instance.new("Frame")
	NotificationFrame.Name = "NotificationFrame"
	NotificationFrame.Parent = NotificationsGUI
	NotificationFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	NotificationFrame.BorderColor3 = Color3.fromRGB(0, 0, 0)
	NotificationFrame.BackgroundTransparency = 0.500
	NotificationFrame.BorderSizePixel = 0
	NotificationFrame.Position = position
	NotificationFrame.Size = UDim2.new(0, 300, 0, 100) -- Initial size

	local UICorner = Instance.new("UICorner")
	UICorner.CornerRadius = UDim.new(0, 7)
	UICorner.Parent = NotificationFrame

	local Title = Instance.new("TextLabel")
	Title.Name = "Title"
	Title.Parent = NotificationFrame
	Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Title.BackgroundTransparency = 1.000
	Title.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Title.BorderSizePixel = 0
	Title.Position = UDim2.new(0.0233333334, 0, 0.0700000003, 0)
	Title.Size = UDim2.new(0, 260, 0, 30)
	Title.Font = Enum.Font.Ubuntu
	Title.Text = options.Title
	Title.TextColor3 = Color3.fromRGB(255, 255, 255)
	Title.TextSize = 20.000
	Title.TextXAlignment = Enum.TextXAlignment.Left

	local Description = Instance.new("TextLabel")
	Description.Name = "Description"
	Description.Parent = NotificationFrame
	Description.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Description.BackgroundTransparency = 1.000
	Description.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Description.BorderSizePixel = 0
	Description.Position = UDim2.new(0.0233333334, 0, 0.349999994, 0)
	Description.Size = UDim2.new(0, 285, 0, 43)
	Description.Font = Enum.Font.Ubuntu
	Description.Text = options.Description
	Description.TextColor3 = Color3.fromRGB(255, 255, 255)
	Description.TextSize = 16.000
	Description.TextXAlignment = Enum.TextXAlignment.Left

	local Close = Instance.new("TextButton")
	Close.Name = "Close"
	Close.Parent = NotificationFrame
	Close.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Close.BackgroundTransparency = 1.000
	Close.BorderColor3 = Color3.fromRGB(0, 0, 0)
	Close.BorderSizePixel = 0
	Close.Position = UDim2.new(0.899999976, 0, 0, 0)
	Close.Size = UDim2.new(0, 30, 0, 30)
	Close.Font = Enum.Font.SourceSans
	Close.Text = "x"
	Close.TextColor3 = Color3.fromRGB(255, 255, 255)
	Close.TextScaled = true
	Close.TextSize = 14.000
	Close.TextWrapped = true
	Close.MouseButton1Click:Connect(function()
		NotificationFrame:Destroy()
	end)

	local NotificationTimerBackground = Instance.new("Frame")
	NotificationTimerBackground.Name = "NotificationTimerBackground"
	NotificationTimerBackground.Parent = NotificationFrame
	NotificationTimerBackground.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
	NotificationTimerBackground.BorderColor3 = Color3.fromRGB(0, 0, 0)
	NotificationTimerBackground.BorderSizePixel = 0
	NotificationTimerBackground.Position = UDim2.new(0.0233333334, 0, 0.829999983, 0)
	NotificationTimerBackground.Size = UDim2.new(0, 285, 0, 5)

	local UICorner_2 = Instance.new("UICorner")
	UICorner_2.CornerRadius = UDim.new(0, 3)
	UICorner_2.Parent = NotificationTimerBackground

	local NotificationTimer = Instance.new("Frame")
	NotificationTimer.Name = "NotificationTimer"
	NotificationTimer.Parent = NotificationFrame
	NotificationTimer.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	NotificationTimer.BorderColor3 = Color3.fromRGB(0, 0, 0)
	NotificationTimer.BorderSizePixel = 0
	NotificationTimer.Position = UDim2.new(0.0233333334, 0, 0.829999983, 0)
	NotificationTimer.Size = UDim2.new(0, 285, 0, 5)

	local UICorner_3 = Instance.new("UICorner")
	UICorner_3.CornerRadius = UDim.new(0, 3)
	UICorner_3.Parent = NotificationTimer

	NotificationFrame:TweenPosition(UDim2.new(0.77, 0, 0.8, yOffset), Enum.EasingDirection.In, Enum.EasingStyle.Sine, 0.5)

	NotificationTimer:TweenSize(UDim2.new(0, 0, 0, 5), Enum.EasingDirection.In, Enum.EasingStyle.Linear, options.Time)

	wait(options.Time)
	NotificationFrame:TweenPosition(UDim2.new(1, 0, 0.8, yOffset), Enum.EasingDirection.In, Enum.EasingStyle.Back, 0.5)
	wait(0.5)
	NotificationFrame:Destroy()
end


















local UIS = game:GetService('UserInputService')
local frame = TopBar
local dragToggle = nil
local dragSpeed = 0.1
local dragStart = nil
local startPos = nil

local function updateInput(input)
	local delta = input.Position - dragStart
	local position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X,
		startPos.Y.Scale, startPos.Y.Offset + delta.Y)
	game:GetService('TweenService'):Create(frame, TweenInfo.new(dragSpeed), {Position = position}):Play()
end

frame.InputBegan:Connect(function(input)
	if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) then 
		dragToggle = true
		dragStart = input.Position
		startPos = frame.Position
		input.Changed:Connect(function()
			if input.UserInputState == Enum.UserInputState.End then
				dragToggle = false
			end
		end)
	end
end)

UIS.InputChanged:Connect(function(input)
	if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
		if dragToggle then
			updateInput(input)
		end
	end
end)
```

## Creating the Window

```lua
local main = Library:Init { Title = "ZENITH" }
```

## Creating a Tab

```lua
local Tab = GUI:CreateTab({
	Text = "Tab",
	icon = "rbxassetid://2790547157"
})
```

## Adding a Section

```lua
local section = GUI:Section({
	text = "Section"
}, Tab)
```

## Adding a Button

```lua
local button1 = GUI:Button({
	text = "Button",
	Callback = function()
		print("Button clicked!")
	end,
}, section)
```

## Adding a Toggle

```lua
local Toggle = GUI:Toggle({
	text = "Toggle",
	callback = function(ToggleActive)
		if ToggleActive then
			print("Toggle Off")
		else
			print("Toggle On")
		end
	end
}, section)
```

## Adding a Slider

```lua
local Slider = GUI:Slider({
	text = "WalkSpeed",
	min = 16,
	max = 100,
	default = 16,
	callback = function(value)
		local humanoid = game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
		if humanoid then
			humanoid.WalkSpeed = value
		end
		end
}, section)
```

## Creating a Notification

```lua
local Notification = GUI:Notification({ Title = "Title", Description = "Hello", Time = "3" })
```
