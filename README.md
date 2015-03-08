Notes for some fuzzing research...


Software to be fuzzed:

Easy File Share - <link>
FileCopa - <link>
Serv-U - <link>
Vulnserver - <link>
WingFTP - <link>
WiseFTP - <link>


Exercise 1 - Fuzzing Vulnserver with Peach3
-------------------------------------------

Running Peach Pit Validation:

```
peach -t fuzzers\vulnserver_peachpit.xml
```

Start the Peach Remote Agent(For Instrumentation):

```
peach -a tcp
```

Run the Peach fuzzing session:

```
peach fuzzers\vulnserver_peachpit.xml TestHTER
```

Results:

* Example Peach Logs - https://github.com/f47h3r/fuzzing_notes/blob/master/results/vulnserver/PeachLogs
* Example of Fuzz test case that is exploitable - https://github.com/f47h3r/fuzzing_notes/blob/master/results/vulnserver/PeachLogs/vulnserver_peachpit.xml_TestHTER_20150302155506/Faults/EXPLOITABLE_0x264d5172_0x00000000/726/action_2_Output_Unknown%20Action%202.txt


Vulnserver Exploit
-----------------------------

* Vulnserver HTER Crasher: https://github.com/f47h3r/fuzzing_notes/blob/master/results/vulnserver/exploits/crasher.py

* Vulnserver HTER Exploit: https://github.com/f47h3r/fuzzing_notes/blob/master/results/vulnserver/exploits/vulnserver_exploit_calc.py

Finding a "jmp eax" instruction:

```bash

sudo ./msfpescan -j eax ~/Research/fuzzing/results/vulnserver/bin/essfunc.dll

-- Output --

[/fuzzing/results/vulnserver/bin/essfunc.dll]
0x62501084 call eax
0x625011b1 jmp eax
0x625015b1 call eax


```



TODO
---------

* Write Exploit for Vulnserver
* Setup EFS Server
* Fuzz EFS Server


References
-----------------

* http://thisisdearmo.blogspot.com/2012/01/stack-based-bof-for-hter-command-in.html