<h1 id="h-important">Lesson 3</h1>

Zeek is a network analysis tool that reads network traffic from a pcap and organises the data into different log files based on type or protocol.

*Skip this lesson if your Kali VM has Zeek already installed.* 

So if you have a pcap with several things going on, let's say http connections and a file transfer (FTP), then putting zeek through that pcap will make a file named `http.log` and `ftp.log`.

The greatest strength of zeek is organising your data to make it easier for the human (and the computer) to read big data. If you have 1000 http connections, 1000 SSH, 1000 FTP, 1000 emails, and all of that in a single pcap then that clutter would be extremely hard to read and furthermore would be extremely hard to work with (Wireshark will start slowing down starting at 2GB+ pcaps).

However, as a reminder, you can never be a master at something on the first day. Don't be intimitated if you think reading zeek logs is complicated because it is but with enough practice zeek logs will be understand to see after each lesson.
  
<a href="https://www.corelight.com/hubfs/cheat-sheet/bro-zeek-msft-logs-combo.pdf?hsLang=en">https://www.corelight.com/hubfs/cheat-sheet/bro-zeek-msft-logs-combo.pdf?hsLang=en

```echo 'deb https://download.opensuse.org/repositories/security:/zeek/xUbuntu_24.04/ /' | sudo tee /etc/apt/sources.list.d/security:zeek.list
curl -fsSL https://download.opensuse.org/repositories/security:zeek/xUbuntu_24.04/Release.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/security_zeek.gpg > /dev/null
sudo apt update
sudo apt install zeek-8.0```