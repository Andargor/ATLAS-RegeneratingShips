

# Regenerating Ships

This ATLAS mod regenerates the health of all player-owned ship structures, including planks, sails, guns, and all attached structures such as walls and ceilings. We use it on our private server, and it was created to alleviate the chore of manually repairing every structure that the crew won't repair. The default settings repair 200 health every 10 minutes (600 seconds), which will repair most medium ships within about 4 hours.

In order to keep the processing as light as possible, the health regeneration does not require resources, nor a crew. It will not interfere with normal repairs.


## INI SETTINGS

The following are the default settings, that can be modified by adding this section to the GameUserSettings of *every* tile in a grid. To keep the default settings, you do not need this entry in your INI.

[RegeneratingShips]
RegenerationInitialDelaySeconds=60.0
RegenerationIntervalSeconds=600.0
RegenerationAmountAnchored=200.0
RegenerationAmountUnanchored=0.0

The settings can be interpreted in this fashion:

Once a server is started, after *RegenerationInitialDelaySeconds*, start iterating over player-owned ships every *RegenerationIntervalSeconds*, and repair every attached structure by *RegenerationAmountAnchored* for anchored ships, and *RegenerationAmountUnanchored* for unanchored ones.

NOTE: The smaller the RegenerationIntervalSeconds, the processing is done more often. This may bog down large servers with many player ships. For more health regeneration, it is recommended to increase the RegenerationAmountAnchored and/or RegenerationAmountUnanchored values instead of shortening the processing interval.


