# Installing-linux-on-Iomega-Lenovo-PX4-300D-NAS
This is a guide of how to install devuan linux into this NAS using TTL to USB adapter

I saw this old guide of how to install linux on  PX6-300D version, which is very similiar to this. 
https://open-desk.org/posts/linux-on-lenovo-emc-px6-300d/

![1](https://user-images.githubusercontent.com/76133742/217362709-4a67b757-c5ec-4994-b014-a3994813c23e.png)

Then I found out that I needed the TTL to USB adapter, which is PL2303. I strongly recommend you to buy this exact same chip, I bought another one, it didn't give no output. I think the other cheap one was missing some control chip that's why. 

Secondly, you need a multimeter to measure voltages. I recommend you do it. Even though I will give you which pin does give 5v and 3v vice versa, don't trust it. Don't fry your board and measure it yourself first. 

One of them gives 5 volts, which will go to 5V.
One of them gives 3V, which is RXD.
One of them doesn't give any voltages, it's GND.
One of them gives arbitrary voltages, such as 0.3V or 1.1V. It's then TXD.

After finding about these, you need these type of cables to connect them to the TTL to USB adapter. They are sold at electronic stores. It must be female on both ends. Plug them like in the photo.

![2](https://user-images.githubusercontent.com/76133742/217362803-7c462e20-00ba-4cdf-b3d6-fda6f0170df2.jpg)

Then, plug that USB into a PC's USB port, preferably USB2.0, it's more reliable. Then, I assume you use linux, inside minicom change the port name to ttyUSB0. There are minicom guides on the internet. Baudrate is 115200-N-1

![3](https://user-images.githubusercontent.com/76133742/217362888-4cc53d42-6889-4eed-a561-1d6fdfe1fc14.jpg)


Then, start the device, you will see a BIOS prompt. I think it was del button that got me into the BIOS menu. Then, there you see it has 1GB NAND FLASH chip inside, which the original firmware was installed. You can backup that if you want. It's actually debian 7, it's very old. And 1 GB is not enough for even debian server, so I used a small SSD instead of that, on USB 3.0 port. 

For this, there is an easy way. Install linux on an SSD on another PC, then remove it from the PC, then put that inside the NAS. It will work. But change the BIOS boot priority to that disk. 
![4](https://user-images.githubusercontent.com/76133742/217363093-81c7aa54-5fcc-4bf0-b5d4-019dfa6a5d62.jpg)
