# i3status_brightness
brightness indicator for i3status bar


add to i3 config (change paths as needed):
'''
# brightness settings
bindsym XF86MonBrightnessUp exec sh -c "brightnessctl set +5% | grep -oE '[0-9]+%'> ~/.config/i3/bright_level" && $refresh_i3status

bindsym XF86MonBrightnessDown exec sh -c "brightnessctl set 5%- | grep -oE '[0-9]+%'> ~/.config/i3/bright_level" && $refresh_i3status

'''


add to i3status config (change paths as needed):
'''
# add brightness level to status bar
order += "read_file brightness_level"

# read file contatining brightness level
read_file brightness_level {
         format = "Brightness: %content"
         path = "~/.config/i3/bright_level" 
}

'''
