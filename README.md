### KAPACITOR Commands

kapacitor define error_percent -type stream -tick error_percent.tick -dbrp error_percent_example.autogen


kapacitor record stream -task error_percent -duration 30s

kapacitor batch stream -task error_percent -past 15m

kapacitor list recordings $rid

kapacitor replay -recording $rid -task error_percent

kapacitor enable error_percent

kapacitor show error_percent


while true; do i=0; done


kapacitor define error_percent -tick error_percent.tick

kapacitor replay -recording $rid -task batch_cpu_alert

## Task commands
kapacitor define \
    error_percent \
    -type batch \
    -dbrp udpdb.default \
    -tick error_percent.tick

kapacitor enable error_percent
