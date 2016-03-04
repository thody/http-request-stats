# http-request-stats
cURL your way to request timing stats - a helpful command to isolate request bottlenecks.

```zsh
curl -w "@stats.txt" -o /dev/null -s http://www.google.com
```

- `-w "@stats.txt"` point to the report template
- `-o /dev/null` send the response output to `/dev/null`
- `-s` use silent mode
- `http://www.google.com` the URL to request

The output will look something like this:

```zsh
time_namelookup: 0.006
time_connect: 0.016
time_appconnect: 0.000
time_pretransfer: 0.016
time_redirect: 0.000
time_starttransfer: 0.029
-----------------
time_total: 0.029
```



