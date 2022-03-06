# Rofi i3 Scratchpad Mode
An i3 scratchpad window selector mode for Rofi.
## Requirements:
**POSIX shell**  
**Rofi** window switcher/application launcher/dmenu replacement  
**i3** improved tiling window manager  
**jq** command line JSON processor  
## Usage:
Ensure script is executable, then use one of the following options to add to your Rofi modi:  

**Option 1:** Launch Rofi with a script mode set using the syntax ```"{name}:{executable}"```  
```
rofi -show scratchpad -modi "scratchpad:/path/to/script/rofi_i3_scratchpad"
```
**Option 2:** Add custom mode to Rofi ```config.rasi``` file  
```
configuration {
	modi: "scratchpad:/path/to/script/rofi_i3_scratchpad";
}
```
Other modi can be added as usual seprarated by commas.  

The i3 scratchpad mode should then be available when launching Rofi, offering a list of window IDs and titles along with "All Windows". Choosing any option will bring the selected window from the scratchpad, close Rofi and focus the window ("All Windows" will bring all windows from the scratchpad). If there are no windows in the scratchpad, "No Windows in Scratchpad" will be stated; selecting this option closes Rofi.
