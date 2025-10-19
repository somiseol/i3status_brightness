# i3status_brightness
brightness indicator addition for i3status bar using brightnessctl

## add to i3 config (change paths as needed):
```
#brightness up
bindsym XF86MonBrightnessUp exec sh -c "brightnessctl set +5% | grep -oE '[0-9]+%'> ~/.config/i3/bright_level" && $refresh_i3status

#brightness down
bindsym XF86MonBrightnessDown exec sh -c "brightnessctl set 5%- | grep -oE '[0-9]+%'> ~/.config/i3/bright_level" && $refresh_i3status
```


## add to i3status config (change paths as needed):
```
#add to status bar
order += "read_file brightness_level"

#reads brightness level from output file
read_file brightness_level {
         format = "Brightness: %content"
         path = "~/.config/i3/bright_level" 
}
``` 
