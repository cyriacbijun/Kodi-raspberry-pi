# Install Netflix, Hotstar, Jio TV on raspberry pi with KODI

Are you also a tech enthusiast who has a spare Raspberry pi laying around just because you do not like the latest do-it-yourself or instructable?
Well, thankfully I am here to show you the alternate **entertainment** possiblities of the raspberry pi. All this made possible by two awesome open source projects and addons develeopers [Stefano Gottardo](https://github.com/CastagnaIT) and [BotAllen](http://botallen.com/):
- [Kodi](https://kodi.tv/)
- [LibreElec](https://libreelec.tv/)

Clicking on the links themselves will provide an intro. So, let's get started:

1. Download the libreelec OS `img` file from [here](https://libreelec.tv/downloads_new/). Since I have used a raspberry pi 4, this would be the [latest](https://releases.libreelec.tv/LibreELEC-RPi4.arm-9.2.7.img.gz). Beta versions are also available, but this not recommended for day-to-day use.
2. You can use any disc writing software( rufus, dd, etc.,) to write the `img` file unto the microSD card. But personally I would recommend using the **LibreELEC USB-SD Creator** which is available for all major OSes. 
3. Next step is to insert the microSD onto the raspberry pi and start the setup. It is fairly easy to follow the onscreen intructions( setting up wifi, region, ssh, samba settings and maybe customize your interface).

>Note: For rasberry pi 4, connect `HDMI` to port 1 only, otherwise the audio output will not be available.

>Time not correct: Since raspberry pi depends on internet for time, using the Network Time Protocol, it may happen that the time is not fetched correctly. This may be due to inability to access the Time server. Therefore, if time is not updated correctly then add the Google NTP ip address `216.239.35.0` in NTP server settings under LibreElec settings.

4. Now, if you scroll to the `add-ons` section, there are many addons already available, where `youtube` is on of them. Now, for the specialized ones..

## Netflix
The `netflix` addon for kodi is available as a `GitHub` [repo](https://github.com/CastagnaIT/plugin.video.netflix). This is not available officially to kodi users, we have to explicitly add the `addon repository`. 
1. First download the `repo` zip file.
    - [For Kodi 18.X](https://github.com/castagnait/repository.castagnait/raw/master/repository.castagnait-1.0.1.zip)
    - [For Kodi 19.X](https://github.com/castagnait/repository.castagnait/raw/matrix/repository.castagnait-1.0.0.zip)
2. This step is done as a prerequisite for the signing in to netflix. Sometimes simple username and password will not work for accessing your netflix account. So, you need to create an authentication key by doing the following.
You can create the NFAuthentication.key file from any _Personal Computer (desktop / laptop)_, no matter what operating system you use (and Kodi is not needed), then with this file you can login to Netflix add-on from all your devices.

    To create this file and get the PIN, you need to use one of the following software:

    <details>
    <summary><b>For Windows</b><sup> [click to expand]</sup></summary>
    <p>

    **PREREQUISITE**: Chrome browser installed

    **INSTRUCTIONS**: Download the zip and extract the folder, then run the software and follow the instructions on screen. After you have created the file, you have to open it, with Netflix add-on by choosing the login with "Authentication key". Remember to delete the Authentication key file after login.

    **DOWNLOAD**: [NFAuthenticationKey_Windows.zip](https://www.dropbox.com/sh/80zv4umiiyx8ok1/AAABi-vk9CKNNXvpmzkCRTiIa?dl=0) (Google may report incorrectly as malware, press continue and ignore it)

    </p>
    </details>

    <details>
    <summary><b>For Linux and MacOS</b><sup> [click to expand]</sup></summary>
    <p>

    **PREREQUISITE**: A web browser is required, supported browsers: _Chrome, Chromium, Brave Browser_

    **INSTRUCTIONS**: Download the zip, extract the folder and open this folder with the Terminal/Console. Then run the following commands.

    Install these python packages:<br/>
    `pip install pycryptodomex` (or pip3)<br/>
    `pip install websocket-client` (or pip3)

    After run the script:<br/>
    `python NFAuthenticationKey.py` (or python3)<br/>
    Follow the instructions on screen, after you have created the file, you have to open it with Netflix add-on by choosing the login with "Authentication key". Remember to delete the Authentication key file after login.

    **DOWNLOAD**: [NFAuthenticationKey_Linux.zip](https://www.dropbox.com/sh/ls3veptflvneub1/AABz9Tt3EqKUb90PQXNarNxga?dl=0)

    </p>
    </details>
>Note:A PIN is generated on making the `authentication key`, remember this, we need this later

3. Now, you have to copy the repository file `repository.castagnait-1.0.x.zip` and the `authentication key` to the device. This can be done using samba or sftp. If you are using an external device: copy this file to an USB flash drive or memory card and connect it to the device

    * Now open Kodi and in the Add-ons browser, choose `Install from zip file`
    * Navigate in to the Home/downloads folder (or USB flash drive/memory card if you use an external device)
    then install the repository file `repository.castagnait-1.0.x.zip`
    * Return to the add-ons browser and choose `Install from repository` then select `CastagnaIT repository` and install Netflix add-on

4. When signing in, use the `authentication key` to sign in, by choosing the file you copied. Enter the PIN in step 2 and then sign in by entering password.

Well, that's it. The Netflix addon offers many customizations and configurations which is good to have. My favourites are:
- Setting the resolution of video, quality of audio and subtitle language.
- remembering the last seen series
- Skipping intro/exit scenes and much more.

## Hotstar, Jio TV and Sony Liv

All these addons are developed by another great developer and here is the [link](https://github.com/botallen/repository.botallen)

This also follows the same steps as installing netflix. The repository file `repository.botallen-2.0.0.zip` is available [here](https://github.com/botallen/repository.botallen/releases/download/v2.0.0/repository.botallen-2.0.0.zip).

Now, you have to copy the repository file `repository.botallen-2.0.0.zip` to the device. This can be done using samba or sftp. If you are using an external device: copy this file to an USB flash drive or memory card and connect it to the device
- Now open Kodi and in the Add-ons browser, choose `Install from zip file`
- Navigate in to the Home/downloads folder (or USB flash drive/memory card if you use an external device) then install the repository file `repository.botallen-2.0.0.zip`
- Return to the add-ons browser and choose `Install from repository`
    then select `BotAllen Repository` and go into the `Video add-ons` section in the repo, and you'll find all video add-ons
