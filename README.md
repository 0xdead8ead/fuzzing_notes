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
