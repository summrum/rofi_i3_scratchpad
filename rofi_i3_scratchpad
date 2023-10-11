#!/usr/bin/sh
# rofi i3 scratchpad menu mode v1.2

# create list of window IDs and titles in scratchpad
if [ "$(which jq)" ]; then
	scratched="$(i3-msg -t get_tree | jq '.nodes[] | .nodes[] | .nodes[] | select(.name=="__i3_scratch") | .floating_nodes[] | .nodes[] | .window,.name' | paste - -)"
	if [ "$@" ]; then
		# show all windows and none in scratchpad options
		case "$@" in
			"All Windows")
			i3-msg '[class=.] scratchpad show' && sleep 0.1s && pkill -u $USER rofi
			;;
			"No Windows in Scratchpad")
			exit 0
			;;
		# bring chosen window from scratchpad
			*)
	    	winid=$(echo "$@" | cut -f1)
	    	i3-msg "[id=$winid] scratchpad show" && pkill -u $USER rofi
	    	;;
	    esac
	else
		# create menu from list of windows (or lack of)
		if [ -z "$scratched" ]; then
	    	echo "No Windows in Scratchpad"
	    else
	        echo "$scratched"
	    	echo "All Windows"
	    fi
	fi
else
	echo "jq not found"
fi
