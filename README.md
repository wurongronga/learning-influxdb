# Flux

To see how to retrieve data from a source, select the data source: InfluxDB, CSV, or PostgreSQL.

[InfluxDB](https://docs.influxdata.com/flux/v0.x/get-started/#) [CSV](https://docs.influxdata.com/flux/v0.x/get-started/#) [PostgreSQL](https://docs.influxdata.com/flux/v0.x/get-started/#)

```js
from(bucket: "example-bucket")
  |> range(start: -1d)
  |> filter(fn: (r) => r._measurement == "example-measurement")
  |> mean()
  |> yield(name: "_results")
```

Each example includes the following functions (in the order listed):

* [`from()`](https://docs.influxdata.com/flux/v0.x/stdlib/influxdata/influxdb/from/) to retrieve data from the data source.
* [Pipe-forward operator (`|>`)](https://docs.influxdata.com/flux/v0.x/get-started/syntax-basics/#pipe-forward-operator) to send the output of each function to the next function as input.
* [`range()`](https://docs.influxdata.com/flux/v0.x/stdlib/universe/range/), [`filter()`](https://docs.influxdata.com/flux/v0.x/stdlib/universe/filter/), or both to filter data based on column values.
* [`mean()`](https://docs.influxdata.com/flux/v0.x/stdlib/universe/mean/) to calculate the average of values returned from the data source.
* [`yield()`](https://docs.influxdata.com/flux/v0.x/stdlib/universe/yield/) to yield results to the user.

__
