# CPUBeacon

Basic functions for reading `/proc/stat`

## Usage

`usage(wait; fields=[CPUBeacon.system, CPUBeacon.user])`

`wait` is the number of seconds to sleep before reading `/proc/stat` again.
`fields` represent which fields should be summed in the numberator while finding the fraction of usage.

Example output:

```julia
usage(1) # Wait for one second to get statistics
5-element Array{Float64,1}:
 0.0595855 
 0.00990099
 0.175258  
 0.019802  
 0.0340909 
```
the first element is the average of all others. the other elements represent fraction of *jiffies* spent in `fields` during `wait` time.
