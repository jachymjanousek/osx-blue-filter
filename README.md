# osx-blue-filter
Applescript that switch color filter checkbox in Accessibility/Display settings for flitering blue light.

## About
The snippet is written by me, possibly not the best approach, but it works! 😃

## Code 
```applescript
tell application "System Preferences"
	activate
	delay 0.1
	set the current pane to pane id "com.apple.preference.universalaccess"
	delay 0.1
	tell application "System Events"
		delay 0.1
		tell table 1 of scroll area 1 of window "Accessibility" of application process "System Preferences"
			select row 5
		end tell
		delay 0.1
		click radio button "Colour Filters" of tab group 1 of group 1 of window "Accessibility" of application process "System Preferences"
		click checkbox "Enable Colour Filters" of tab group 1 of group 1 of window "Accessibility" of application process "System Preferences"
	end tell
	quit
end tell
```

## "Installation"

### Create Applescript
Copy the code above. Open **Script Editor** and create new (**&#8984;+N**). Paste the code inside editor and save (**&#8984;+S**). 

### Save as Application
In Save Dialog fill the name of your new Application (_Blue filter_)
Select destination (_Application_)
File Format select **Application**, so you can easily run it from Spotlight search.
Other checkbox leave empty and save.

Now your blue filter App is ready to use!

## Setup Blue Filter

1. On your Mac, choose Apple menu > System Preferences, click Accessibility, click Display, then click Color Filters.

2. Select Enable Color Filters.

3. Click the “Filter type” pop-up menu, then choose **Color Tint**, which applies a tint to the entire screen.

4. Click on box with color tint inside. 

5. In color picker dialog, select "RGB Sliders" from pop-up menu.

6. Set values as desired. I prefer levae little bit of green, as I need better color distinction on code highlight in IDE. 

My RGB values are:
- Red: 255
- Green: 64
- Blue: 0

Close the color picer dialog and now you are ready to use this "App" as shortcut to toggle blue light filter

## Disclaimer

This script only enable/disable Color filter. It does not set the value of color that will be applied.
Maybe I will implement this in futuer, but for now, you have to set this up manually.

With new OSX versions it's possible that script will stop working. 

When the script is runnig do not click! You have to wait, until the script finish the action. If you click during the process, the script will fail and throw an error. Just close it and run again.
