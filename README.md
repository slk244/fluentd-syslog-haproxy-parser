# fluentd-syslog-haproxy-plugin
An syslog haproxy log parser

## Usage

This plugins works with default http log format from HAProxy:

```
  log-format "%ci:%cp [%tr] %ft %b/%s %TR/%Tw/%Tc/%Tr/%Ta %ST %B %CC %CS %tsc %ac/%fc/%bc/%sc/%rc %sq/%bq %hr %hs %{+Q}r"
```

## Installing steps

```
gem build fluentd-syslog-haproxy-parser.gemspec
fluent-gem install fluentd-syslog-haproxy-parser-0.0.1.gem

```

## Full fluentd configuration

```
<source>
  @type syslog
  port 5140
  bind 0.0.0.0
  <parse>
    @type haproxy
  </parse>
  tag haproxy
</source>

<match **>
  @type stdout
</match>
```
