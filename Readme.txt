8-19-16

[The Novus Project]
The goal of this project is to creat a browser that works differently from how standard
browsers operate; specifically most emphasis will be on its user interface.

[Goals]
*Utilize WASD keys (or allow custom bindable keys) for shifting between browser windows;
it should appear to animate by sliding from a tab to another tab when any of the movement
keys are pressed. When the shift occurs, users should be able to see a minimap that pops
up temporarily in a corner somewhere that shows what tab their browser is focused on compared
to all other opened tabs. Initially, this should be limited to 9 browser windows and when users
reach an edge it jumps to the opposite side. Think of it like a grid, and see the example
below:
{tab 1} {@tab 2} {tab 3}	//@ represents the tab focused on
{tab 4} {tab 5} {tab 6}		//if the user moves up then it should go to tab 8
{tab 7} {tab 8} {tab 9}
	   |
	   V
{tab 1} {tab 2} {tab 3}	
{tab 4} {tab 5} {tab 6}	
{tab 7} {@tab 8} {tab 9}	//this limits browser to having 9 tabs opened at once in view
Optionally, allow users to open more than 9 tabs which will remove the ability to hop from one
edge to another. Instead, users would potentially have unlimited tabs to use. Whenever a tab is
closed, then it needs to close the open space by shifting another tab into the position that the
previous tab was, only if that tab was apart of the interior structure and surround by 4 other tabs.
In that case, the tab on the edge gets shifted in towards the center. Tabs on the edge that get closed
can be ignored and do not require any action.

*Indicate traversal tabs: these tabs are basically hotkeyed tabs that can be jumped to instantly by the
user to skip the process of scrolling to them with WASD. The input for this is simply pressing any of the
number keys 0-9; to set the traversal tabs, users must first hold Ctrl, then press the # key they would
like to hotkey that tab to. There should be some subtle indication on the popup minimap to indicate what
tabs are hotkeyed and what hotkey(s) they are assigned to.

*Tabs are stored together as a collection (name this later) in a backpack. The backpack is opened using
the 'i' key. In the backpack you can see all your collections of tabs, move to different ones, and start
new ones. Each collection holds in memory all the data (tabs) that were opened and they are minimized -
similar to how firefox stores tabs in memory but doesn't load them until in focus by the user - while
another collection is opened. This allows users to have access to more than 9 tabs only in this browser;
people can open as many collections as they want. The intended use is for collections to all be focused
on a similar topic such as tabs for sports, social media, video games, youtube videos, or any other group
of stuff that people find interesting. They would be able to swap between these collections of tabs freely
through the backpack feature.

*Develop user states "Navigation" and "Control". The Control state allows users to function the browser
like any typical standard browser such as Chrome or Firefox being able to type in information using any
of the keys and focusing on parts of the webpage using 'tab'. The Navigation state is what handles
traversal between each of the tabs and collections through using WASD or the 'i' key. If users click
somewhere on a webpage then it will shift to the Control state automatically and users can interact
with the webpage as normal. To go back to the Navigation state a bindable key for switching states is
used; the 'alt' key would probably work well for this since it conveniently located for ease of
use - not sure what to do for alternatives because this binding has to persist in both the Control
and Nav states (maybe make it right shift only?) - another option could be to use one of the 'F#' keys
such as F12. To differentiate between the current state the user is in, there should be a notable
visual difference between Control/Navigation states. One solution is to make different color schemes
for control and navigation: eg navigation mode could have a red color scheme around the borders of
the browser or for its overall look, but when it goes to control mode the color scheme should
interpolate to blue. Another recommendation is to make the address bar of a website only show while
the user is in control mode, and to hide it while navigating through pages in navigation mode.

*Develop a map mode (maybe make this a state?) that shows the overall picture in a grid-like
presentation of all websites that are currently open in a collection, in addition to any hotkeyed
traversal tabs. Users have the option of using mouse to select a tab to immediately jump to,
or to use the mouse to close out tabs they no longer want open. Whatever tab the mouse is hovered
over will become highlighted to indicate that tab is focused i.e. hotkeying will utilize that tab.

[Notes]
Keep in mind to make every action within the Navigation state bindable to any key - each binding must
use a unique key (no duplicate bindings allowed).

















