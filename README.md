---
title: "Running Cedr"
---

{% include toc title="Table of Contents" %}

## Prerequisites

- A USB drive or SD card, 4gb or more (32gb is reccomended), formatted with a single partition, ext4 filesystem

## Section I - Installing Cedr

Plug in your USB drive/SD card and run the following command in bash:

```
fdisk -l
```

Identify your USB drive/SD card in the list. Usually, it'll be at the end. Find the text starting with `/dev` right before your drive is listed. That is your /dev *device*. Remember it, we'll need it.

Run the following command to install cedr to the drive (replace /dev/sdX with your SD card/USB drive):

```
curl https://raw.githubusercontent.com/rainestorme/cedr/main/cedr-bootstrap.sh | bash -s /dev/sdX xfce
```

After a while (10-20 minutes) you'll be prompted for a username and password. Supply them. The chroot will automatically be unmounted.

## Section II - Launching Cedr

Run the following commands:

```
cd /home/chronos/usbdrv
./cedr-activate.sh
```

## Section III - Unmounting

Once finished, run:

```
bash <(curl http://raw.githubusercontent.com/rainestorme/cedr/main/cedr-umount.sh)
```

and unplug your drive.

## Section IV - Launching Cedr Again

Plug in your drive and run:

```
fdisk -l
```

Find your /dev device and run the following command, replacing /dev/sdX with your device:

```
curl https://raw.githubusercontent.com/rainestorme/cedr/main/cedr-mount.sh | bash -s /dev/sdX
```

Once finished, run:

```
bash <(curl http://raw.githubusercontent.com/rainestorme/cedr/main/cedr-umount.sh)
```

and unplug your drive.
