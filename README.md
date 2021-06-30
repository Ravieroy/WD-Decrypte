## Unlock Western Digital Hard Disk.

This is a fork of [SofianeHamlaou](https://github.com/SofianeHamlaoui/WD-Decrypte). I have merely written the script to automate the process for Debian/Arch based distros. You can find the original tutorial here https://youtu.be/Qz51UelzByA.
 
 ----
### This is a script I wrote to make the unlocking of Western Digital Hard Disk easier. There are other ways like using wdpassport-utils to unlock it, but for some reason it didn't work for me always or may be I am too lazy. Either way, this script will help you to make the process less tiresome. 

I do not claim to have written the code for unlocking the WD HDD itself as it has been done by experts already. I am merely using the github repo by Sofiane Hamlaou to make the process seamless and fast. This should work in all distros if all the dependencies are satisfied beforehand. For Debian/Ubuntu and arch-based distros you don't have to worry about dependencies as the script will prompt you to install if anything is missing.

**For Debian/Ubuntu/Arch-based distros just run the script. It will do the rest**

Having said that following programs are needed for this to work.

1. **sg3_utils** : You will be prompted for the installation of sg3-utils but you can get the deb files from [here](http://sg.danny.cz/sg/sg3_utils.html). If you want to install them manualy then download the deb files for Debian/Ubuntu and head over to the Downloads folder and use the following command to install it.
```bash
sudo dpkg -i fileName 
```
2. **python 2 or 3** : All the distros now have preinstalled python version 3 which you can check by `python3 --version` but for some reason the program looks for python and hence you might need python 2.7.x. When I checked the script in arch based linux Garuda Linux, it had `python --version` and hence you need not install python 2.7.x. 

**TL;DR :So to just cut things short, if `python --version` shows your python version then you are good to go else you need to install python.**

3. **Git** : You should have git installed but most probably you already have that. So just go ahead.
----

When you plug your WD-HDD you would only see WD Unlocker in your files.

![WD_unlocker](https://user-images.githubusercontent.com/81288438/120518555-53797180-c3ef-11eb-8517-835faa3b77f2.png)

1. Clone this repository or just copy paste `git clone https://github.com/Ravieroy/WD-Decrypte` and head over to the folder which contains the script.  Make sure the script has execute permissons. If not use `chmod +x unlockHdd.sh` to make it executable.


2. Run the script by `./unlockHdd.sh`. If it says ***permission denied*** then the script still doesn't have execute permissions. If it has (and all the dependencies are satisfied) this is what you should see. You would be prompted to clone the geekhaider's repository. 

![Cloning](https://user-images.githubusercontent.com/81288438/120519473-4741e400-c3f0-11eb-84b6-e55d18353ae8.png)

**Sometimes a operation not permitted error occurs as shown below but just keep doing as the script prompts and you will be good to go**

![Step_1](https://user-images.githubusercontent.com/81288438/120518967-c4208e00-c3ef-11eb-8158-40bfe1d05ca0.png)

4. Now most of the time the last line of the output should contain the mount name of your WD-HDD. This is in the [...] brackets, for example [sda], [sdb] etc. You need to enter your disk name **without the brackets**, like in my case it was **sda**. If you really want to be sure run the following command to see your HDD mentioned.

```bash
dmesg | grep -i scsi
```

![Step_2](https://user-images.githubusercontent.com/81288438/120520010-ee268000-c3f0-11eb-834b-500dd7dbe27f.png)


4. Now you need to enter you WD password which you had setup while first running the hard disk in windows PC. The password won't be shown or stored anywhere. Just enter it. Provide your root password as well. If everything goes well **SCSI Status: Good** should be prompted.

![Step_3](https://user-images.githubusercontent.com/81288438/120520134-11e9c600-c3f1-11eb-9e8a-22d9a60d4237.png)

![Step_4](https://user-images.githubusercontent.com/81288438/120520140-131af300-c3f1-11eb-80c5-6e9c063511a8.png)


Now you are done. Go ahead into your Files app and you should see your WD-HDD unlocked.

Hope this helps someone out there.
