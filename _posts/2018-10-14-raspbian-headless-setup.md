---
published: true
tags: raspbian headless setup wifi ssh
title: Raspbian Headless Setup
---
To set any Raspberry Pi in headless mode, you'll only need your Pi with pre-loaded Raspbian OS (latest is Stretch) and your Wi-Fi network.
Make sure you know your Wi-Fi SSID and Password in order to perform headless setup.

Once you've burned/etched the Raspbian image onto the microSD card, connect the card to your working PC and you'll see the card being mounted as "boot". Inside this "boot" directory, you need to make 2 new files. You can create the files using your favourite code editor.

**Step 1**: Create an empty file. You can use Notepad on Windows or TextEdit to do so by **creating a new file**. Just name the file ssh. Save that empty file and dump it into **boot partition** (microSD).

**Step 2**: Create another file name wpa_supplicant.conf . This time you need to write a few lines of text for this file. For this file, you need to use the **FULL VERSION** of **wpa_supplicant.conf**. Meaning you must have the 3 lines of data namely **country, ctrl_interface and update_config**.

{% gist 5f2c332b6ad8dae2fd1b9519bac0b40a %}

Original forum post: [https://www.raspberrypi.org/forums/viewtopic.php?t=191252](https://www.raspberrypi.org/forums/viewtopic.php?t=191252)
