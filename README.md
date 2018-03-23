-----------------------------------------------------------------------------------------
-- Created by: Aayman Shameem
-- Created on: Mar 23 2018
-- 
-- This code will tell the user what kind of movie the user can watch based on the age input 
-----------------------------------------------------------------------------------------
-- the title on the top
local titleText = display.newText( "Type in age", display.contentCenterX, display.contentCenterY - 488, native.systemFont, 120 )

local moreText = display.newText( "You can watch a: ", display.contentCenterX, display.contentCenterY + 458, native.systemFont, 120 )

-- the text field for the user's input
local ageInput = native.newTextField( display.contentCenterX, display.contentCenterY - 177, 720, 277 )
ageInput.id = "The user's input"

-- the button of integers
local verifyButton = display.newImageRect( "./assets/sprites/enterButton.png", 675, 277 )
verifyButton.x = display.contentCenterX 
verifyButton.y = display.contentCenterY + 177
verifyButton.id = "the age button"



local function LeAgeButton( event )	

	local ageCheck = tonumber(ageInput.text)

	if ageCheck > 17 then 
	moreText.text = "You can watch a R rated movie alone."

	elseif ageCheck > 13 then 
	moreText.text = "You can watch a PG rated movie."

	else 
	moreText.text = "You can watch a G rated movie alone."	
	end
end

verifyButton:addEventListener( "touch", LeAgeButton )
