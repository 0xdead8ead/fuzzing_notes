Notes for some fuzzing research...




Fuzzing Vulnserver with Peach3
------------------------------

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