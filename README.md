<h1>Packet Analysis Using Wireshark</h1>

<h2>Description</h2>
In this lab, we will explore analyzing packet captures using the packet analyzer tool, Wireshark. The network packet capture file contains data captured from a system that made web requests to a site. We will access Wireshark using a virtual machine.


<h2>Environments Used </h2>

- <b>Wireshark</b>

<h2>Program Walk-Through:</h2>

<p align="center">
We first start by opening the file from the desktop in Wireshark: <br/>
<img src="https://i.imgur.com/FdlUfRZ.png" height="100%" width="100%" alt="Wireshark"/>
<br />
<br />
Once the packet capture is open, we will apply an IP address filter in the search bar to search for traffic associated with IP <em><strong>"142.250.1.139"</strong></em>. We'll examine the first packet with the <em><strong>TCP</strong></em> protocol:  <br/>
<img src="https://i.imgur.com/GvtAGyL.png" height="100%" width="100%" alt="Splunk Query"/>
<br />
<br />
If we click on the "Transmission Control Protocol" subtree, we can details regarding the source and destination TCP ports, sequence numbers, and TCP flags: <br/>
<img src="https://i.imgur.com/YH6IXoz.png" height="100%" width="100%" alt=" Wireshark"/> <br/>
<br />
<img src="https://i.imgur.com/A6tWD2K.png" height="100%" width="100%" alt=" Wireshark"/>
<br />
<br />
Next we will search using source and destination IP addresses, which can be done using either <em><strong>ip.src</strong></em> or <em><strong>ip.dst</strong></em>:  <br/>
<img src="https://i.imgur.com/YKwWUxD.png" height="100%" width="100%" alt="Wireshark"/> <br/>
<br />
<img src="https://i.imgur.com/2fumcwR.png" height="100%" width="100%" alt="Wireshark"/>
<br />
<br />
Now we will search by ethernet MAC address using <em><strong>eth.addr</strong></em> which includes all traffic to that address regardless of protocol:  <br/>
<img src="https://i.imgur.com/2DGpNWO.png" height="100%" width="100%" alt="Wireshark"/>
<br />
<br />
If we click on the first packet and look under the "Ethernet II" subtree we can see if the MAC address was the source or destination address:  <br/>
<img src="https://i.imgur.com/m5uNDdy.png" height="100%" width="100%" alt="Wireshark"/>
<br />
<br />
If we expand the "Internet Protocol Version 4" subtree we can identify more information about the packet including the "Time to Live" and Protocol" fields:  <br/>
<img src="https://i.imgur.com/lktNllj.png" height="100%" width="100%" alt="Wireshark"/>
<br />
<br />
Now we will use filters to examine DNS traffic and its queries and answers. We can do this by applying a <em><strong>udp.port</strong></em>:  <br/>
<img src="https://i.imgur.com/hmffq5x.png" height="100%" width="100%" alt="Wireshark"/>
<br />
<br />
If we click on the first packet and click on the "Domain Name System (query)" subtree, we can see the name of the queried website "opensource.google.com":  <br/>
<img src="https://i.imgur.com/7YL71cE.png" height="100%" width="100%" alt="Wireshark"/>
<br />
<br />
If we expand the "Answers" subtree, we can the addresses associated with the queried website:  <br/>
<img src="https://i.imgur.com/EZvjjK0.png" height="100%" width="100%" alt="Wireshark"/>
<br />
<br />
Now we will use filters to examine TCP packets and search for text present in payload data contained inside network packets. We apply the <em><strong>tcp.port</strong></em> filter:  <br/>
<img src="https://i.imgur.com/wGApfxY.png" height="100%" width="100%" alt="Wireshark"/>
<br />
<br />
If we open the first packet we can see the Destination IP address is "169.254.169.254" along with other information:  <br/>
<img src="https://i.imgur.com/UldSehU.png" height="100%" width="100%" alt="Wireshark"/>
<br />
<br />
Lastly, we will search for TCP packet data that contains the specific text, "curl":  <br/>
<img src="https://i.imgur.com/kvc9aU2.png" height="100%" width="100%" alt="Wireshark"/>
</p>
<br />
<br />

