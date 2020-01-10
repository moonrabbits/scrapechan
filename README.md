# Mameko-Chan: A "quality analyzer" for all current posts on any 4chan board  

This Python script scrapes a specified 4chan board catalog for thread titles/teasers,
runs the titles against (you)r list of words/phrases, and returns the percentage of threads
that do not match anything in that list.

### Dependencies:  
	python-requests  
	python-httplib  


### Example Usage: 
	$ python3 memeko-chan.py g  
	$ python3 memeko-chan.py a


Running with no board argument will default to /g/  
Add any phrases or words that you want to filter to the lists within the code  
You'd probably want to add separate lists for each board you use  


Pay attention to the format of the phrase though, example:  

Adding "phone" will cause a post with 'microphone' to be deemed bad, however  
adding " phone " (spaces surrounding) will only do so if the word phone (by  
itself) is in the thread title  
	

I use this in my i3bar. If you are using i3blocks:  

	# /g/ thread analyzer
	[absolute_state]
	label=Absolute State
	interval=once
	command=echo $(python3 /path/to/memeko-chan.py)
	separator=true
