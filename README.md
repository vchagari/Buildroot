#################################################################
#	
#		Buildroot 
#
#################################################################

Buildroot compilation:
	
	a. select a appropriate config file from the available default configs available in the configs folder based on your hardware platform. 
	b. make "file name" do make from the parent directory 
		example: I worked recently with the ATMEL SAMA5D2 Xplained rev.B Board, so I used "make atmel_sama5d2_xplained_mmc_defconfig" 
	c. vim .config (from the parent directory). 
	d. add the following lines in the .config file (not necessary, but enabling this will speed up your compilation). 
		1. BR2_JLEVEL=4 (assuming you have atleast 2 processor cores, if you have more, you can increase this number for faster compilation). 
		2. BR2_CCACHE=y. 
		3. If you want a Rootfs
			BR2_ROOTFS_OVERLAY=y
	e. make menuconfig 
		select all the target applications you might need for the buildroot, not necessarily required. 
	f. make linux-menuconfig
		select if anything required, not necessarily requried. 
	g. I added all the necessary basic tools for my project requirments, you can use if it serves your purpose, 
		It can be found in the confgs folder with the name "atmel_sama5d2_xplained_mmc_dev_mod_config".  
	h. Finally do a make in the parent directory.

Note:
Make sure to install all the required dependencies on your host system before compiling the Buildroot, please see buildroot manual for more information. 

References:
https://buildroot.org/

