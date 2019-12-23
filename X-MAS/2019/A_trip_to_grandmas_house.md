# A trip to grandma's house

![chall]

We have been given a .vdi file which is a VirtualBox VM HDD. First I booted the VM and I am almost immediately greeted by a Windows 98 login prompt which has a few ways to bypass.

Method 1: This method is probably the easiest of the two, you simply press ESC or click the close button... Windows 98 did not have good security.

Method 2: This method is a bit more complicated than the previous and involves you going into the DOS prompt. To do this, reboot the VM and hold the CTRL key as the VM boots which will bring you to a Startup Menu. Then select `Command prompt only` which should bring you to a DOS prompt at the root of the C drive. Next, we need to navigate to the `WINDOWS` directory which we can do by simply entering `cd WINDOWS`. Here we need to change or delete the `THOMAS.PWL` file as this is the password file for the user 'Thomas', this can be done by either entering `del THOMAS.PWL` or `move THOMAS.PWL THOMAS.XYZ`. Then simply reboot the VM and enter whatever you want as the password and Windows will confirm the password and will regenerate the PWL file with the password you entered.

After bypassing the login screen, make sure to install the `Standard PCI Graphics Adapter (VGA)` driver which can be done by clicking next on the wizard, display all drivers, show all hardware, find the `SciTech Software, Inc.` manufacturer and then the `SciTech Display Doctor 7.0` model. Then select next and it will prompt you to reboot to install the driver which will fix the resolution of the VM.

For the rest of the drivers you can just click cancel as they are not necessary for completing the challenge.

If all goes well then you should be greeted with the desktop. There are a couple of points of interest:

- The icons spelling out `Mysekritd4tuM`.
- The file called `yeah that's the password`.
- The background saying `password is lowercase and has no spaces!`.
- A TrueCrypt shortcut.
- And a file called `secret.txt` which unintelligible if opened with notepad or any similar program.

![desk]

It's pretty safe to assume that the background and `yeah that's the password` relates to the icons spelling out a password and `secret.txt` is probably a TrueCrypt volume (which if you don't know, it is essentially an encrypted file that can be opened like a flash drive once decrypted).

So the next logical step is to enter `mysekritd4tum` as the password for `secret.txt` in TrueCrypt. This can be done by opening TrueCrypt, selecting `secret.txt` through the Select File button, selecting a drive letter for it to mount the file to, and then pressing Mount. This should decrypt the file and mount it to the letter specified.

If you look inside you will see some interesting looking files which is a Minecraft save file. As Minecraft is not installed and does not easily run on Windows 98 you need to transfer it off the VM, the easiest way to do this is by copying out the files to another location such as My Documents, booting another VM that has a shared folder or internet access and connect the `HDD.vdi` file as a secondary hard drive. Next, you can just either copy the files into the shared folder and access them on your host PC or upload them to something like Google Drive.

The easiest way to get the flag out of the world, other than just opening it with Minecraft, is to use a program like MCEdit or a different Minecraft map viewer. Next just look somewhere around 1000 blocks from 0, 0 and you should find the flag: `X-MAS{Druaga1_W0uld've_ruN__th1s_0n_4n_SSD}`! Which if you don't know is a reference to the [YouTuber Druaga1](https://www.youtube.com/user/Druaga1/) who has done videos such as installing Windows 98 on an SSD as well as installing Minecraft onto Windows 98.

## Problems I faced

I had quite a few issues throughout this challenge, from my VM not working to be just being stupid.

The first problem I faced was Windows crashing just before it loaded the desktop which I tried to get around by booting into safe mode however this meant that the display driver wouldn't be used and therefore only a small portion of the desktop would be visible. Additionally, It would destroy the formatting of any icons off-screen so even if you managed to boot it properly or tried `CTRL+A` ing then you wouldn't be able to see the rest of the password as it would become properly organised. The actual fix for me was to use VMware even though the author designed it in VirtualBox and other people could get to the desktop just fine with VirtualBox.

A minor issue caused by using VMware is the PCI Bridges that it uses which means you have to click cancel almost 40 times to get to the desktop as Windows doesn't like not having drivers for them.

Another problem that I had was the password as I thought the 'u' was a 'v' which meant that I wasted hours on trying to find out how to get into the file... In hindsight, it's really obvious that it is a 'u' and not a 'v'.

The next, more major, issue was TrueCrypt not mounting the volume and instead freezing the VM. This was pretty easily fixed by just transferring the secrests.txt file out of the VM and running TrueCrypt on my host PC.

## Closing thoughts on the challenge

Overall, it was a really fun and interesting adventure into Windows 98 and very unexpectantly resulting in me playing Minecraft of all things. Some of the problems that I had took hours for me to figure out how to fix but I eventually completed the challenge in 7th place, 1 day and 22 hours after release.



[chall]: challenge.png "Challenge screenshot"
[desk]: desktop.png "Desktop screenshot"
