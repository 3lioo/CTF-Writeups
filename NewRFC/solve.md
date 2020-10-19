## **Challenge name : NewRFC**

# Description :  
We have created a classified messaging protocol. reverse the protocol ;-).
## Solution :
we open the pcap file using wireshark and we get this
[](https://github.com//3lioo//CTF-Writeups//blob//master//NewRFC//2020-10-19_124543.png)

we can notice that every packet has different protocol so it have to be something about protocols but after reading a lot about wirshark, packets analyzing i couldn't find any thing useful then i have received some free hints and still have no idea WTF is reversing the protocols 
so the CTF ended and i didn't solve it 
I've recently contacted my friend whom solved it and it turns out to be so easy to solve it 
look at your wireshark again and remember it is all about protocols 
every packet has different protocol number so let's extract it all using tshark

    tshark -r classified.pcap -T fields -e ip.proto > flag
  and we got this numbers 
  and when we convert the numbers to asci we will get this string 
  

    ZmxhZ3tFejN5XzJsaW5lc19jT2Rpbmd9
when you base64 decode it you will get your flag 

    flag{Ez3y_2lines_cOding}
 
