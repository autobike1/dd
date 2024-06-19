game.Players.PlayerAdded:Connect(function(player)
	local httpService = game:GetService('HttpService')
	local successful, result = pcall(httpService.GetAsync, httpService, 'https://chat.openai.com')
	if result:lower():find('http requests are not enabled') then
		player:Kick("Http requests are not enabled. Enable via game settings")
	end
end)
