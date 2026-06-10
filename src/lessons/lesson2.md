<h1 id="h-tip">Lesson 2</h1>

If you have 0 pcap literacy, you need to start by being comfortable with a console.
  
![](../assets/screenshots/kali2.jpg)

A console is where you can tell the computer to do things.
  
Enter these commands into the console and see what happens:

![](../assets/screenshots/kali3.jpg)
`ls`
  
`touch file1`
  
`l`

`echo hello`

`tshark -h`

`cd Downloads`

> [!TIP]  
> Ctrl + Shift + V to paste commands in a Kali console.

Okay! You should now be a **MASTER** at Linux command line.
  
Time to learn Linux file systems.

This is your file system tree.
```
/ <- root directory
    /bin
    /dev
    /home
        /home/kali
            /home/kali/Downloads
            /home/kali/Documents <- you should be here
            /home/kali/Music
            /home/kali/Pictures
            /home/kali/Videos
    /mnt
    /run
    /sys
    /usr
    /boot
    /etc
    /opt
    /root
    /tmp
    /var
```

The `cd` commmand lets you move directories. If you do `cd ..` you will move upwards in the tree.

```
/
    /bin
    /dev
    /home
        /home/kali <- You are now here
    /run
```

Do this command `cd usr/share/bin` to move to a specific place in the tree.

```
/
    /run
    /sys
    /usr
        /usr/share
            /usr/share/nikto
            /usr/share/nmap <- You are now here
            /usr/share/nodejs
    /boot
    /etc
```

Do `cd ../../../` to move upwards 3 times in the tree

```
/ <- You are now here
    /run
    /sys
    /usr
    /boot
    /etc
```

You should now be an **EXPERT** in linux file systems!