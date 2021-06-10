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

## Usage

### Create Applescript
Copy the code above. Open **Script Editor** and create new (**&#8984;+N**). Paste the code inside editor and save (**&#8984;+S**). 

### Save as Application
In Save Dialog fill the name of your new Application (_Blue filter_)
Select destination (_Application_)
File Format select **Application**, so you can easily run it from Spotlight search.
Other checkbox leave empty and save.

### Icon (opt.)
Now your blue filter script is ready, but for easy distinction, I prefer add own icon.

- Find your desired image and copy it to clipboard (**&#8984;+C**).
- Open Script location in Finder. 
- Select Script and open Get Info (**&#8984;+I**) from right-click menu.
- Click on script icon and you will see highlight. press (**&#8984;+V**) and your image from clipboard will be set as icon.

## Disclaimer
With new OSX versions it's possible that script will stop working. 
