## **Challenge name : NewRFC**

# Description :  
We have created a classified messaging protocol. reverse the protocol ;-).
![link](https://github.com/3lioo/CTF-Writeups/blob/master/NewRFC/classified.pcap)
## Solution :
we open the pcap file using wireshark and we get this
![](https://github.com/3lioo/CTF-Writeups/raw/master/NewRFC/2020-10-19_124543.png?raw=true)

we can notice that every packet has different protocol so it have to be something about protocols but after reading a lot about wirshark, packets analyzing i couldn't find anything useful then i have received some free hints and still have no idea WTF is reversing the protocols 
so the CTF ended and i didn't solve it but
I've recently contacted my friend whom solved it and it turns out to be so easy to solve it 
so let's do it.

look at your wireshark again and remember it is all about protocols 
every packet has different protocol number so let's extract it all using tshark

    tshark -r classified.pcap -T fields -e ip.proto > flag
  and we will get this numbers 

![](https://github.com/3lioo/CTF-Writeups/blob/master/NewRFC/22.png?raw=true)

we convert the numbers to asci and we will get this string 
  

    ZmxhZ3tFejN5XzJsaW5lc19jT2Rpbmd9
    
  it is base64 so decode it you will get your flag 

    flag{Ez3y_2lines_cOding}
 
