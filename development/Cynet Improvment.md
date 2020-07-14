## Inconsistency of `cynet.spatioTemporal` and `cynet.cynet_chunk` in using partition file

1. Suppose we have binary partition, then `cynet_chunker` need a file with two columns with the first column being the coords (as in the `.coords` file) but `sp` needs just one column of the partition points;
2. `cynet_chunker` takes partition filename as a string, but for `sp` , one needs to put the filename in a bracket like `["partition_filename.csv"]`.
These inconsistency can be a little confusing for users, and since they probably don't have access to the binary source code, they probably couldn't figure them out either.

## About the `threshold` parameter in `spatioTemporal`
In case you want to keep all the time series no matter how sparse a time series is, you may want to set the `threshold` parameter in `spatioTemporal` to be zero. But the current cynet class code use `>=` and hence will keep time series that is entirely zero. Later developer may consider use `>` instead of `>=`.