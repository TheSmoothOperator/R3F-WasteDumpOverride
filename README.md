# R3F-WasteDumpOverride
This is a simple override used if you want to be able to sell R3F loaded cargo. This way your traders do not get overrun by mission (DMS, VEMF, etc) crates everywhere.

This overrides the wastedump trader to give a third option.

Option 1: Sell vehicle cargo (This is everything default in the vehicles inventory)
Option 2: Sell loaded cargo (This is everything loaded using R3F)
Option 3: Sell vehicle and ALL cargo (This is everythign. Vehicle, R3F cargo, and inventory)

INSTALLATION:
*************
Step 1: Copy "custom" folder into your mission folder
Step 2: Add these lines into your config.cpp for the mission in the "CfgExileCustomCode" section
------------------
ExileServer_system_trading_network_wasteDumpRequest = "custom\ExileServer_system_trading_network_wasteDumpRequest.sqf"; // R3F-WasteDumpOverride by Operator
ExileClient_gui_wasteDumpDialog_show = "custom\ExileClient_gui_wasteDumpDialog_show.sqf"; // R3F-WasteDumpOverride by Operator
ExileClient_gui_wasteDumpDialog_event_onModeDropDownSelectionChanged = "custom\ExileClient_gui_wasteDumpDialog_event_onModeDropDownSelectionChanged.sqf"; // R3F-WasteDumpOverride by Operator
------------------
Step 3: Pack it up and enjoy.


BUG(?):
*************
There is a single problem with this script. If you are doing "inception" with R3F, the script will not recognize items below level 1.
Example:
Hunter -- Level 0 (This is my vehicle)
Mission crate -- Level 1 (This crate is loaded into the hunter)
Hatchback -- Level 1 (This vehicle is loaded into the hunter)
Mission crate -- Level 2 (This is loaded into the hatchback)
Quad bike -- Level 2 (This is loaded into the hatchback)
Mission crate -- Level 3 (This is loaded into the quad)

In this example, I have a items below level 1. Now it will recognize the Hatchback and any items in its INVENTORY (not R3F), but anything below that will not be recognized and sold for zero. So everything will be sold, but you will only receive money for everything above the line.
*************
Hunter -- Level 0 (This is my vehicle)
Mission crate -- Level 1 (This crate is loaded into the hunter)
Hatchback -- Level 1 (This vehicle is loaded into the hunter)
------------------
Mission crate -- Level 2 (This is loaded into the hatchback)
Quad bike -- Level 2 (This is loaded into the hatchback)
Mission crate -- Level 3 (This is loaded into the quad)
*************


THANKS:
*************
ynpmoose for the R3F tag (ZeroSurvival.com)
mubby (FindersKeepers.info)