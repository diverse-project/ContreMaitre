# Energy

My DSL represent a site description with installed equipments, activity
planning with flexibility (morning task can be shifted up to 2 hours etc).

This DSL is used to run one simulation and get few metrics as a result.

I want generate multiple variants for a single site and collect all the
corresponding metrics.

I don't know if I want to include in my grammar a way to express this variability
for instance `capacity [10000;30000] Wh` to generate `capacity 10000 Wh`, `capacity 20000 Wh` and `capacity 30000 Wh`.
I would still need to specify the ''step'' somewhere actually…
I could also stick with bash script to generate these variants.

My metrics are printed in the stdo of my program, easily grep-able but maybe we could imagine
another way:
* raw result.log
* csv file to link to the next phase (visualization and scientific tooling).

One run take ~3 minutes on my machine, requires a jvm-jdk (not only jre) and uses multiple csv files as input, read-only(up to 20MB).
These files could be shared among simulation for replication issue.

1 variable file (DSL) + multiples csv files (data) -> simulation (3 minutes) -> multiple metrics on the standard output
