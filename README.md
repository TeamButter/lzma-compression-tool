# LZMA compression tool 
This tool is used to compress kernel and recovery ramdisks to save up the space for devices have limited space for kernel and recovery .

## How to use this tool 
* You must first activate LZMA support for ramdisks in kernel .
	* Go to your kernel config file then change this **# CONFIG_RD_LZMA is not set** to **CONFIG_RD_LZMA=y**
* Get the following repos and put them in mentioned path 
	* compression tool - This repository. Clone this repository in device/vendor_name/device_name.
* Add those line to **BoardConfig.mk** file .
	# LZMA compression for recovery's & kernel ramdisk....
	#BOARD_CUSTOM_BOOTIMG_MK := device/vendor_name/device_name/custombootimg.mk
	#BOARD_CANT_BUILD_RECOVERY_FROM_BOOT_PATCH := true

* Enjoy 

#### Note
* This tool should work with any device .
* LZMA compression takes more time to decompress than GZIP but When I tested it didn't take more than 1 or 2 more seconds to decompress .
* You won't be able to decompress boot.img or recovery.img using boot-repacker or unpack tool for linux as you will get an error because those tools won't be able to decompress ramdisks for recovery or kernel -boot-repacker only gives you kernel zImage- and If you want to edit anything in ramdisk you will need to build it again from source !!!

## This tool derived from
	* http://review.cyanogenmod.org/#/c/96227/
	* http://review.cyanogenmod.org/#/c/118533/

## Credits (no specific order)
* Andreas Blaesius
* Dan Pasanen
* LehKeda
