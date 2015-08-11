Stouts.statsdaemon
=============

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.statsdaemon.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.statsdaemon)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.statsdaemon-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/1969)

Ansible role which help you with:

* Install and setup [statsdaemon](https://github.com/etsy/statsdaemon/)

#### Variables

```yaml
statsdaemon_enabled: yes                # enable the role
statsdaemon_version: 0.7.1
statsdaemon_home: /opt/statsdaemon      # where to install

statsdaemon_address: ":8125"            # listen UDP
statsdaemon_tcpaddr: ""                 # listen TCP
statsdaemon_debug: false                # print statistics sent to graphite
statsdaemon_delete_gauges: true         # don't send values to graphite for inactive gauges, as opposed to sending the previous value
statsdaemon_flush_interval: 10          # flush interval (seconds)
statsdaemon_graphite: "127.0.0.1:2003"  # graphite service address (or - to disable)
statsdaemon_max_udp_packet_size: 1472   # maximum UDP packet size
statsdaemon_percent_threshold: []       # percentile calculation for timers (0-100, may be given multiple times)
statsdaemon_persist_count_keys: 60      # number of flush-intervals to persist count keys
statsdaemon_postfix: ""                 # postfix for all stats
statsdaemon_prefix: ""                  # prefix for all stats
statsdaemon_receive_counter: ""         # metric name for total metrics received per interval
```


#### Usage

Add `Stouts.statsdaemon` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.statsdaemon

  vars:
    statsdaemon_graphite: g.myhost.com
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.statsdaemon/issues)!
