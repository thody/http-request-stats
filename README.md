# http-request-stats
cURL your way to request stats - a helpful command to isolate request bottlenecks.

## Timing Report
```zsh
curl -w "@timing_report_template.txt" -o /dev/null -s http://www.google.com
```

- `-w "@timing_report_template.txt"` point to the report template
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

## Full Report

Need more info? This command dumps all that cURL will report on.

```zsh
curl -w "@full_report_template.txt" -o /dev/null -s http://www.google.com
```

Output:

```zsh
remote_ip: 184.150.183.114
remote_port: 80
content_type: text/html; charset=UTF-8
http_code: 302
size_download: 258
size_header: 213
size_request: 78
size_upload: 0
speed_download: 9262.000
speed_upload: 0.000
redirect_url: http://www.google.ca/?gfe_rd=cr&ei=dLHZVoWZHquC8Qevna6gDw
url_effective: http://www.google.com/
num_connects: 1
num_redirects: 0
ssl_verify_result: 0

time_appconnect: 0.000
time_connect: 0.021
time_namelookup: 0.013
time_pretransfer: 0.021
time_redirect: 0.000
time_starttransfer: 0.028
==========================
time_total: 0.028
```



