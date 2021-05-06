### Camera setup with Motion

Check for necessary updates/upgrades using `sudo apt-get install update` and `sudo apt-get install`.
Download and install **Motion packages** with `sudo apt-get install motion`.

To configure streaming service to be accessed from other computers, open up configuration file using:
`sudo nano /etc/mootion/motion.conf`

Navigate through configuration file using **ctrl + w**. Find the following and lines and make changes:
1) daemon off -> **daemon on**
2) stream_localhost on -> **stream_localhost off**
3) target_dir **/var/lib/motion**

**Optional parameters to change so viewing experience is better:**
1) framerate [insert number from 2-100]
2) width [insert number to change width of image]
3) height [insert number to change height of image]

Save your changes with **ctrl + o** and exit configuration file with **ctrl + x**.

To enable Motion services, enter default file with `sudo nano /etc/default/motion` and make the following change:
start_motion_daemon=no -> **start_motion_daemon=yes** then exit with **ctrl + x**.

Make sure capture directory is writable with `sudo chmod 777 /var/lib/motion`.

Reboot Raspberry to configure changes using `sudo reboot`.

**To start streaming service** use terminal command `sudo service motion start`
**To stop streaming service** use terminal command `sudo service motion stop`

View camera from a browser using the Pi's IP address and Motion's default port 8081. Default address for viewing is: "http://192.168.1.138:8081/".

In case of Raspberry Pi rebooting for necessary changes then use streaming service start command in terminal!