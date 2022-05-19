# libinput_touch_events_printout
Grab and printout libinput touch events.

Currently Listens for these events:
	ABS_MT_POSITION_Y
	ABS_MT_POSITION_X
	EV_SYN
	EV_ABS
	ABS_MT_SLOT (MultiTouch Event support. Max 4 slots)
	ABS_MT_TRACKING_ID
	SYN_DROPPED
	EV_SYN

More info on touch events here:
	https://www.kernel.org/doc/Documentation/input/event-codes.txt
	https://www.kernel.org/doc/Documentation/input/multi-touch-protocol.txt

In the Events a finger is lifted, the application dumps out the current stats on touch input gaps.

##Compiling:
==========
Natively:
	gcc -o touch_fast touch_events.c
	
cross:
	arm-linux-gnueabihf-gcc -o touch_fast touch_events.c

##Example Usage:
==============
touch_fast /dev/input/event1

##Example output:
===============
	Reading from:
	device file = /dev/input/event3
	device name = Unknown
	Time: 12.809210:  24 : 6
	Time: 13.109698:  23 : 5
	Time: 55.097399:  359 : 317
	Time: 55.107539:  359 : 319
	Time: 55.114337:  358 : 322
	Time: 55.124475:  357 : 325
	Time: 55.131240:  354 : 328
	Time: 55.141367:  351 : 331
	Time: 55.178539:  351 : 332
	Time: 55.185313:  351 : 333
	Time: 55.195529:  352 : 336
	Time: 55.202304:  354 : 339
	Time: 55.212444:  358 : 342
	Time: 55.222572:  360 : 345
	Time: 55.229365:  361 : 348
	----------MULTITOUCH DETECTED----------
	Time: 55.229365:  425 : 71
	Time: 55.239507:  425 : 71
	----------FINGER LIFTED----------
	X-Axis:|0|636|119|67|11|4|0|0|0|2|492|
	Y-Axis:|0|597|478|843|182|26|4|0|0|1|1096|
	Time: 55.266502:  361 : 348
	----------MULTITOUCH DETECTED----------
	Time: 55.266502:  361 : 349
	Time: 55.273258:  361 : 350
	Time: 55.281655:  360 : 352
	Time: 55.291793:  360 : 356
	Time: 116.017981:  471 : 444
	Time: 116.024734:  471 : 446
	Time: 116.034874:  470 : 449
	Time: 116.041640:  470 : 452
	Time: 116.051773:  470 : 455
	Time: 116.061901:  471 : 458
	Time: 116.122634:  471 : 459
	Time: 116.464995:  471 : 459
	----------FINGER LIFTED----------
	X-Axis:|0|1459|662|657|357|129|28|5|0|7|1685|
	Y-Axis:|0|962|681|1177|237|34|7|0|0|2|1596|
