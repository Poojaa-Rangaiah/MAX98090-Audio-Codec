# MAX98090-Audio-Codec
The device tree overlay for the MAX98090 audio codec is avaliable for RPi4 model B Rev 1.5, armv7l (32-bit) architecture.

To edit this DTS file,
 `$sudo nano max98090.dts`
To compile it to .dtbo file,
 `$dtc -@ -I dts -O dtb -o max98090.dtbo max98090.dts`
To copy it to the overlays directory,
 `$sudo cp max98090.dtbo /boot/firmware/overlays/`
Ensure to add it in config.txt file,
 `$sudo nano /boot/firmware/config.txt`
Then add, 
 `dtoverlay = max98090` before that make sure if `dtparam=i2s=on` is uncommented, otherwise the external I2S interface in RPi'S GPIO will be disabled.
Then reboot your RPi with the following command,
 `$sudo reboot`