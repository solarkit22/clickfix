# clickfix
Script for Logitech G Hub fixing double clicking

# Script
	EnablePrimaryMouseButtonEvents(true)
	lastInstance = 0
	debounceTime = 100
	function OnEvent(event, arg)
  	if (event == "MOUSE_BUTTON_PRESSED") and arg == 1 then
      if (GetRunningTime() - lastInstance) >= debounceTime then
        PressMouseButton(1)
      end
      lastInstance = GetRunningTime();
      else
        ReleaseMouseButton(1)
  	end
	end
