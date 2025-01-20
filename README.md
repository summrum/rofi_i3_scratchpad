# Rofi i3/sway Scratchpad Mode
An i3/sway scratchpad window selector mode for Rofi. Not really of all that much use alongside the standard Rofi window mode, except that it _only_ selects scratchpad windows (so can be less cluttered in some situations) and also allows for presenting all scratchpad windows.  
## Requirements:
**POSIX shell**  
**Rofi** or **Rofi-wayland** window switcher/application launcher/dmenu replacement  
**i3** or **sway** improved tiling window manager  
**jq** command line JSON processor  
**pkill** process command
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
Other modi can be added as usual seprarated by commas; the mode also doesn't have to be called "scratchpad", any name or glyph can be used.  

The i3 scratchpad mode should then be available when launching Rofi, offering a list of window IDs and corresponding titles along with "All Windows". Choosing any option will bring the selected window from the scratchpad, close Rofi and focus the window ("All Windows" will bring all windows from the scratchpad). If there are no windows in the scratchpad, "No Windows in Scratchpad" will be stated; selecting this option closes Rofi.
