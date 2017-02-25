# Install Nvidia Proprietary Arch Linux
#based on https://github.com/midfingr tutorials
#YouTube Video: https://youtu.be/jZ2bQRJAg_w


#choose option1 (mesa) when gnome instalation asks
#sudo pacman -S xf86-video-nouveau (to confirm)

sudo pacman -S nvidia nvidia-libgl
#if asked to remove mesa-libgl, answer yes (y)
reboot


#32-bit libraries (multilib)

sudo pacman -S lib32-nvidia-utils lib32-nvidia-libgl lib32-mesa-demos libva-vdpau-driver
sudo pacman -S nvidia-settings


#Nvidia presistance service

sudo systemctl enable nvidia-persistenced.service
reboot


#check with (terminal):
glxinfo32 | grep OpenGL
vainfo


#Optional

sudo pacman -S nvdock #nvdock in system start commands to auto-start
sudo nvidia-xconfig --cool-bits=4 #control temp (reboot)
yaourt gputest
