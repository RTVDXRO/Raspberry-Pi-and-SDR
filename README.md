<!DOCTYPE html>
<html class="no-js" lang="en">
  <head>
  </head>
  <body>
    <div class="wrapAll clearfix">
      <div class="mainsection"><br>
        <div class="article">
          <h1>Raspberry Pi and SDR<br>
          </h1>
          <p class="siteSub">
          </p>
          <div class="articleRight">
            <div class="articleRightInner"> <img src="img/R3b.jpg"
                alt="rasp" width="234" height="185"> </div>
            Raspberry Pi 3 Model B+ </div>
          <br>
          The Raspberry Pi is a series of small single-board computers
          developed by the Raspberry Pi Foundation to promote the
          teaching of basic computer science in schools and in
          developing countries.<br>
          <br>
          RTL-SDR dongles are often used on single board computers. <br>
          These small credit sized computers are powerful enough to run
          multiple dongles, and run various decoding programs. <br>
          Currently, the most popular of these small computers is the
          Raspberry Pi.<br>
          <br>
          This guide shows a setup with various Radiosonde Decoding
          programs such as Auto-RX, DxlAPRS, RS-Decoders, Sondefinder
          and more SR Goodies!<br>
          If the Pi runs rtl_tcp, SpyServer or a similar server, then
          the RTL-SDR can then be accessed by a networked connected PC
          anywhere in your house, or even remotely over the internet
          from anywhere in the world.<br>
          <br>
          <br>
          <div class="contentsPanel">
            <div class="contentsHeader">Contents:</div>
            <ul>
              <li><span></span>Overview
                <ul>
                  <li>1.1&nbsp; <a href="#Raspberry_Hardware_">Raspberry Hardware</a><br></li>
                  <li>1.2&nbsp; <a href="#Raspberry_-_Raspian_Buster_Install">Raspian Buster Install</a><br></li>
                  <li>1.3&nbsp; <a href="#LCD_Display_Install_">Install LCD Driver</a><br></li>
                  <li>1.4&nbsp; <a href="#Install_RTL-SDR_USB_Drivers:_">Install RTL-SDR Driver</a><br></li>
                  <li>1.5&nbsp; <a href="#Dependencies_">Dependencies</a><br></li>
                  <li>1.6&nbsp; <a href="#GPSD_">GPSD Setup</a><br></li>
                  <li>1.7&nbsp; <a href="#RS-Decoder_Scripts_">RS-Decoder Scripts</a><br></li>
                  <li>1.8&nbsp; <a href="#Foxtrot_GPS_">FoxtrotGPS</a><br></li>
                  <li>1.9&nbsp; <a href="#Navit_">Navit</a></li>
                  <li>2.0&nbsp; <a href="#Gqrx_">Gqrx</a></li>
                  <li>2.1&nbsp; <a href="#Virtual_Audio_Setup_">Virtual Audio Setup</a></li>
                  <li>2.2&nbsp; <a href="#librtlsdr_errors_and_workarounds">Librtlsdr Errors</a><br></li>
                  <li>2.3&nbsp; <a href="#Auto-RX_">Auto-RX</a></li>
                  <li>2.4&nbsp; <a href="#DxlAPRS_">DxlAPRS</a></li>
                  <li>2.5&nbsp; <a href="#APRS-Map_">APRS-Map</a></li>
                  <li>2.6&nbsp; <a href="#GPS2APRS_">GPS2APRS</a></li>
                  <li>2.7&nbsp; <a href="#RS-Decoder_with_APRS-Map._">RS-Decoder APRS-Map</a><br></li>
                  <li>2.8&nbsp; <a href="#SondeFinder_">SondeFinder</a></li>
                  <li>2.9&nbsp; <a href="#Multi-SDR_Script">MultiSDR</a></li>
                  <li>3.0&nbsp; <a href="#Direwolf_">Direwolf</a><br></li>
                  <li>3.1&nbsp; <a href="#Dump_VDL2_">DumpVDL2</a></li>
                  <li>3.2&nbsp; <a href="#FM-Transmitter_">FM-Transmitter</a></li>
                  <li>3.3&nbsp; <a href="#HeatMap_">HeatMap</a></li>
                  <li>3.4&nbsp; <a href="#Multimon_">Multimon</a></li>
                  <li>3.5&nbsp; <a href="#Qt-DAB_">Qt-DAB</a></li>
                  <li>3.6&nbsp; <a href="#Retrogram_">Retrogram</a></li>
                  <li>3.7&nbsp; <a href="#RTL_433_">RTL_433</a></li>
                  <li>3.8&nbsp; <a href="#rtl_tcp_and_Spyserver_">RTL-TCP and Spyserver </a><br></li>
                  <li>3.9&nbsp; <a href="#RTTY-Decoder_">RTTY-Decoder</a></li>
                  <li>4.0&nbsp; <a href="#Vor-Track_">Vor-Track</a></li>
                  <li>4.1&nbsp; <a href="#OpenWebRX_">OpenWebRX</a><br></li>
                  <li>4.2&nbsp; <a href="#RaspAP_">RaspAP</a></li>
                  <li>4.3&nbsp; <a href="#RPi-Monitor_">Rpi-Monitor</a></li>
                  <li>4.4&nbsp; <a href="#Tweaks_">Tweaks</a></li>
                  <li>4.5&nbsp; <a href="#Backup_Scripts_">Backup Scripts</a><br></li>
                </ul>
              </li>
            </ul>
          </div>
          <h2><a name="Raspberry_Hardware_"></a>Raspberry
            Hardware&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <br>
          </h2>
          <br>
          Raspberry Pi...<br>
          <br>
          <p> <img src="img/display.jpg" alt="" width="411"
              height="273"><br>
          </p>
          <p>3.5 inch TFT Lcd Touch Screen Raspberry Pi 480x320 RGB
            Pixels.<br>
          </p>
          &nbsp;<br>
          <p> <img src="img/sdr.jpg" alt="sdr" width="266" height="195">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <img src="img/v3.jpg" alt="" width="216" height="156"><br>
          </p>
          <p> RTL-SDR USB Adapter RTL2832U + R820T2 + 1PPM TCXO TV Tuner
            Stick Ontvanger Oscillator.<br>
            RTL-SDR Blog V3 R820T2 RTL2832U 1PPM TCXO SMA Software
            Defined Radio<br>
          </p>
          <a href="https://github.com/happysat/DFM-09-Modification-to-GPS-Mouse" target="_blank"><img
              src="img/Mini_DFM09_3.jpg" alt="" width="322" height="238"
              border="0"></a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          <img src="img/kb.jpg" alt="" width="245" height="157">
          <br><img src="img/powerbank.png" alt="" width="425" height="258"><br>
          DFM09 Modified GPS-Mouse, Wireless Keyboard and Powerbank.<br>
          <br>
          <img src="img/koel2.jpg" alt="" width="167" height="143">&nbsp;
          <img src="img/koel.jpg" alt="" width="220" height="172"><br>
          <br>
          Some extra cooling stuff.<br>
          <h2><a name="Raspberry_-_Raspian_Buster_Install"></a>Raspberry
            - Raspian Buster LXDE Install&nbsp;&nbsp; <br>
          </h2>
          <p><br>
            Install Buster preferred is Lite --&gt;&gt; <a
              href="https://downloads.raspberrypi.org/raspbian_lite/images/">https://downloads.raspberrypi.org/raspbian_lite/images/</a><br>
            <a
              href="https://downloads.raspberrypi.org/raspbian_lite/images/">
              <meta http-equiv="content-type" content="text/html;
                charset=UTF-8">
            </a>
            <meta http-equiv="content-type" content="text/html;
              charset=UTF-8">
            Full --&gt;&gt;&nbsp;&nbsp; <a
              href="https://downloads.raspberrypi.org/raspbian_full/images/">https://downloads.raspberrypi.org/raspbian_full/images/</a><br>
            Unzip and burn to SD <a
href="https://raspberry-projects.com/pi/pi-operating-systems/win32diskimager">https://raspberry-projects.com/pi/pi-operating-systems/win32diskimager</a></p>
          <p>Do not eject sd goto boot folder and make ssh file no
            contents inside, eject SD put in pi and boot.</p>
          <p><br>
            Find out in use IP (eth connected overhere) and login with <a
href="https://www.chiark.greenend.org.uk/%7Esgtatham/putty/latest.html">Putty</a><br>
          </p>
          <p> <img src="img/putty.png" alt="" width="493" height="251"></p>
          <p>SSH 22 User: <b>pi</b> password: <b>raspberry</b></p>
          <p><b>Change to new password:</b><br>
            passwd<br>
            <br>
          </p>
          <p><b>Paste in terminal for </b><b>update</b><b>:</b></p>
          <p>sudo apt-get update &amp;&amp; sudo apt-get upgrade -y
            &amp;&amp; sudo apt-get dist-upgrade<br>
            <br>
            <b>Install x-server and deps:</b><br>
          </p>
          <p>sudo apt-get install --no-install-recommends xserver-xorg
            xinit xserver-xorg-input-evdev -y<br>
            <br>
            <b>Install LXDE Desktop:</b><br>
          </p>
          <p>sudo apt-get install lxde-core lxappearance lxtask -y<br>
            <br>
          </p>
          <p><b>Install Raspberry Stuff:</b><br>
            sudo apt-get install raspberrypi-ui-mods -y<br>
          </p>
          <p><br>
            <b>Audio and Some other Programs:</b><br>
          </p>
          <p>sudo apt-get install pulseaudio pavucontrol preload pluma
            alacarte gpicview xfce4-terminal p7zip-full file-roller
            dialog -y<br>
            <br>
            <b>Samba:</b><br>
          </p>
          <p>sudo apt-get install samba samba-common-bin<br>
            <br>
            sudo smbpasswd -a pi<br>
            Then set a password as prompted.<br>
            &nbsp;<br>
            <b>Enable Auto-login, Display, Expand filesystem, VNC, WiFi
              ect with raspi-config:</b><br>
            sudo raspi-config<br>
          </p>
          <p> Choose option 3: Boot Options<br>
            Choose option B1: Desktop / CLI and B4 Desktop Autologin
            Desktop Gui ect.<br>
            <br>
          </p>
          <p><img src="img/raspicfg.png" alt="" width="478" height="220"><br>
          </p>
          <br>
          <p>Setup country WiFi in 4 Localization Options.<br>
            Select&nbsp; 5 Interface Options:<br>
            Enable P3 VNC.<br>
          </p>
          <p>Select 7 Advanced options, A1 Expand Filesystem<br>
          </p>
          <p>Select <b>Finish</b>, and<b> reboot the pi </b>hopefully
            return in Gui Desktop mode ;)<br>
            <br>
          </p>
          <p>Cleanup the install mess leftovers, sudo apt autoremove
            &amp;&amp; sudo apt clean<br>
          </p>
          <h2><a name="LCD_Display_Install_"></a>LCD Display Install<br>
          </h2>
          sudo raspi-config<br>
          <br>
          Select&nbsp; 5 Interface Options:<br>
          Enable P4 SPI.<b><br>
          </b><b><br>
          </b> git clone https://github.com/waveshare/LCD-show.git<br>
          cd LCD-show/<br>
          ./LCD35-show <br>
          <br>
          With the recent updates in Raspbian Buster to Kernel v5, the
          old display driver is not working anymore.<br>
          <br>
          sudo rm -rf LCD-show (remove old LCD-Show)<br>
          <br>
          git clone https://github.com/MrYacha/LCD-show.git<br>
          chmod -R 755 LCD-show &amp;&amp; cd LCD-show/<br>
          sudo ./LCD35-show<br>
          <br>
          The LCD35 is a generic design made by lots of different
          manufacturers most of them use the ILI9486 driver and some
          work faster than others in terms of refresh rates. <br>
          There are slow 16MHz (blue pcb) and a fast 125MHz (black pcb)
          display versions.<br>
          <br>
          To determin which refresh rate your display has, goto
          /var/log/kernel.log open it and search for string fb1.<br>
          <br>
          The default setting is 15 MHz, which is slow but safe - you
          should have no problems with this speed,<br>
          but the display refresh isn't very fast. <br>
          If you can run the display at a faster clock rate, the refresh
          rate will improve.<br>
          <br>
          In /boot/config.txt refresh rate set to 20MHz,
          dtoverlay=waveshare35a:speed=20000000<br>
          If the display does not support refresh rates above 20MHz
          colors acting weird and the screen flickers.<br>
          <br>
          If you want to try different clock rates to see how fast your
          display will go, MrYacha GIT repo has also done a set of
          configurations at different clock rates for you to test. <br>
          Download the TAR archive here: <a
            href="https://ufile.io/vaeet36o" target="_blank">https://ufile.io/vaeet36o</a>
          to your Pi. <br>
          Then untar it and try the different dtbo/dto files (20 -
          115MHz) to see which is best for you.<br>
          <br>
          tar -xf lcd.tar<br>
          sudo cp 20.dto /boot/overlays/waveshare35a.dtbo<br>
          sudo reboot<br>
          etc.
          <h2><a name="Install_RTL-SDR_USB_Drivers:_"></a>Install
            RTL-SDR USB Drivers:<br>
          </h2>
          Open the terminal and Install the necessary tools:<br>
          <br>
          sudo apt-get install git cmake build-essential
          libusb-1.0-0-dev<br>
          <br>
          <b>Install RTL-SDR-Blog Driver:</b><br>
          <br>
          git clone git://github.com/happysat/rtl-sdr-blog.git<br>
          cd rtl-sdr-blog/<br>
          mkdir build<br>
          cd build<br>
          cmake ../ -DINSTALL_UDEV_RULES=ON -DDETACH_KERNEL_DRIVER=ON<br>
          make<br>
          sudo make install<br>
          sudo ldconfig<br>
          sudo cp ../rtl-sdr.rules /etc/udev/rules.d/<br>
          echo blacklist dvb_usb_rtl28xxu &gt;&gt; blacklist-rtl.conf<br>
          echo blacklist rtl2832 &gt;&gt; blacklist-rtl.conf<br>
          echo blacklist rtl2830 &gt;&gt; blacklist-rtl.conf<br>
          sudo cp blacklist-rtl.conf /etc/modprobe.d/<br>
          <br>
          Save the file and reboot the machine.<br>
          <br>
          <b>Improvements:</b><br>
          <br>
          rtl_tcp is significantly improved by modifying to code to use
          a ring buffer instead of using semaphore based locking.<br>
          The result is a tremendous performance improvement in rtl_tcp.<br>
          <br>
          After the ring buffer changes rtl_tcp can handle much better
          and higher maximum sample rate's with less lag. <br>
          Unfortunately this patch is not included in the official
          upstreamed Osmocom drivers.<br>
          <h2><a name="Dependencies_"></a>Dependencies<br>
          </h2>
          sudo apt-get install xfce4-terminal&nbsp; <br>
          sudo apt-get install dialog <br>
          sudo apt-get install socat&nbsp; <br>
          sudo apt-get install perl&nbsp;&nbsp; <br>
          sudo apt-get install&nbsp; sox&nbsp; <br>
          sudo apt-get install gpsd gpsd-clients python-gps<br>
          <br>
          Needed for: Tabbed terminal for small screens, menu scripts,
          pty-link virtualports, NMEA script, audio and GPS support.
          <h2><a name="GPSD_"></a>GPSD
            Setup&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <br>
          </h2>
          <p> <br>
            In order to use gpsd with the decoder we have to <b>disable
              the service</b>.<br>
            So it can be manually started by the decoder:</p>
          <b>sudo systemctl stop gpsd.socket</b><br>
          <b>sudo systemctl disable gpsd.socket</b><br>
          <br>
          Should you ever want to enable the default gpsd systemd
          service you can run these commands to restore it:<br>
          <b>sudo systemctl enable gpsd.socket</b> and <b>sudo
            systemctl start gpsd.socket</b><br>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;"> </p>
          <h2><a name="RS-Decoder_Scripts_"></a>RS-Decoder Scripts<br>
          </h2>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;"><br>
            <a href="files/RS-Decoders.tar.gz?raw=true">Download</a> <b>Pre-Compiled
              Decoders</b></p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;"><b><a
                href="https://github.com/happysat/RS-Binaries/tree/main/Raspberry" target="_blank">Updated
                compiled RS-Decoders are overhere.</a><br>
              <br>
            </b></p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;"><b>Setup:<br>
            </b> </p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;">Extract
            RS-Decoders.tar.gz</p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;"><img
              src="img/Extract.png" alt="" width="318" height="180"> <br>
          </p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;">chmod 755 -R
            home/pi/Radio/Radiosonde</p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;"><br>
            <b>Create new group with the groupadd command:</b><br>
            sudo groupadd dailout <br>
            <br>
            <b>Add user to a group with the gpasswd command:</b><br>
            sudo adduser pi dialout<br>
            <b><br>
            </b></p>
          <p><b>Make permissions for COM ports:</b></p>
          <p>Run ./home/pi/Radio/Radiosonde/vp1.sh so the virtual ports
            are accessible in /tmp for setting chown permissions.</p>
          <p><img src="img/ports_perm.png" alt="" width="467"
              height="216"><br>
          </p>
          sudo chown -R pi:pi /tmp/virtualcom0<br>
          sudo chown -R pi:pi /tmp/virtualcom1<br>
          <br>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;"><img
              src="img/rtl_fm.png" alt="" width="456" height="238"><br>
            <br>
          </p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;">Run shortcut from
            desktop, start <a href="#Foxtrot_GPS_">FoxtrotGPS</a>.<br>
            <br>
          </p>
          <p> <b>Folders and Symlinks for the Decoders, the log files
              go overhere:</b></p>
          <p>mkdir /home/pi/log<br>
            mkdir /home/pi/tmp<br>
            <br>
          </p>
          <img src="img/tmp.png" alt="" width="135" height="218"><br>
          <br>
          <p><b><a href="#Less_Read_and_Writes_on_SD_Card">/tmp is a
                virtual folder</a><br>
            </b></p>
          <p><b><br>
              Compile decoders DFM-09/RS-41/M10/M20:</b><br>
          </p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;"><br>
            git clone https://github.com/rs1729/RS<br>
            cd RS/demod/mod<br>
            gcc -c demod_mod.c -w -O3<br>
            gcc -c bch_ecc_mod.c -w -O3<br>
            <br>
          </p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;">Compiling Mod
            DFM09/RS41<br>
            gcc rs41mod.c demod_mod.o bch_ecc_mod.o -lm -O3 -o rs41mod
            -w<br>
            gcc dfm09mod.c demod_mod.o -lm -O3 -o dfm09mod -w<br>
            <br>
            Compiling Mod M10/20"<br>
            gcc m10mod.c demod_mod.o -lm -O3 -o m10mod -w<br>
            sleep 1<br>
            gcc mXXmod.c demod_mod.o -lm -O3 -o mXXmod -w<br>
          </p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;"> Or any other you
            need.</p>
          <p style="color: rgb(0, 0, 0); font-family: &quot;Times New
            Roman&quot;; font-size: medium; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 400; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;"> You also <a
              href="https://github.com/rs1729/RS/tree/master/tools"
              target="_blank"><b>need pos2nmea.pl</b></a> (NMEA perl
            script) from folder RS/tools in the folder for GPS output!<br>
          </p>
          <b><a href="#RS-Decoder_with_APRS-Map_and_GPS2APRS.">It is
              also possible to use the NMEA output of the RS-Decoders
              and feed data into APRSMap via UDP.</a></b><br>
          <br>
          <b>Example of script's:</b><br>
          <br>
          <b>DFM06/09:<br>
          </b>
          <p>dfm.sh<br>
            #!/bin/bash<br>
            rtl_fm -p 0 -g 42.1 -M fm -F9 -s 15K -f402870000
            2&gt;/dev/null | sox -t raw -r 15k -e s -b 16 -c 1 - -r
            48000 -b 8 -t wav - lowpass 2600 2&gt;/dev/null | ./dfm09mod
            --dist -vv --ptu --auto 2&gt;&amp;1 | tee -a
            /home/pi/Log/dfm09_`date +%Y%m%d%H`Z.txt | ./pos2nmea.pl
            &gt; /tmp/virtualcom0<br>
            exit</p>
          <p>dfm_gps.sh</p>
          <p>#!/bin/bash<br>
            xfce4-terminal -T vp -e ./vp.sh&nbsp; --tab -T DFM -e
            ./dfm.sh<br>
            <br>
          </p>
          <p><img src="img/dfm.png" alt="" width="477" height="295"></p>
          <br>
          <b>Gqrx </b><b><b>DFM06/09</b>:<br>
            <br>
          </b>dfm_gqrx.sh<br>
          &nbsp;#!/bin/bash<br>
          sox -t alsa default -r 48000 -b 8 -t wav - lowpass 2600
          2&gt;/dev/null | ./dfm09mod --dist -v --ptu --auto 2&gt;&amp;1
          | tee -a /home/pi/Log/dfm09_`date +%Y%m%d%H`Z.txt |
          ./pos2nmea.pl &gt; /tmp/virtualcom0<br>
          exit<br>
          <p>dfm_gqrx_gps.sh<br>
            xfce4-terminal -T vp -e ./vp.sh --tab -T DFM -e
            ./dfm_gqrx.sh<br>
          </p>
          <br>
          <p><img src="img/menu.png" alt="" width="480" height="289">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <img src="img/dfm_raw.png" alt="" width="477" height="289"><br>
          </p>
          <br>
          <b>RS41:<br>
          </b> <br>
          rs41.sh<br>
          #!/bin/bash<br>
          rtl_fm -p 0 -g 49.6 -M fm -F9 -s 9K -f405300000 2&gt;/dev/null
          | sox -t raw -r 9k -e s -b 16 -c 1 - -r 48000 -b 8 -t wav -
          lowpass 2600 2&gt;/dev/null | ./rs41mod --ecc2 --crc -vx --ptu
          2&gt;&amp;1 | tee -a /home/pi/Log/rs41_`date +%Y%m%d%H`Z.txt |
          ./pos2nmea.pl &gt; /tmp/virtualcom0<br>
          exit<br>
          <br>
          rs41_gps.sh<br>
          #!/bin/sh<br>
          xfce4-terminal -T vp -e ./vp.sh --tab -T DeBilt -e
          ./rs41_bilt.sh<br>
          <br>
          <img src="img/rs41d.png" alt="" width="480" height="296"><br>
          <br>
          <b>Gqrx RS41:<br>
            <br>
          </b> rs41_gqrx.sh<br>
          #!/bin/bash<br>
          sox -t alsa default -r 48000 -b 8 -t wav - lowpass 2600
          2&gt;/dev/null | ./rs41mod --ecc2 --crc -vx --ptu 2&gt;&amp;1
          | tee -a /home/pi/Log/rs41_`date +%Y%m%d%H`Z.txt |
          ./pos2nmea.pl &gt; /tmp/virtualcom0<br>
          exit<br>
          <p>rs41_gqrx_gps.sh<br>
            #!/bin/sh<br>
            xfce4-terminal -T vp -e ./vp.sh --tab -T RS41 -e
            ./rs41_gqrx.sh<br>
          </p>
          <br>
          <img src="img/rs-sat.png" alt="" width="480" height="293"><br>
          <br>
          <b>Virtual COM Ports:</b><br>
          <p> <b>vp.sh</b><br>
          </p>
          <p>#!/bin/bash<br>
            <br>
            echo "Creating Virtual Com Port: 0 and 1"<br>
            <br>
            vcpath='/tmp'<br>
            socat -d -d pty,link=${vcpath}/virtualcom0,raw,echo=0
            pty,link=${vcpath}/virtualcom1,raw,b4800,echo=0 &amp;<br>
            socatpid=$!<br>
            echo "socat pid=$socatpid"<br>
            sleep 2<br>
            <br>
            trap "kill $socatpid &amp;&gt;/dev/null; exit 0" INT TERM
            EXIT<br>
            <br>
            echo "Start GPSD on Virtual Com Ports"<br>
            killall -q gpsd<br>
            gpsd -D2 -b -n -N ${vcpath}/virtualcom1<br>
            <br>
          </p>
          <p> <img src="img/vp1.png" alt="" width="480" height="294"> </p>
          <br>
          <p><b>Make permissions for COM ports:</b><br>
          </p>
          <p>Run ./vp1.sh so the virtual ports are accessible in /tmp
            for setting chown permissions.</p>
          <p><img src="img/ports_perm.png" alt="" width="467"
              height="216"><br>
          </p>
          <p> sudo chown -R pi:pi /tmp/virtualcom0<br>
            sudo chown -R pi:pi /tmp/virtualcom1<br>
            <br>
          </p>
          <p style="margin-bottom: 0in">As long as the socat (Terminal
            vp) is running, you have a pair of VPs open.</p>
          They are named virtualcom 0 and 1 so they stay static and no
          dev/pts/ number change. <br>
          <br>
          <b>What does it all mean.</b><br>
          <br>
          <b>rs41mod -h</b><br>
          rs41mod [options] audio.wav<br>
          options:<br>
          &nbsp;-v, -vx, -vv&nbsp; (info, aux, info/conf)<br>
          &nbsp;-r, --raw<br>
          &nbsp;-i, --invert<br>
          &nbsp;--ths &lt;x&gt;&nbsp;&nbsp;&nbsp; (peak threshold;
          default=0.7)<br>
          &nbsp;--iq0,2,3&nbsp;&nbsp;&nbsp; (IQ data)<br>
          <br>
          <b>dfm09mod -h</b><br>
          dfm09mod [options] audio.wav<br>
          options:<br>
          &nbsp;-v, -vv<br>
          &nbsp;-r, --raw<br>
          &nbsp;-i, --invert<br>
          &nbsp;--ecc&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (Hamming
          ECC)<br>
          &nbsp;--ths &lt;x&gt;&nbsp;&nbsp;&nbsp; (peak threshold;
          default=0.6)<br>
          &nbsp;--json&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (JSON output)<br>
          &nbsp;--ecc2 now also gives the output after each block how
          many bits the error correction has corrected. <br>
          &nbsp;--ptu temperature Info<br>
          &nbsp;--dist is like ecc, but only blocks that belong to the
          same frame are taken, i. if errors occur, the frame is
          discarded / Inversed used for DFM06/90<br>
          <br>
          <p> </p>
          <p></p>
          <h2><a name="Foxtrot_GPS_"></a>Foxtrot GPS<br>
          </h2>
          <p><br>
            <img src="img/Foxtrotgps3.png" alt="" width="480"
              height="294"> &nbsp; &nbsp; &nbsp;&nbsp; <img
              src="img/Foxtrotgps.png" alt="" width="480" height="293"><br>
            <br>
          </p>
          <p> </p>
          <p><b>sudo apt-get instal foxtrotgps</b><br>
          </p>
          <p>Will install FoxtrotGPS v1.21 from feed.<br>
            <br>
          </p>
          <p><b>For newer versions build from source:</b><br>
          </p>
          <p>Dependencies - <a
              href="https://www.foxtrotgps.org/build.html"
              target="_blank">https://www.foxtrotgps.org/build.html</a></p>
          <p>Download <a href="https://www.foxtrotgps.org/releases/"
              target="_blank">source</a> on FoxtrotGPS website.<br>
            &nbsp;</p>
          <p> <b>Insert extra Maps for FoxtrotGPS.</b><br>
          </p>
          Open FoxtrotGPS, goto Info Icon 3th screen, Map Types and
          select New, Insert:<br>
          <br>
          http://tile.memomaps.de/tilegen/%d/%d/%d.png
          <p><br>
          </p>
          <img src="img/Foxtrotgps2.png" alt="" width="509" height="368">
          <p><br>
          </p>
          <p>For Thunderforest maps sign up free at their <a
              href="https://www.thunderforest.com/" target="_blank">website</a>
            to get api-key and insert it into the links below:<br>
            <br>
          </p>
          <p><b>Example:</b><br>
          </p>
          <p>thunderforest_api_key = 123</p>
          <p>https://tile.thunderforest.com/pioneer/%d/%d/%d.png?apikey=123<br>
            https://tile.thunderforest.com/cycle/%d/%d/%d.png?apikey=123<br>
https://tile.thunderforest.com/transport/%d/%d/%d.png?apikey=123<br>
https://tile.thunderforest.com/landscape/%d/%d/%d.png?apikey=123<br>
https://tile.thunderforest.com/outdoors/%d/%d/%d.png?apikey=123<br>
https://tile.thunderforest.com/transport-dark/%d/%d/%d.png?apikey=123<br>
https://tile.thunderforest.com/spinal-map/%d/%d/%d.png?apikey=123<br>
https://tile.thunderforest.com/neighbourhood/%d/%d/%d.png?apikey=123<br>
https://tile.thunderforest.com/mobile-atlas/%d/%d/%d.png?apikey=123<br>
          </p>
          <h2><a name="Navit_"></a>Navit<br>
          </h2>
          <p><b><br>
              Install Navit.</b><br>
            sudo apt-get install navit<br>
            <br>
          </p>
          <p>It's <b>recommended</b> to follow this excellent guide
            about navit:<br>
          </p>
          <p><a
              href="http://ozzmaker.com/navigating-navit-raspberry-pi/"
              target="_blank">http://ozzmaker.com/navigating-navit-raspberry-pi/</a></p>
          <p><br>
            <img src="img/Navit.png" alt="" width="480" height="296"><br>
            <br>
            <a href="files/navit.tar.gz?raw=true">OSD for&nbsp; 3.5"&nbsp;
              480x320 resolution Display</a>.</p>
          <p>Put in pi/.navit folder.<br>
            <br>
          </p>
          <p><b>Download Offline Map's:</b><br>
          </p>
          <p>
            <meta http-equiv="content-type" content="text/html;
              charset=UTF-8">
            <a href="http://maps3.navit-project.org/">http://maps3.navit-project.org/</a>
          </p>
          <h2><a name="Gqrx_"></a>Gqrx<br>
          </h2>
          <p><br>
            Gqrx v2.11.5 is available on the Raspbian Buster feed.<br>
            Drivers included: Rtlsdr, Airspy, SDRPlay, HackRF, RFSpace,
            Funcube Dongle, Red Pitaya and SoapySDR (no plugins).</p>
          <p> <b>sudo apt-get install gqrx-sdr -y<br>
              <br>
            </b></p>
          <p>After that it is possible to update Gqrx from git:</p>
          <p><b>sudo apt-get install qt5-default libqt5svg5-dev
              libpulse-dev<br>
              <br>
              For command line builds:<br>
              <br>
            </b>git clone https://github.com/csete/gqrx.git<br>
            cd gqrx/<br>
            mkdir build &amp;&amp; cd build<br>
            cmake ..<br>
            make<br>
          </p>
          <p>Overwrite gqrx binary.<br>
            sudo cp gqrx /usr/bin<br>
            sudo chmod 755 /usr/bin/gqrx<br>
            <br>
          </p>
          <img src="img/Gqrx.png" alt="" width="480" height="294"><br>
          <p><br>
            <span style="color: rgb(26, 26, 27); font-family: &quot;Noto
              Sans&quot;, Arial, sans-serif; font-size: 14px;
              font-style: normal; font-variant-ligatures: normal;
              font-variant-caps: normal; font-weight: 400;
              letter-spacing: normal; orphans: 2; text-align: start;
              text-indent: 0px; text-transform: none; white-space:
              normal; widows: 2; word-spacing: 0px;
              -webkit-text-stroke-width: 0px; background-color: rgb(255,
              255, 255); text-decoration-style: initial;
              text-decoration-color: initial; display: inline
              !important; float: none;"><b>Run volk_profile from
                terminal</b>, wait for it to finish, then enjoy the
              performance boost.</span><br>
            <br>
          </p>
          If you are only interested in the FFT set Mode to Demod Off,
          this will greatly reduce the CPU load.<br>
          In most cases you can reduce the CPU load further by reducing
          the window size, sample rate, FFT rate and FFT size (try 2048
          at 10-15 Hz).<br>
          <br>
          <a href="files/Gqrx_Profile.tar.gz?raw=true">Download</a> Gqrx Profile
          for 3,5" LCD and some optimize settings.<br>
          Extract to home/pi/.config/gqrx/<br>
          <h2><a name="Virtual_Audio_Setup_"></a>Virtual Audio Setup<br>
          </h2>
          <br>
          <b>Some virtual audio can be setup: </b>
          <p>Adding this line to this file<b>
              ~/.config/pulse/default.pa:</b></p>
          <p>load-module module-null-sink sink_name=VBCable_A
            sink_properties=device.description="VBCable"</p>
          <br>
          Will always load the desired NULL sinks on starting the
          pulseaudio sound server.<br>
          Removing sinks that had been loaded by pactl or pacmd, i.e.
          without settings in our default.pa can most quickly done by <b>
            pulseaudio -k&nbsp; </b>
          <p>This command will kill the running pulseaudio instance, to
            instantaneously respawn it (in a default set up) using
            values defined in the default.pa.</p>
          <p><br>
            It is recommend disabling PulseAudio logging, as this seems
            to be a large user of CPU cycles.<br>
            <br>
            Edit /etc/pulse/daemon.conf<br>
            Now find "log-level" and change it to "log-level = error". <br>
            Remove the semi-colon on the log-level line too. Save and
            exit.<br>
            <br>
            ; log-target = auto<br>
            log-level = error<br>
            ; log-meta = no<br>
            You can now reload pulseaudio either by rebooting, or
            running "pulseaudio -k" at a command line.<br>
            <br>
          </p>
          <img src="img/PavuControl.png" alt="" width="480" height="290">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          <img src="img/PavuControl2.png" alt="" width="480"
            height="286"><br>
          <br>
          <b>Do not forget Gqrx Audio / PavuControl to select the
            Virtual audio!</b><br>
          <h2><a name="librtlsdr_errors_and_workarounds"></a>librtlsdr
            errors and workarounds<br>
          </h2>
          <br>
          Librtlsdr did not always play very nice with other SDR
          Software in Stretch.<br>
          In Buster it's a real <b>pain in the ass</b>, conflicting
          with many software...<br>
          <br>
          Things get worsens because many SDR programs follow a install
          script which off course installs drivers or even uninstall
          certain rtl-sdr libraries.<br>
          Gqrx is available on Busters feed, this will also install
          GNURadio, Soapy drivers librtlsdr* ect ect.<br>
          <br>
          This saves a lot of time and it runs smoother compared to Gqrx
          in Stretch.<br>
          But the libraries conflict with SondeFinder, and Qt-DAB.<br>
          <br>
          <b>Removing librtlsdr breaks gqrx..</b><br>
          <br>
          pi@raspberrypi:~ $ sudo apt purge librtlsdr*<br>
          Reading package lists... Done<br>
          The following packages were automatically installed and are no
          longer required:<br>
          Ect, ect..<br>
          The following packages will be REMOVED:<br>
          gqrx-sdr* gr-osmosdr* libgnuradio-osmosdr0.1.4*<br>
          librtlsdr-dev* librtlsdr0* soapysdr0.6-module-all*<br>
          soapysdr0.6-module-rtlsdr*<br>
          &nbsp; <br>
          <b>Dirty fix screwing dpkg..</b><br>
          <br>
          <b>sudo dpkg --purge --force-all librtlsdr0</b><br>
          <br>
          Open var/lib/dpkg/status<br>
          <p> <b>Insert:</b></p>
          <p> Package: librtlsdr0<br>
            Status: install ok installed<br>
            Priority: optional<br>
            Section: libs<br>
            Installed-Size: 93<br>
            Maintainer: A. Maitland Bottoms &lt;bottoms@debian.org&gt;<br>
            Architecture: armhf<br>
            Multi-Arch: same<br>
            Source: rtl-sdr<br>
            Version: 0.6-1+rpt1<br>
            Depends: libc6 (&gt;= 2.4), libusb-1.0-0 (&gt;= 2:1.0.21)<br>
            Description: Software defined radio receiver for Realtek
            RTL2832U (library)<br>
            &nbsp;rtl-sdr is a software defined radio (SDR) receiver
            software for certain<br>
            &nbsp;low-cost DVB-T/DAB(+) USB dongles based on the Realtek
            RTL2832U chip.<br>
            &nbsp;.<br>
            This package contains the shared library.<br>
            Homepage: http://sdr.osmocom.org/trac/wiki/rtl-sdr<br>
            <br>
          </p>
          <p><b>Save it.</b><br>
          </p>
          <p>Apt update will complain sometimes about librtlsdr0 when
            updating but assumes its installed.<br>
            No wierd side affects are noticed, just ignore it <b>Everything</b>
            (SF, QT, Gqrx ect) will run fine :)<br>
            <br>
          </p>
          <p><img src="img/Error.png" alt="" width="480" height="288"><br>
            <br>
          </p>
          <p>Same story for sudo apt-get remove rtl-sdr&nbsp; <b>&lt;&lt;--
              do not do this, it will break stuff!</b><br>
          </p>
          <p>Rtl-sdr-blog driver <a
href="file:///D:/Program%20Files/SDR/Setup/Website/Project/Raspberry_Buster/index.html#Install_RTL-SDR_USB_Drivers:_">overhere</a>
            is compatible with all SDR programs listed on this website.</p>
          Rtl-sdr-blog driver github has a <a
            href="https://github.com/rtlsdrblog/rtl-sdr-blog/commits/master"
            target="_blank">few commits</a> about "EEPROM flag to
          determine if direct sampling mode should be forced ON."<br>
          Resulting in conflicts with librtlsdr which<b> breaks</b>
          everything in this Buster SDR setup, <b>those commits are </b><b><a
href="https://github.com/happysat/rtl-sdr-blog/commits/master"
              target="_blank">reverted</a></b><b> in the driver listed
            on this <a
href="#Install_RTL-SDR_USB_Drivers:_">website</a>.<br>
            <br>
            <img src="img/spoken.jpg" alt="" width="314" height="200"><br>
          </b>
          <h2><a name="Auto-RX_"></a>Auto-RX<br>
          </h2>
          <a
            href="https://github.com/projecthorus/radiosonde_auto_rx/wiki"
            target="_blank"><img src="img/autorx.png" alt="" width="578"
              height="221" border="0"></a><br>
          <br>
          <a
            href="https://github.com/projecthorus/radiosonde_auto_rx/releases"
            target="_blank">Automatic Radiosonde Receiver Utilities.</a><br>
          Set of utilities ('auto_rx') based on rs1279's RS-Decoders
          codebase to allow automatic reception and uploading Radiosonde
          decoded data to HabHub and/or Radiosondy.<br>
          <br>
          <b>The following radiosonde types are supported:</b><br>
          <br>
          Vaisala RS92, RS41, Graw DFM06/DFM09/DFM17/PS-15, Meteomodem
          M10, Intermet iMet-1, iMet-4, Lockheed Martin LMS6 and Meisei
          iMS-100.<br>
          <br>
          <a href="https://github.com/projecthorus/chasemapper/"
            target="_blank">Chasemapper</a> is a mapping system designed
          specifically for chasing high-altitude weather balloons,
          intended to be run on Raspberry Pi's.<br>
          Accessable from a tablet or laptop computer via a web browser,
          providing live predictions of the balloon flight path during
          the flight calculated from GFS weather models.<br>
          <br>
          The primary purpose of chasemapper is to provide an
          easy-to-use mapping interface to help you as close as possible
          to the landing location of a high-altitude balloon payload.<br>
          Maps can also be served up from a offline local cache,
          allowing use without internet connectivity.<br>
          <br>
          <b>Refer to the Wiki for </b><b><a
              href="https://github.com/projecthorus/radiosonde_auto_rx/wiki"
              target="_blank">Auto-RX</a></b><b> and </b><b><a
              href="https://github.com/projecthorus/chasemapper/"
              target="_blank">Chasemapper</a></b><b> Installation.</b><br>
          <br>
          Auto-RX is intend to run as a service when Buster starts up
          and scan a range of white listed Frequencies.<br>
          The Auto-RX Menu Script will provide some useful handy options
          to make fast actions without editing system files or any other
          time consuming things.<br>
          <br>
          It's expected that Auto-RX with this script does <b>NOT</b>
          run as a <b>service</b>!<br>
          <br>
          <img src="img/auto_rx.jpg" alt="" width="1082" height="475"><br>
          <br>
          <b>Screen #1</b> Startup with some device info.<br>
          <b>Screen #2</b> and <b>#3</b> Menu with several
          pre-programmed frequencies, option to insert a manual
          frequency or the last one used, En(dis)able APRS/HabHub
          upload.<br>
          <br>
          &nbsp;<img src="img/type_freq.png" alt="" width="480"
            height="114"><br>
          <br>
          <b>Screen #4</b> Menu with clean exit on all running instants,
          Device info, View Station Config File and Show the GFS
          Prediction Model Date from Chasemapper.<br>
          <b>Screen #5</b> Chasemapper running with DFM09 (Sirf/Binary
          mode) GPS-Mouse and offline maps from FoxtrotGPS
          initialized.&nbsp; <br>
          <b>Screen #6</b> Auto-RX Scanning the frequency awaiting
          signal to start decoding. <br>
          <br>
          <img src="img/chase.jpg" alt="" width="986" height="623"><br>
          <br>
          Some Chasemapper examples in 3,5" LCD Full Screen with
          Chromium Browser webIF port :5001<br>
          Predictor screen, Auto-RX Menu script will determine and push
          the Burst Alt. and Descent rate data/info to Chasemapper
          config based on the choice of a pre-programmed Wx-station.<br>
          As Value's can be different for each station, after the Burst
          Chasemapper makes it's own calculations for a accurate as
          possible prediction. <br>
          <br>
          <b>Auto-RX and Chasemapper Scripts.</b><br>
          <br>
          Setup:<br>
          <br>
          First install Auto-RX and Chasemapper from Github.<br>
          Make sure Chasemapper folder is <b>inside</b> the Auto-RX
          folder. <br>
          Example:/home/pi/Radio/auto_rx/chasemapper and the Predict
          files installed into Chasemapper folder.<br>
          And <b>everything</b> is setup in <b>station.cfg</b> and <b>horusmapper.cfg</b>
          for Chasemapper.<br>
          &nbsp; <br>
          <a href="files/Auto-RX.tar.gz?raw=true">Download Auto-RX and
            Chasemapper Script</a><br>
          <br>
          Unpack Auto-RX.tar.gz move files to /home/pi/Radio/auto_rx<br>
          Station.cfg info can change if Auto-RX gets updated, the
          script read some value's from it..<br>
          Same for Chasemapper, horusmapper.cfg only Burst and Descent
          Rate value's are inserted.<br>
          <b>chmod 755</b> all scripts.<br>
          <br>
          Put icons in /usr/share/pixmaps<br>
          GPS mouse is also loaded in the scripts, edit/change (maybe
          the baudrate default 9600) or comment out.<br>
          <br>
          Auto-RX and Chasemapper log files are <a
            href="#Less_Read_and_Writes_on_SD_Card">redirected via
            symlinks</a> to a temp folder which runs in a virtual memory
          to make less SD writes as stated in fstab.<br>
          After program exit they are moved to /home/pi/Log/ for
          archive.<br>
          <br>
          <img src="img/tmp.png" alt="" width="135" height="218"><br>
          <br>
          <a href="#Less_Read_and_Writes_on_SD_Card"><b>The following
              symlinks are needed for writing logfiles:</b></a><br>
          <br>
          ln -s /home/pi/tmp/Auto-RX /home/pi/Radio/auto_rx/log<br>
          ln -s /home/pi/tmp/Auto-RX
          /home/pi/Radio/auto_rx/chasemapper/log_files<br>
          <br>
          <b>Start Auto-RX and Chasemapper with the shortcut on the
            Desktop.</b><br>
          <h2><a name="DxlAPRS_"></a>DxlAPRS<br>
          </h2>
          <p><br>
            DxlAPRS Chain program written by OE5DXL, it is possible to
            decode most types of probes used in Europe. <br>
            The data may be viewed locally on a map or passed on to APRS
            and / or Radiosondy Servers.<br>
            DxlAPRS can decode multiple Radiosondes simultaneously. <br>
            <br>
          </p>
          <p><b>The following radiosonde types are supported:<br>
              <br>
            </b> Vaisala RS92, RS41, Graw DFM06/DFM09/DFM17/PS-15,
            Meteomodem M10.<br>
          </p>
          DxlAPRS is normally started as a service when Buster starts up
          and begin auto scan preferred frequencies range.<br>
          DxlAPRS Menu Script will provide some useful handy options,
          start APRS-Map and Local GPS.<br>
          <br>
          It's expected that DxlAPRS with this script does <b>NOT</b>
          run as a <b>service</b>!<br>
          <br>
          <p><img src="img/dxl.jpg" alt="" width="1066" height="407"><br>
            <br>
          </p>
          <p><b>Screen #1</b> Startup with some device info.<br>
            <b>Screen #2</b> Menu with pre-programmed frequencies,
            insert a manual frequency, the last one used, edit sdr
            frequency List to custom, En(dis)able APRS upload, enter
            PPM.<br>
            <b>Screen #3</b>, <b>#4</b> and <b>#5</b> SondeUDP,&nbsp;
            Sondemod and UDPGate will show received data, including
            distance of received Radiosonde.<br>
            <b>Screen #6</b> GPS2APRS Tab, connected to Local GPS-Mouse
            to show position on APRS-Map.</p>
          <p><br>
            In running operational mode the <b>first tab</b> shows the
            DxlAPRS <b>SDR-Config menu</b> with a few options:<br>
            <br>
          </p>
          <img src="img/Dxl_Menu.png" alt="" width="480" height="292">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          <img src="img/Dxl_Menu2.png" alt="" width="480" height="290">
          <br>
          <p><br>
            During reception it's possible switching to <b>another
              single or multiple Frequency</b> or Custom Frequency list
            (<b>Remove # to make active</b>) without restarting.<br>
            <br>
          </p>
          <p><img src="img/freq.jpg" alt="" width="358" height="66"><br>
            <br>
            <img src="img/Freq_list.png" alt="" width="480" height="207"></p>
          <p><br>
          </p>
          <p>DxlAPRS uses rtl_tcp for its local connection.<br>
            For the ring buffers to work rtl_tcp parameter -b
            Blocksize=20 is removed from the script.<br>
            <br>
          </p>
          <p><img src="img/rtl_tcp.png" alt="" width="480" height="294">
            <br>
          </p>
          <p><br>
            UDPGate <b>Webinterface</b> on <b>127.0.0.1:14501</b><br>
            <br>
          </p>
          <p> </p>
          <p><img src="img/webif.png" alt="" width="480" height="271"><br>
          </p>
          <b><a href="files/DxlAPRS.tar.gz?raw=true">Download DxlAPRS</a></b><br>
          <br>
          This setup is intented to run only <b>1 SDR</b>.<br>
          <br>
          Unpack DxlAPRS.tar.gz to move files to /home/pi/Radio/<br>
          <b>sudo chmod 755</b><b> -R</b>&nbsp; /home/pi/Radio/DxlAPRS<br>
          <br>
          <b>Edit</b> <b>home/pi/Radio/dxlAPRS/config/userinfo.txt</b>
          for your call, location ppm and gain value's.<br>
          And <b>station_beacon.txt </b>the Lat/Lon of your position.<br>
          You can copy these value's later from APRSMap from
          home/pi/Radio/dxlAPRS/bin/aprsmap/aprsmap.cfg when setup.<br>
          <br>
          Put icons in /usr/share/pixmaps.<br>
          GPS mouse is also loaded in the scripts, <b>edit/change</b>
          home/pi/Radio/dxlAPRS/scripts/gps.sh (maybe the <b>baudrate</b>
          default 4800) or comment out.<br>
          <br>
          <b>Start DxlAPRS with the shortcut on the Desktop</b>, this
          will open the screens above and APRSMap.<br>
          <br>
          <b>For APRS-Map the same thing</b>, fill in <b>callsign</b>
          with optional SSID and <b>QTH Location</b> from the <b>Online
            Menu</b>.<br>
          Zoom to your QTH as far as you can 100% identify your home
          (zoom level &lt;16). <br>
          <br>
          Then open ONLINE - MY POSITION and point to your home. <br>
          While push and hold the SHIFT key click on your home. <br>
          The coordinates will be copied into the MY POSITION field,
          Just click OK to save them.<br>
          <br>
          DxlAPRS log files are <a
            href="#Less_Read_and_Writes_on_SD_Card">redirected via
            symlinks</a> to a temp folder which runs in a virtual memory
          to make less SD writes as stated in fstab.<br>
          After program exit they are moved to /home/pi/Log/ for
          archive.<br>
          <br>
          <img src="img/tmp.png" alt="" width="135" height="218"><br>
          <br>
          <a href="#Less_Read_and_Writes_on_SD_Card"><b>The following
              symlinks are needed for writing log files:</b></a><br>
          ln -s /home/pi/tmp/DxlAPRS /home/pi/Radio/dxlAPRS/log<br>
          <br>
          <b>Distance from the received radiosonde.<br>
            <br>
          </b>Sondeudp window shows the distance to the sonde,
          elevation, GPS deviation, etc.<br>
          An important feature is also the Overground feature, which
          must be activated extra, here we need -N, that is the height
          of <b>your location</b>.<br>
          The own coordinates -P in Maidenhead format and SRTM files. <br>
          <br>
          <b>Edit /home/pi/Radio/dxlAPRS/scripts/dxlaprs.sh<br>
            <br>
          </b> <b>Line 299:</b><br>
          -N 92 \&nbsp;&nbsp;&nbsp;<b> Edit to your height of location,
            which you can find out </b><b><a
              href="http://topocoding.com/" target="_blank">overhere.</a></b><br>
          <br>
          <b>Line </b><b>300:</b><br>
          <br>
          -P JO12XX34 \&nbsp; <b>Edit to you QTH Locator, which you can
            find </b><b><a href="https://k7fry.com/grid/"
              target="_blank">overhere.</a></b><br>
          <br>
          <b>Line 301:</b><br>
          <br>
          -S /home/pi -L AC=DFM09,70=DFM17 \&nbsp; <b>This is the path
            where WW15MGH.DAC file is (Allready set).</b><br>
          <br>
          <b>The Earth Gravitational Model </b><b><a
href="https://earth-info.nga.mil/GandG/wgs84/gravitymod/egm96/binary/binarygeoid.html"
              target="_blank">EGM96 file (WW15MGH.DAC)</a></b><b> is
            needed download and </b><b>copy it to / home/pi</b><b>.</b><br>
          <br>
          <b>Last thing is the </b><b><a
              href="https://wiki.openstreetmap.org/wiki/SRTM"
              target="_blank">STRM Files</a></b><b>.</b><br>
          <br>
          <b><a href="https://dds.cr.usgs.gov/srtm/version2_1/SRTM3/"
              target="_blank">Download the strm file for your latitude.</a></b><br>
          <b>Extract zip and place them in /home/pi/srtm1</b><br>
          <br>
          If everything is configured correctly then such values should
          be visible in the comment field from APRS and in SondeUDP
          window.<br>
          <br>
          <b>Build DxlAPRS from source</b>, needed Dependencies: <br>
          sudo apt-get install build-essential libx11-dev libxext-dev
          libpng-dev libjpeg-dev<br>
          git clone https://github.com/oe5hpm/dxlAPRS.git<br>
          cd dxlAPRS/src<br>
          make all<br>
          <br>
          <b>Pre-Build Binaries ready.</b><br>
          <a
href="http://dxlaprs.hamspirit.at/?fbclid=IwAR0ZuXHxGyk4hw01_tfS-IzljIDKVAiOUL5e4aqUUaOVq9a-RjuSiZVMGlw">http://dxlaprs.hamspirit.at/?fbclid=IwAR0ZuXHxGyk4hw01_tfS-IzljIDKVAiOUL5e4aqUUaOVq9a-RjuSiZVMGlw</a><br>
          <b><br>
          </b><b> Refer for News, Tips and tricks about DXL-Toolchain
            Installation to:</b><br>
          <br>
          <a
            href="https://sites.google.com/view/oe3jtb/tipps-und-tricks"
            target="_blank">https://sites.google.com/view/oe3jtb/tipps-und-tricks</a><br>
          <br>
          <a href="https://sites.google.com/view/oe3jtb/aktuelles">https://sites.google.com/view/oe3jtb/aktuelles</a><br>
          <br>
          <h2><a name="APRS-Map_"></a>APRS-Map<br>
          </h2>
          <br>
          APRS-Map displays the current Radiosonde Position and your own
          position (off course a GPS-Mouse is required) in Maps.<br>
          <br>
          <img src="img/aprsmap.png" alt="" width="482" height="347">&nbsp;
          <br>
          <br>
          <b>Change start view:</b><br>
          <br>
          Set the target area on the map.<br>
          Then click Zoom and with the Shift key pressed, left-click on
          this button:<br>
          <br>
          <img src="img/pos.png" alt="" width="193" height="167"><br>
          <br>
          The button is then called as the level (here: 11) and is used
          as a view at program start. <br>
          This view can also be called up with the "1" key. <br>
          <br>
          In the same way, the three buttons on the right work next to
          it.<br>
          With Shift and click on the respective button the current view
          is saved, only the click (or the digit) calls up this view.<br>
          <br>
          In response to these actions, there are brief messages at the
          top left. "View stored!" after saving and "Show One Symbol
          Off" after invoking a saved view. <br>
          <p> </p>
          <br>
          <p><img src="img/aprsmap2.png" alt="" width="482" height="292"><br>
            <br>
          </p>
          <p>Its possible to <b>use other map sources</b>, open and
            edit dxlAPRS\bin\aprsmap\maplist insert:<br>
            <br>
          </p>
          <p>tiles_osm&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;
            zxy&nbsp;&nbsp;&nbsp;&nbsp;
            png&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            http://tile.openstreetmap.org OSM Carto (Standard)<br>
            tiles_topo&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;
            zxy&nbsp; &nbsp; &nbsp;
            png&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            http://tile.opentopomap.org&nbsp; OpenTopoMap<br>
            tiles_topo2&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;
            zxy&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; png &nbsp; &nbsp;
            &nbsp;&nbsp; http://tile.memomaps.de/tilegen OpenTopoMap2<br>
            tiles_topplus&nbsp; &nbsp; &nbsp; zyx&nbsp;&nbsp;
            &nbsp;&nbsp; png&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            http://sgx.geodatenzentrum.de/wmts_topplus_open/tile/1.0.0/web/default/WEBMERCATOR
            TopPlusOpen<br>
            tiles_esrisat&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;
            zyx&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            jpg&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;
            http://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile&nbsp;
            ArcGIS ESRI Satellite World Imagery<br>
            tiles_transport &nbsp; zxy&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            png&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            http://tile.thunderforest.com/transport ?apikey=123&nbsp;
            Thunderforest Transport (requires API key)<br>
            tiles_landscape zxy&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            png&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            http://tile.thunderforest.com/landscape ?apikey=123
            Thunderforest Landscape (requires API key)<br>
            tiles_outdoors&nbsp;&nbsp; zxy&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            png&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            http://tile.thunderforest.com/outdoors ?apikey=123
            Thunderforest Outdoors (requires API key)<br>
            tiles_transport&nbsp;&nbsp;
            zxy&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            png&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            http://tile.thunderforest.com/transport ?apikey=123
            Thunderforest transport (requires API key)<br>
            tiles_mobile zxy png
            http://tile.thunderforest.com/mobile-atlas ?apikey=123
            Thunderforest mobile (requires API key)<br>
            tiles_transport-dark zxy png
            http://tile.thunderforest.com/transport-dark ?apikey=123
            Thunderforest transport-dark (requires API key)<br>
            <br>
          </p>
          <p><b>This must be changed in dxlAPRS\bin\aprsmap\aprsmap.cfg
              also:</b><br>
          </p>
          Map Names|1|tiles_topo2 0.25 78<br>
          Map Names|1|tiles_mobile 0.25 73<br>
          Map Names|1|tiles_osm 0.25 65<br>
          Map Names|1|tiles_topo 0.25 71<br>
          Map Names|1|tiles_topplus 0.25 61<br>
          Map Names|1|tiles_esrisat 0.25 98<br>
          Map Names|1|tiles_landscape 0.25 69<br>
          Map Names|1|tiles_transport 0.25 62<br>
          Map Names|1|tiles_outdoors 0.25 75<br>
          Map Names|1|tiles_transport-dark 0.25 94
          <p>The Map listed on top will be the <b>first one</b> to show
            up.<br>
          </p>
          <p>For Thunderforest maps <b>sign up free</b> at their <a
              href="https://www.thunderforest.com/" target="_blank">website</a>
            to get api-key and insert it into the links above.<br>
          </p>
          <p><br>
          </p>
          <p><img src="img/maps.png" alt="" width="480" height="295">
            &nbsp; &nbsp; <img src="img/bright_map.png" alt=""
              width="480" height="296"><br>
            <br>
          </p>
          <p>Maps can be selected in <b>Tools / Choose Maps</b>, and
            some adjustment options in <b>Config / Brightness.</b><br>
          </p>
          All Maps Tiles can be saved for <b>Offline</b> usage.<br>
          <br>
          <b>Note's:</b><br>
          Aprsmap has a setting that should not be used. Config, Map
          Parameter, Trackfilter - Leave it <b>unchecked</b>.!<br>
          <br>
          More about the regular functions and options from APRS-Map
          read the Wiki:<br>
          <a
            href="http://wiki.oevsv.at/index.php?title=DXL_-_APRSmap_englisch"
            target="_blank">http://wiki.oevsv.at/index.php?title=DXL_-_APRSmap_englisch</a><br>
          <h2><a name="GPS2APRS_"></a>GPS2APRS<br>
          </h2>
          <br>
          <b>Setup GPS:</b><br>
          <br>
          Make sure you have the right <b>Port number</b> and <b>Baudrate</b>
          which the GPS is connected to:<br>
          <br>
          <a href="https://github.com/happysat/DFM-09-Modification-to-GPS-Mouse" target="_blank">Modified
            DFM GPS</a> Script for - <a href="files/Gps.tar.gz?raw=true">Binary
            2 NMEA mode</a><br>
          <br>
          <b>dmesg | grep ttyUSB<br>
          </b><br>
          ./gps2aprs -t /dev/ttyUSB0:4800 -I CAR -i /k -D -0 30 -b 2 -v
          -r 127.0.0.1:9002<br>
          <br>
          gps2aprs -h<br>
          <br>
          &nbsp;-t
          &lt;tty&gt;:&lt;baud&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          (/dev/ttyUSB0:4800)<br>
          &nbsp;-I
          &lt;mycall&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          Mycall with SSID like NOCALL-15<br>
          &nbsp;-D&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          DAO Extension on for 20cm Resolution<br>
          &nbsp;-b
          &lt;s&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          Driving Beacon Time in Seconds (15)<br>
          &nbsp;-r
          &lt;x.x.x.x:destport&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Use
          AXUDP (to Soundmodem)<br>
          &nbsp;-v&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          Verbous-Mode<br>
          &nbsp;-i&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          Ballon /O, Car /&gt; -i /k<br>
          <br>
          <img src="img/gps.png" alt="" width="483" height="316"><br>
          <br>
          <b>Goto APRS-Map Config / Rf-Ports Tab: </b><br>
          <br>
          Check RF-Port 1 and make sure its
          UDP1(ip:send:listen)|1|127.0.0.1:9001:9002<br>
          And NMEA data from your local GPS-Mouse should roll in.<br>
          <br>
          The Car position should be Visible and every 30 Seconds
          updated.<br>
          In DxlAPRS gps start script is included and runs on start in
          tabbed terminal.<br>
          <h2><a name="RS-Decoder_with_APRS-Map._"></a>RS-Decoder with
            APRS-Map. </h2>
          <br>
          It is also possible to use the NMEA output of the RS-Decoders
          and feed data into APRSMap via UDP thru the Perl pos2aprs
          script.<br>
          -U UDP Ip and Port.<br>
          -d generates APRS frames with DAO (and thus finer position
          resolution).<br>
          -i&nbsp; Sonde ID E.g. i-Met.<br>
          <br>
          <b>POS2APRS:</b><br>
          <br>
          <a
          href="/files/RS_APRS.tar.gz?raw=true">Download
            pos2aprs script's.</a><br>
          <br>
          <b>For DFM:<br>
          </b><br>
          <b><b>rtl_fm:</b></b><br>
          <br>
          rtl_fm -p 0 -g 49.6 -M fm -F9 -s 15K -f402870000
          2&gt;/dev/null | sox -t raw -r 15k -e s -b 16 -c 1 - -r 48000
          -b 8 -t wav - lowpass 2600 2&gt;/dev/null | ./dfm09mod --dist
          -v --ptu --auto 2&gt;&amp;1 | ./pos2aprs.pl RASPI 0
          "Radiosonde" -d -U 127.0.0.1:9002 &gt; /dev/null<br>
          <br>
          <b><b>Gqrx:</b></b><br>
          <br>
          sox -t alsa default -t wav - 2&gt;/dev/null | ./dfm09mod
          --dist -v --ptu --auto 2&gt;&amp;1 | ./pos2aprs.pl RASPI 0
          "Radiosonde" -d -U 127.0.0.1:9002 &gt; /dev/null<br>
          <br>
          <b>For RS-41:<br>
          </b><br>
          <b><b>rtl_fm:</b></b><br>
          <br>
          rtl_fm -p -1 -g 49.6 -M fm -F9 -s 9K -f403500000
          2&gt;/dev/null | sox -t raw -r 9k -e s -b 16 -c 1 - -r 48000
          -b 8 -t wav - lowpass 2600 2&gt;/dev/null | ./rs41mod --ecc2
          --crc -vx --ptu 2&gt;&amp;1 | ./pos2aprs.pl RASPI 0
          "Radiosonde" -d -U 127.0.0.1:9002 &gt; /dev/null<br>
          <br>
          <b>Gqrx:</b><br>
          <br>
          sox -t alsa default -t wav - 2&gt;/dev/null | ./rs41mod --ecc2
          --crc -vx --ptu 2&gt;&amp;1 | ./pos2aprs.pl RASPI 0
          "Radiosonde" -d -U 127.0.0.1:9002<b> </b>&gt; /dev/null<br>
          <br>
          <b>For i-Met4:<br>
          </b><br>
          <b><b>rtl_fm:</b></b><br>
          <br>
          rtl_fm -p -1 -g 49.6 -M fm -F9 -s 9K -f403000000
          2&gt;/dev/null | sox -t raw -r 9k -e s -b 16 -c 1 - -r 48000
          -b 8 -t wav - lowpass 2600 2&gt;/dev/null | imet1rsb
          2&gt;&amp;1 | ./pos2aprs.pl RASPI 0 "Radiosonde" i-Met4 -d -U
          127.0.0.1:9002 &gt; /dev/null<br>
          <br>
          <b>Gqrx:</b><br>
          <br>
          sox -t alsa default -t wav - 2&gt;/dev/null | ./imet1rsb
          2&gt;&amp;1 | ./pos2aprs.pl RASPI 0 "Radiosonde" i-Met4 -d -U
          127.0.0.1:9002<b> </b>&gt; /dev/null<br>
          <br>
          <br>
          The paths to the programs and the exact parameters must of
          course be adjusted accordingly!<br>
          <br>
          <b>Goto APRS-Map Config / Rf-Ports Tab: <br>
            <br>
          </b> <img src="img/RF-Port.png" alt="" width="555"
            height="291"><br>
          <br>
          Check RF-Port 1 in APRS-Map and make sure its
          UDP1(ip:send:listen)|1|127.0.0.1:9001:9002<br>
          And NMEA data from rs-decoder should roll in:<br>
          <br>
          <img src="img/rs_aprs.jpg" alt="" width="587" height="312"><br>
          <br>
          <h2><a name="SondeFinder_"></a>SondeFinder<br>
          </h2>
          <br>
          This program can decode radiosondes: RS41, DFM, PilotSonde,
          iMet and M10.<br>
          Interface via touch screen, optional GPS input.<br>
          <br>
          <img src="img/sf.png" alt="" width="481" height="320"><br>
          <br>
          <b>Installation </b><b><a
href="http://www.om3bc.com/docs/SF/sondefinder_en.html?fbclid=IwAR30axg6sGTKY4N37iuPTq3RLEiXqEczKUx51K8DYWEuWM1Uz8JGD2ofh1I"
              target="_blank">instructions</a></b><b>.</b><br>
          <br>
          <b>Note:</b><br>
          <br>
          Full installer from www.om3bc.com/docs/SF/install_all.sh will
          <b>overwrite RTL-SDR drivers, not recommend on Buster.</b><br>
          <b>Manual install:</b><br>
          <br>
          sudo apt-get install cmake build-essential python-pip
          libusb-1.0-0-dev python-numpy git pandoc sox -y<br>
          sudo pip install pyrtlsdr<br>
          <br>
          sudo wget www.om3bc.com/docs/SF/sondefinder.tar.gz<br>
          tar -zxf sondefinder.tar.gz<br>
          <br>
          cd Desktop<br>
          cp sondefinder.desktop /home/pi/Desktop<br>
          <br>
          If the program is properly installed, a SondeFinder icon must
          appear on the the Desktop.<br>
          <br>
          <img src="img/sf_gps.png" alt="" width="480" height="316"><br>
          <br>
          GPS Connection, use USB GPS Mouse, and set proper Baudrate
          4800.<br>
          <h2><a name="Multi-SDR_Script"></a>Multi-SDR Script</h2>
          <br>
          <img src="img/Multi-sdr.png" alt="" width="373" height="240">
          &nbsp; &nbsp; <img src="img/Multi-sdr2.png" alt=""
            width="381" height="238"><br>
          <br>
          <b>Multi-SDR</b> is a script that bundle several SDR
          applications and their command line's.<br>
          Included are pre-compiled binaries: DumpVDL2, Retrogram,
          rtl_433, RTTY-Decoder, Multi-mon, Qt-DAB and Vortrack.<br>
          <br>
          <b><a href="files/MultiSDR.tar.gz?raw=true">Download Binaries and
              Script.</a></b><br>
          &nbsp;<br>
          chmod 755 the script, edit to your own needs.<br>
          Maybe not all Binaries will run without Dependencies,<b> read</b>
          <b>github author site</b> which dependencies are needed.<br>
          <br>
          <h2><a name="Direwolf_"></a>Direwolf<br>
          </h2>
          Dire Wolf is a software "soundcard" AX.25 packet modem/TNC and
          APRS encoder/decoder. <br>
          It can be used stand-alone to observe APRS traffic, as a
          tracker, digipeater, APRStt gateway, or Internet Gateway
          (IGate). <br>
          For more information, look at <a
            href="https://github.com/wb2osz/direwolf/blob/dev/doc/README.md"
            target="_blank">https://github.com/wb2osz/direwolf/blob/dev/doc/README.md</a><br>
          <br>
          <b>Optional Requirements:</b><br>
          sudo apt-get install libudev-dev libhamlib-dev libasound2-dev<br>
          <br>
          git clone https://github.com/wb2osz/direwolf.git<br>
          cd direwolf<br>
          git checkout dev<br>
          mkdir build &amp;&amp; cd build<br>
          cmake ..<br>
          make<br>
          make install<br>
          make install-conf<br>
          <br>
          <b>Examples:</b><br>
          <br>
          <b>RS-41 Modified APRS 70CM:</b><br>
          <br>
          rtl_fm -p -1 -g 29.6 -f 432500000 - | direwolf -c
          /home/pi/Radio/Direwolf/sdr-1200bps.conf -r 24000 -D 1 - <br>
          <br>
          <b>Terrestrial APRS 2 Mtr:</b><br>
          &nbsp;<br>
          rtl_fm -p -1 -g 29.6 -f 144800000 - | direwolf -c
          /home/pi/Radio/Direwolf/sdr-1200bps.conf -r 24000 -D 1 -<br>
          <br>
          <b>ISS APRS 2Mtr</b><b>:</b><br>
          &nbsp; <br>
          rtl_fm -p -1 -g 29.6 -f 145825000 - | direwolf -c
          /home/pi/Radio/Direwolf/sdr-1200bps.conf -r 24000 -D 1 -&nbsp;
          <br>
          <br>
          sdr-1200bps.conf:<br>
          <br>
          ACHANNELS 1<br>
          ADEVICE null null<br>
          CHANNEL 0<br>
          <br>
          MODEM 1200<br>
          <br>
          AGWPORT 8000<br>
          KISSPORT 8001<br>
          <br>
          IGFILTER m/700<br>
          IGTXLIMIT 6 10<br>
          <h2><a name="Dump_VDL2_"></a>Dump VDL2<br>
          </h2>
          Dumpvdl2 is a VDL Mode 2 message decoder and protocol
          analyzer.<br>
          <br>
          <img src="img/vdl2.png" alt="" width="480" height="296"><br>
          <br>
          ./dumpvdl2 --rtlsdr 0 --gain 29.6 --correction 0 136725000
          136775000 136875000 136975000 2&gt;&amp;1 | tee
          /home/pi/tmp/vdl2_`date +%Y%m%d%H`.txt<br>
          <br>
          <a href="https://github.com/szpajder/dumpvdl2" target="_blank">https://github.com/szpajder/dumpvdl2</a><br>
          <h2><a name="FM-Transmitter_"></a>FM-Transmitter<br>
          </h2>
          <br>
          Use Raspberry Pi as FM transmitter, works on every Raspberry
          Pi board.<br>
          <p><a href="https://github.com/markondej/fm_transmitter"
              target="_blank">https://github.com/markondej/fm_transmitter</a><br>
            <br>
            This project uses the general clock output to produce
            frequency modulated radio communication.<br>
            The radiofrequency signal is emitted on GPIO 4 (pin 7 on
            header P1).<br>
            <br>
            <b>How to use it</b><br>
            To use this project You will have to build executable. <br>
            <b>First, clone this repository, then use "make" command as
              shown below:</b><br>
            <br>
            git clone https://github.com/markondej/fm_transmitter<br>
            cd fm_transmitter<br>
            make</p>
          <p> After successful build You can start transmitting by
            executing "fm_transmitter" program:<br>
            <br>
            sudo ./fm_transmitter -f 88.9 acoustic_guitar_duet.wav</p>
          sox -t alsa default -r 48000 -c 1 -b 16 -t wav - | sudo
          ./fm_transmitter -f 88.9 -<br>
          <p><br>
            Connect 20 - 40 cm plain wire to Raspberry Pi's GPIO 4,
            means Pin 7 of the GPIO header (header P1). <br>
            This acts as the antenna.<br>
            The optimal length of the wire depends the frequency you
            want to transmit, but it works with a few centimeters for
            local testing.</p>
          <p><br>
          </p>
          <p><b>Pinout of the Pi:</b><br>
          </p>
          <p>sudo apt-get install python3-gpiozero python-gpiozero -y <br>
            <br>
          </p>
          <img src="img/pinout.png" alt="" width="256" height="312"><br>
          <br>
          Terminal: type <b>pinout</b><br>
          <h2><a name="HeatMap_"></a>HeatMap<br>
          </h2>
          Heatmap:<br>
          <br>
          <img src="img/heatmap2.png" alt="" width="480" height="97"><br>
          <br>
          rtl-gopow, Render tables from rtl_power to a nice heat map.<br>
          <br>
          <img src="img/Heatmap.png" alt="" width="820" height="245"><br>
          <br>
          rtl_power -f 400M:450M:8k -p 0 -g 29.6 -i 10 -e 60m -d 0 &gt;
          /home/pi/tmp/$(date +%Y-%m-%d_%H-%M)_400-450MHz_8k.csv<br>
          ./gopow -i /home/pi/tmp/*.csv<br>
          <br>
          This will perform a scan over the frequency range of
          400-450MHz range 5kHz in 60 minutes&nbsp; -e 1h / 60m<br>
          -p =ppm -g = gain -i = interval -e = duration -d = dongle<br>
          <br>
          ./gopow -i *.csv<br>
          <br>
          <a href="https://github.com/dhogborg/rtl-gopow"
            target="_blank">https://github.com/dhogborg/rtl-gopow</a><br>
          <h2><a name="Multimon_"></a>Multimon<br>
          </h2>
          <br>
          <a href="https://github.com/EliasOenal/multimon-ng"
            target="_blank">Multimon-ng</a> is the successor of multimon
          and decodes the following digital transmission modes:<br>
          POCSAG, FLEX, AFSK, DTMF, MORSE CW and many more.<br>
          <br>
          <img src="img/aprs.png" alt="" width="480" height="296">
          &nbsp; &nbsp; <img src="img/Flex.png" alt="" width="480"
            height="295">&nbsp;&nbsp;&nbsp;&nbsp; <br>
          <br>
          <img src="img/pocsag.png" alt="" width="480" height="296">&nbsp;&nbsp;&nbsp;&nbsp;
          <img src="img/CW.png" alt="" width="480" height="295"><br>
          <br>
          <br>
          <b>Example AX-25, Flex, Pocsag and Morse:</b><br>
          <br>
          rtl_fm -p -1 -g 29.6 -f 432500000 -s 22050 - | multimon-ng -a
          AFSK1200 -t raw /dev/stdin 2&gt;&amp;1 | tee
          /home/pi/tmp/ax25_`date +%Y%m%d%H`.txt <br>
          <br>
          rtl_fm -f 169.65M -M fm -s 22050 -p 0 -g 29.6 | multimon-ng -a
          FLEX -t raw /dev/stdin 2&gt;&amp;1 | tee
          /home/pi/tmp/C2000_`date +%Y%m%d%H`.txt <br>
          <br>
          rtl_fm -p 0 -g 29.6 -f 172.45M -s 22050 - | multimon-ng -a
          POCSAG1200 -t raw /dev/stdin 2&gt;&amp;1 | tee
          /home/pi/tmp/POCSAG_`date +%Y%m%d%H`.txt<br>
          <br>
          rtl_fm -M usb -p 0 -g 29.6 -f 432650000 -s 22050 - |
          multimon-ng -a MORSE_CW -t raw /dev/stdin 2&gt;&amp;1 | tee
          /home/pi/tmp/CW_`date +%Y%m%d%H`.txt<br>
          <br>
          git clone https://github.com/EliasOenal/multimon-ng.git<br>
          cd multimon-ng<br>
          mkdir build &amp;&amp; cd build<br>
          cmake ..<br>
          make<br>
          <br>
          <h2><a name="Qt-DAB_"></a>Qt-DAB<br>
          </h2>
          Very good DAB Receiver, all info <a
            href="https://github.com/JvanKatwijk/qt-dab#widgets-and-scopes"
            target="_blank">overhere</a>.<br>
          <br>
          <img src="img/dab_sdr.png" alt="" width="131" height="229">
          &nbsp; &nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <img
            src="img/Qt-Dab.png" alt="" width="480" height="314"><br>
          <br>
          Selecting upmix as audio source did work on the audio jack of
          the Pi. &nbsp;
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <br>
          <br>
          <img src="img/dab_motd.png" alt="" width="324" height="237">&nbsp;
          &nbsp; &nbsp; &nbsp; <img src="img/dab_spectrum.png" alt=""
            width="480" height="237"><br>
          <br>
          <b>Appimage from Stretch do not work on Buster, so build from
            source:</b><br>
          <br>
          sudo apt-get update<br>
          sudo apt-get install git cmake qt5-qmake build-essential g++
          libsndfile1-dev qt5-default libfftw3-dev portaudio19-dev<br>
          sudo apt-get install libfaad-dev zlib1g-dev rtl-sdr
          libusb-1.0-0-dev mesa-common-dev libgl1-mesa-dev
          libqt5opengl5-dev libsamplerate0-dev libqwt-qt5-dev
          qtbase5-dev<br>
          <br>
          git clone https://github.com/JvanKatwijk/qt-dab.git<br>
          cd qt-dab<br>
          You can <a
href="https://github.com/JvanKatwijk/qt-dab#configuring-using-the-qt-dabpro-file"
            target="_blank">select which devices</a> will have support
          for Qt-DAB in qt-dab.pro file.<br>
          qmake qt-dab.pro<br>
          make<br>
          <br>
          cd linux-bin<br>
          mv qt-dab* qt-dab<br>
          sudo cp qt-dab /usr/local/bin<br>
          sudo chmod 755 /usr/local/bin/qt-dab<br>
          <br>
          qt-dab in terminal to run.<br>
          <br>
          Shortcut:<br>
          <br>
          Qt-DAB.desktop<br>
          <br>
          [Desktop Entry]<br>
          Name=Qt-DAB<br>
          Exec=qt-dab<br>
          Terminal=false<br>
          Type=Application<br>
          Icon=/usr/share/pixmaps/qt-dab.png<br>
          Categories=GTK;Utility;<br>
          <br>
          <a href="files/Qt-DAB.tar.?raw=true"><b>Download pre-compiled Qt-DAB
              Binary</b></a><br>
          <br>
          <b>For Qt-DAB Binary only:</b><br>
          sudo apt-get install libfaad-dev -y<br>
          <h2><a name="Retrogram_"></a>Retrogram<br>
          </h2>
          Retrogram, Spectrum analyzer on your terminal/ssh console with
          ASCII art ~ RTLSDR<br>
          <br>
          <img src="img/retrogram.png" alt="" width="480" height="295"><br>
          <br>
          <b>Example:</b><br>
          retrogram --rate 1.4e6 --freq 403.5e6 --step 1e5 --gain 32<br>
          <br>
          <b>* Center Frequency &nbsp;&nbsp;&nbsp; using keys [f-F] </b><b><br>
          </b><b>* Sampling rate&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;
            using keys [r-R]</b><b><br>
          </b><b>* Gain &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;
            &nbsp;&nbsp; &nbsp;&nbsp;&nbsp; using keys [g-G]</b><b><br>
          </b><b>* Reference level&nbsp; &nbsp;&nbsp;&nbsp; using keys
            [l-L] </b><b><br>
          </b><b>* Dynamic Range&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;
            using keys [d-D]</b><b><br>
          </b><b>* Frame rate&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            &nbsp;&nbsp;&nbsp; using keys [s-S]</b><b><br>
          </b><b>* Tuning step&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;
            &nbsp;&nbsp;&nbsp; using keys [t-T]</b><b><br>
          </b><b>* Hide/Show Controls &nbsp;&nbsp;&nbsp; using keys
            [c-C]</b><b><br>
          </b><b>* Quit program&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;
            using keys [q-Q]</b><br>
          <br>
          <a href="https://github.com/r4d10n/retrogram-rtlsdr">https://github.com/r4d10n/retrogram-rtlsdr</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          <br>
          <h2><a name="RTL_433_"></a>RTL_433<br>
          </h2>
          RTL_433, Program to decode traffic from Devices that are
          broadcasting on 433.9 MHz like temperature sensors.<br>
          <br>
          <img src="img/rtl_433.png" alt="" width="480" height="296"><br>
          <br>
          <b>Example:</b><br>
          rtl_433 -G -p 0 -g 29.6 -f 433956000 -f 433948000 -f 434035000
          -f 433960000 -f 433972000 -f 433912000 -f 433875000 -f
          433920000 -f 433947000 -f 433757000 -H 20 2&gt;&amp;1 | tee
          /home/pi/tmp/433_`date +%Y%m%d%H`.txt<br>
          <br>
          <a href="https://github.com/merbanan/rtl_433" target="_blank">https://github.com/merbanan/rtl_433</a><br>
          <h2><a name="rtl_tcp_and_Spyserver_"></a>rtl_tcp and Spyserver<br>
          </h2>
          rtl_tcp, Spyserver and USB-Reset Menu.<br>
          <br>
          <img src="img/rtl_tcp_menu.png" alt="" width="480"
            height="287"><br>
          <br>
          <b>Option #1</b> starts a rtl_tcp instance.<br>
          <br>
          <img src="img/spyserver.png" alt="" width="480" height="144"><br>
          <br>
          <b>Option #2</b> Starts Spyserver.<br>
          <br>
          <a href="https://airspy.com/?ddownload=4247" target="_blank">Download
            SPY Server</a> – SDR Server for 32bit ARM boards.<br>
          <br>
          Airspy R0, R2, Mini, Airspy HF+ and RTL-SDR can be used as a
          high performance SDR receiver capable of streaming separate
          chunks of the spectrum to multiple clients over the LAN or the
          Internet.<br>
          This build can be used with Raspberry Pi.<br>
          <br>
          <b>Option #3</b> Does Reset the SDR device when it hangs, so
          you do not need to reboot.<br>
          <br>
          <b>Check ID and Device</b> <b>index</b> in script to match
          yours with lsusb command in terminal.<br>
          Also <b>change</b> in rtl_tcp.sh <b>your IP-adres</b> it
          currently set to rtl_tcp -a 127.0.0.1 which does not work on
          outside connections..! <br>
          <br>
          <a href="files/rtl_tcp_spyserver.tar.gz?raw=true"><b>Download rtl_tcp
              and Spyserver script</b></a><br>
          <h2><a name="RTTY-Decoder_"></a>RTTY-Decoder<br>
          </h2>
          RTTY Decoder<br>
          <br>
          <img src="img/rtty.png" alt="" width="480" height="296"><br>
          <br>
          This program expects 16-bit, signed, single-channel audio
          samples on stdin and outputs the decoded text to stdout.<br>
          Debug messages are output to stderr.<br>
          <br>
          <b>Usage: ./rtty &lt;sample rate&gt; &lt;carrier frequency&gt;
            &lt;baud rate&gt; &lt;deviation&gt;</b><br>
          <br>
          <b>Examples:</b><br>
          ./rtty 48000 1000 45 170 can be used for amateur RTTY
          transmissions, while<br>
          ./rtty 48000 1000 50 -450 would be useful for demodulating
          Deutscher Wetterdienst's RTTY broadcasts.<br>
          rtl_fm -M usb -p 0 -g 49.6 -f 432800000 -s 48000 - | ./rtty
          48000 1400 75 570 /dev/stdin&nbsp; would decode Hab Amateur
          RTTY broadcasts.<br>
          <br>
          <b>Compile with: gcc -O2 -Wall -Wextra rtty.c -o rtty -lm</b><br>
          <br>
          <a href="https://gitlab.com/snippets/1812596" target="_blank">https://gitlab.com/snippets/1812596</a><br>
          <h2><a name="Vor-Track_"></a>Vor-Track<br>
          </h2>
          Vortrack<br>
          A simple VOR receiver git the radial in degree from the VOR.<br>
          <br>
          <img src="img/vor_track.png" alt="" width="480" height="295"><br>
          <br>
          <b>Example:</b><br>
          vortrack -p 0 -g 29.6 109.25 <br>
          <br>
          <a href="https://github.com/TLeconte/vortrack" target="_blank">https://github.com/TLeconte/vortrack</a><br>
          <h2><a name="OpenWebRX_"></a>OpenWebRX<br>
          </h2>
          <br>
          <a href="https://www.openwebrx.de" target="_blank">OpenWebRX</a>
          is a multi-user SDR receiver that can be operated from any web
          browser without the need for any additional client software. <br>
          <br>
          <img src="img/OpenWebRX.jpg" alt="" width="435" height="256"><br>
          <br>
          It is the ideal solution to provide access to the HF spectrum
          at your location of choice to a wide audience. <br>
          All you need is a computer, an SDR device and network access.<br>
          <br>
          <a href="https://github.com/jketterl/openwebrx"
            target="_blank">https://github.com/jketterl/openwebrx</a><br>
          <a
href="https://github.com/jketterl/openwebrx/wiki/Manual-Package-installation-%28including-digital-voice%29"
            target="_blank">https://github.com/jketterl/openwebrx/wiki/Manual-Package-installation-(including-digital-voice)</a><br>
          <br>
          Decoding RS41 sondes  in  combination with OpenWebRX 1.1.0 and
          1.2.0 will fail without a small patch in de source code.<br>
          <br>
          To filter the CTCSS signal in the NFM section de-emphasis is enabled by purpose.<br>
          <br>
          For decoding the RS41 signal the full  audio spectrum is needed from  0 herz.<br>
          <br>
          The most ideal option is to get an option in OpenWebRX to enable
          or disable the de-emphasis but at this moment it needs to be done in the code. <br>
          <br>
          Older versions prior OpenWebRX 1.2.0 Edit config_webrx.py:<br>
          <br>
          Change, audio_compression="none"<br>
          <br>
          Rule 85 in csdr.py change:<br>
          <br>
          self.low_cut = -5000<br>
          self.high_cut = 5000<br>
          <br>
          Rule 182<br>
          Comment out #&nbsp; "csdr deemphasis_nfm_ff {audio_rate}",<br>
          <br>
          Radiosonde decoding programs should work know.<br>
          <br>      
          Patching OpenWebRX 1.2.0 for RS41 <br>
          <br>
          copy /lib/python3/dist-packages/csdr/chain/analog.py for backup<br>
          edit /lib/python3/dist-packages/csdr/chain/analog.py 
          jump to line 29
          add a # in front of the NfmDeemphasis(sampleRate),
          and save the file 
          restart OpenWebRX systemctl restart openwebrx<br>
          <h2><a name="RaspAP_"></a>RaspAP<br>
          </h2>
          <br>
          A simple, responsive web interface to control wifi, hostapd
          and related services on the Raspberry Pi.<br>
          <b>Used to set the Pi as a WiFi Access-point for clients
            connecting to various WebInterfaces E.g Auto-RX,
            Chasemapper, DxlAPRS and RPi-Monitor.</b><br>
          <br>
          <a href="https://github.com/billz/raspap-webgui"
            target="_blank"><img src="img/raspap.png" alt="" width="357"
              height="233" border="0"></a><br>
          <br>
          <b><a
              href="https://github.com/billz/raspap-webgui#quick-installer"
              target="_blank">Install RaspAP</a></b><br>
          &nbsp;<br>
          <b>Update RaspAP</b> - <a
            href="https://github.com/billz/raspap-webgui/wiki/FAQs#upgrade"
            target="_blank">https://github.com/billz/raspap-webgui/wiki/FAQs#upgrade</a><br>
          <br>
          <p><b>Configure alternate port for RaspAP's web service:</b><br>
            Edit /etc/lighttpd/lighttpd.conf and change the following
            line:<br>
            server.port&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            = 8080<br>
            <br>
            <b>sudo systemctl restart lighttpd.service<br>
            </b></p>
          <h2><a name="RPi-Monitor_"></a>RPi-Monitor<br>
          </h2>
          <br>
          <img src="img/RPI-Mon.png" alt="" width="463" height="299"><br>
          <p>RPI-Monitor, looks abandon project but<b> works in Buster</b>
            after a few tweaks:<br>
          </p>
          <p>sudo apt-get install dirmngr<br>
            sudo apt-key adv --recv-keys --keyserver
            keyserver.ubuntu.com 2C0D3C0F<br>
            sudo wget http://goo.gl/vewCLL -O
            /etc/apt/sources.list.d/rpimonitor.list<br>
            sudo apt-get update<br>
            sudo apt-get install rpimonitor<br>
            sudo /etc/init.d/rpimonitor update<br>
          </p>
          <p><br>
            <b>Remove RPi-Monitor repository:</b><br>
            Remove PPAs by deleting the .list files from
            /etc/apt/sources.list.d directory.<br>
            <b>sudo apt-key list</b><br>
          </p>
          <p>Find RPI-Monitor PPA name and key and remove it:<br>
            It is the last 8 characters of the long hex.<br>
          </p>
          <p><b>sudo apt-key del &lt;key&gt;</b><br>
            <b><br>
            </b><b> </b></p>
          <b> </b>
          <p><b>Edit the file /etc/rpimonitor/template/network.conf</b><br>
            <br>
            a. Comment those lines you want to left out (eg "To activate
            network monitoring ..." by inserting a # in front of the
            line.<br>
            b. Comment out those lines you want to view (eg
            "web.status.1.content.8.line.1="Ethernet Sent... ") by
            deleting the # in front of the line.<br>
            <br>
            <b>Restart the service by executing the following command:</b><br>
            sudo service rpimonitor restart<br>
            <br>
          </p>
          <p><b>After reboot RPI-Monitor will not work on Buster fix:</b><br>
            To add the delay to the startup script, edit rpimonitor (<b>sudo
              nano /etc/init.d/rpimonitor</b>). <br>
          </p>
          Add the instruction "<b>sleep 10</b>" immediately before the
          "start" instruction in the case structure at the end of the
          program. <br>
          This will be immediately after<b> line 93</b> in the current
          release.<br>
          &nbsp;<br>
          After editing, the section should look like this:<br>
          <br>
          case "$1" in<br>
          &nbsp;&nbsp;&nbsp; start)<br>
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; sleep 10<br>
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; start
          <p> </p>
          <p> </p>
          <h2><a name="Tweaks_"></a>Tweaks<br>
          </h2>
          <br>
          <b>Faster Startup:<br>
          </b>Open Raspberry Pi Configuration<br>
          <br>
          <img src="img/no_wait.png" alt="" width="399" height="243"><br>
          <br>
          Uncheck wait network.<br>
          <br>
          <b>Open Folder As Root in Pcmanfm Filemanger:</b><br>
          <p><br>
            <img src="img/Root.png" alt="" width="477" height="313"></p>
          <p><br>
            <b><a href="files/file-manager.tar.gz?raw=true">Download Open Folder
                as Root File.</a></b><br>
            <br>
          </p>
          gksu package no longer available on the Buster feed.<br>
          <p> There is a workarround but very dirty.. <br>
            It has no wierd side affects ;)<br>
          </p>
          <p><b>Swap buster for stretch repository from sources.list in
              /etc/apt. </b><br>
            Updated the cache, sudo apt-get update &amp;&amp; sudo
            apt-get install gksu -y<br>
            <br>
            After installing gksu swap stretch for buster back in
            sources.list to avoid future problems of wrong versions
            being incorporated.<br>
            And sudo apt-get update after that.</p>
          <p><br>
            <b>Disable Bluetooth:</b><br>
          </p>
          <p>To completely disable the onboard Bluetooth from the
            firmware on the Pi3, add /boot/config.txt</p>
          dtoverlay=pi3-disable-bt<br>
          dtoverlay=pi3-disable-wifi&nbsp; &lt;-- Needed do not insert,
          Example.<br>
          <br>
          <b>64MB Video Memory:</b><br>
          Add to /boot/config.txt or thru Raspberry Pi Configuration:<br>
          gpu_mem=64<br>
          <br>
          <b>Update from Terminal:</b><br>
          <br>
          #!/bin/bash<br>
          sudo apt update &amp;&amp; sudo apt upgrade &amp;&amp; sudo
          apt-get autoclean<br>
          Save as update in pi/.local/bin<br>
          <br>
          <b>Remove Microsoft Repo:</b><br>
          <br>
          Edit /etc/apt/sources.list.d/vscode.list and comment out all
          lines (adding a # at the start of the line). <br>
          Remove the key by deleting
          /etc/apt/trusted.gpg.d/microsoft.gpg<br>
          <br>
          The safest way to future proof a fix, most likely, is to edit
          your /etc/hosts file or local adblocking (pi-hole or router
          based) and set 127.0.0.1 packages.microsoft.com or 0.0.0.0
          packages.microsoft.com. <br>
          Regex filter for _http._tcp.packages.microsoft.com would be
          helpful, too.<br>
          <br>
          Holding the package back may work as well by marking it to
          hold apt-mark hold raspberrypi-sys-mods although this will
          stop other changes from this package.<br>
          <br>
          Take action to stop the repo from being added in the future by
          locking the file. <br>
          Note this may cause an apt failure in the future: sudo chattr
          +i /etc/apt/sources.list.d/vscode.list and sudo chattr +i
          /etc/apt/trusted.gpg.d/microsoft.gpg but ensure the gpg file
          is empty, <br>
          otherwise you're just locking the gpg file in place!<br>
          <h2><a name="Less_Read_and_Writes_on_SD_Card"></a>Less Read
            and Writes on SD Card<br>
          </h2>
          <br>
          These lines can all be added to <b>/etc/fstab</b>.<br>
          Note the use of the size= condition, which limits how much
          space each temporary folder should take up.<br>
          <p><br>
            tmpfs /tmp tmpfs defaults,noatime,nosuid,size=256m 0 0<br>
            tmpfs /var/tmp tmpfs
            defaults,noatime,nosuid,mode=0755,size=256m 0 0<br>
            #System temp folder.<br>
            tmpfs /var/log tmpfs
            defaults,noatime,nosuid,mode=0755,size=100m 0 0<br>
            #System log folder<br>
            tmpfs /var/spool/mqueue tmpfs
            defaults,noatime,nosuid,mode=0755,gid=12,size=30m 0 0<br>
            #Spool<br>
            tmpfs /var/cache/apt/archives tmpfs
            defaults,noexec,nosuid,nodev,mode=0755,size=200m 0 0<br>
            #Apt cache<br>
            tmpfs /home/pi/tmp tmpfs defaults,noatime,nosuid,size=100m 0
            0<br>
            # Need for Auto-RX, DxlAPRS and RS-Decoders.<br>
          </p>
          <p> Using tmpfs means that youll be using RAM instead of the
            SD card.<br>
            This will reduce the amount of writes in the SD card it will
            also increase the memory usage, take this into account.<br>
          </p>
          <p>Files located in /tmp should be temporary and not
            permanent.<br>
            These files are all deleted when your Raspberry PI restarts,
            <br>
            So anything you need to keep or persist across reboots
            shouldn't be stored in RAM.</p>
          <p><br>
            After inserting for example:<br>
            tmpfs /home/pi/tmp tmpfs defaults,noatime,nosuid,size=100m 0
            0<br>
            In /ect/fstab after reboot the tmp folder is accessible in
            the filemanager.<br>
            <br>
          </p>
          <p><img src="img/tmp.png" alt="" width="135" height="218"><br>
            <br>
          </p>
          <p>Auto-RX and Chasemapper log files are redirected via
            symlinks to a temp folder which runs in a virtual memory to
            make less SD writes as stated in fstab.<br>
            After program exit they are moved to /home/pi/Log/ for
            archive.<br>
          </p>
          <br>
          <b>After saving, restart your Raspberry Pi.</b><br>
          This will mount the virtual file system, ready for use.<br>
          <br>
          RS-Decoders Download includes a "clean-up" script for old log
          files:<br>
          <br>
          <img src="img/clean.png" alt="" width="475" height="256"><br>
          <br>
          <b>Older Chromium Browser:</b><br>
          <p>Install older Chromium due screen resolutions with small
            LCD.</p>
          <p>Newer versions do not fit properly.<br>
          </p>
          <p><b>sudo apt-get install gdebi</b></p>
          <p>wget
https://archive.raspberrypi.org/debian/pool/main/c/chromium-browser/chromium-browser_65.0.3325.181-0+rpt4_armhf.deb<br>
            wget
https://archive.raspberrypi.org/debian/pool/main/c/chromium-browser/chromium-codecs-ffmpeg-extra_65.0.3325.181-0+rpt4_armhf.deb<br>
          </p>
          <p>sudo gdebi chromium-browser_65.0.3325.181-0+rpt4_armhf.deb<br>
            sudo gdebi
            chromium-codecs-ffmpeg-extra_65.0.3325.181-0+rpt4_armhf.deb<br>
            <br>
          </p>
          <p><b>Avoid auto updating:</b><br>
          </p>
          sudo apt-mark hold chromium-browser <br>
          sudo apt-mark hold chromium-codecs-ffmpeg-extra<br>
          <br>
          <b>Annoyances:<br>
          </b>
          <p><b>Desktop icons</b> asking permission to execute
            shortcuts.<br>
          </p>
          <p><img src="img/pcmanfm.png" alt="" width="367" height="242"><br>
          </p>
          <p>Open pcmanfm go to Edit/Preferences/General, Check box for
            "Don't ask options on launch executable file" ref<br>
          </p>
          <p><br>
            <b>xfce4-terminal</b> dementia to remember closed tabs even
            if told so:<br>
          </p>
          edit /home/pi/.config/xfce4/terminal/terminalrc change
          MiscConfirmClose=FALSE<br>
          <br>
          <br>
          <b>Change rtl-sdr device serial number:</b>:<br>
          <br>
          <b>rtl_eeprom -s 00000003</b><br>
          #Found 1 device(s):<br>
          #&nbsp; 0:&nbsp; Realtek, RTL2838UHIDIR, SN: 00000001<br>
          #Write new configuration to device [y/n]? y<br>
          #Configuration successfully written.<br>
          #Please replug the device for changes to take effect.<br>
          <br>
          <b>rtl_test</b><br>
          #Found 1 device(s):<br>
          #&nbsp; 0:&nbsp; Realtek, RTL2838UHIDIR, SN: 00000003<br>
          <br>
          WARNING: If running multiple RTLSDRs, do not use serial
          numbers 0, 1, or '00000001'. <br>
          This can lead to rtl_test getting confused and trying to test
          incorrect SDRs, leading to odd behaviour. <br>
          It is strongly suggested you program your RTLSDR serial
          numbers to '00000002', '00000003', etc...<br>
          <br>
          <b>rtl_eeprom -h</b><br>
          Usage:<br>
          &nbsp; &nbsp; [-d device_index (default: 0)]<br>
          &nbsp;&nbsp;&nbsp; [-s &lt;str&gt; set serial number string]<br>
          &nbsp;&nbsp;&nbsp; [-h display this help text]<br>
          <h2><a name="Backup_Scripts_"></a>Backup Script's<br>
          </h2>
          <b><br>
            PiShrink</b><br>
          <br>
          PiShrink is a bash script that automatically shrink a pi image
          that will then resize to the max size of the SD card on boot.
          <br>
          This will make putting the image back onto the SD card faster
          and the shrunk images will compress better.<br>
          <br>
          <img src="img/shrink.png" alt="" width="587" height="230"><br>
          <br>
          <a href="https://github.com/Drewsif/PiShrink" target="_blank">https://github.com/Drewsif/PiShrink</a><br>
          <br>
          wget
          https://raw.githubusercontent.com/Drewsif/PiShrink/master/pishrink.sh<br>
          chmod +x pishrink.sh<br>
          sudo mv pishrink.sh /usr/local/bin<br>
          <br>
          <b>Example:</b><br>
          sudo pishrink.sh pi.img<br>
          <br>
          <b>Mount Raspberry Pi image:</b><br>
          <br>
          <img src="img/Mount_pi.png" alt="" width="570" height="270"><br>
          <br>
          <b>Edit backup img files from Raspberry Pi.</b><br>
          ./mount_pi.sh<br>
          <br>
          This creates a temp-dir for you, auto-assigns the next
          loop-device and sets it up for you as p1 and p2 partition
          devices, and mounts boot and root.<br>
          The cleanup part is in an exit-trap, so if something fails you
          won't have dangling mounts/files.<br>
          <br>
          <b><a href="https://github.com/happysat/mount-pi-image"
              target="_blank">Download Mount script</a></b><b>.</b><br>
          <br>
        </div>
  </body>
</html>
