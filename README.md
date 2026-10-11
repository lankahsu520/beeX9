# 1. Overview

> beeX9 is an open source message handler that implements the MCTT protocol.

> What is MCTT
>
> 1. It is base on multicast (udp) protocol.
> 2. It is similar to MQTT, but it is lightweight.
> 3. There's no need to build a message broker on lan.
> 4. Each daemon (application) can be a server or client.
> 5. Fixed Data Struct and include zwave (hcapi v8_12)

# 2. Depend on
## -  [utilx9](https://github.com/lankahsu520/utilx9)
## -  [zwave/zware](https://www.silabs.com/wireless/z-wave)

# 3. Current Status



# 4. Build
   ```bash
$ make
   ```

# 5. Example or Usage
## - beex9_123 - an example. automatically trigger tamper notification and receive the notification.

```bash
# server
# This will get bee_notify_tamper !
$ ./beex9_123 -d 2 -i enp0s3
[19744/19746] chainX_udp_bind:2138 - bind ... (229.255.255.250:6288)
[19744/19746] chainX_thread_handler_udp:3179 - udp-bind ok !!! (229.255.255.250:6288, dbg: 2, net_status: 1, sockfd: 3, net_security: 0)
[19744/19744] honeycomb_restore_file:1640 - (json_f_mctt: /mctt_honeycomb.json)
[19744/19745] bee_topic_issue_caller:101 - (topic: 0/080027A1F836/1234567890/3/0/00010008, value: {"class":"Tamper Sensor","represent":"Tamper Sensor","val":"open","value":255.0})
[19744/19745] bee_topic_issue_caller:101 - (topic: 0/080027A1F836/1234567890/3/0/00010008, value: {"class":"Tamper Sensor","represent":"Tamper Sensor","val":"idle","value":0.0})
[19744/19745] bee_topic_issue_caller:101 - (topic: 0/080027A1F836/1234567890/3/0/00010008, value: {"class":"Tamper Sensor","represent":"Tamper Sensor","val":"open","value":255.0})
[19744/19745] bee_topic_issue_caller:101 - (topic: 0/080027A1F836/1234567890/3/0/00010008, value: {"class":"Tamper Sensor","represent":"Tamper Sensor","val":"idle","value":0.0})
^C[19744/19744] app_signal_handler:562 - (signum: 2)
[19744/19744] honeycomb_save:1672 - (json_f_mctt: /mctt_honeycomb.json)
[19744/19746] chainX_thread_handler_udp:3182 - udp-bind broken !!! (229.255.255.250:6288, dbg: 2)
[19744/19744] app_stop:479 - Bye-Bye !!! (BEEX_123)
[19744/19744] timer_1sec_loop:358 - Bye-Bye !!! (BEEX_123)
[19744/19744] async_loop:437 - __________ Enter __________
[19744/19744] main:672 - Bye-Bye !!!
```

```bash
# client
# This will be a client. 
# To trigger-bee_topic_issue_caller every second.
# Also get bee_notify_tamper !
$ ./beex9_123 -d 2 -i enp0s3 -c
[19747/19749] chainX_udp_bind:2138 - bind ... (229.255.255.250:6288)
[19747/19749] chainX_thread_handler_udp:3179 - udp-bind ok !!! (229.255.255.250:6288, dbg: 2, net_status: 1, sockfd: 3, net_security: 0)
[19747/19747] honeycomb_restore_file:1640 - (json_f_mctt: /mctt_honeycomb.json)
[19747/19748] bee_topic_issue_caller:101 - (topic: 0/080027A1F836/1234567890/3/0/00010008, value: {"class":"Tamper Sensor","represent":"Tamper Sensor","val":"open","value":255.0})
[19747/19748] bee_topic_issue_caller:101 - (topic: 0/080027A1F836/1234567890/3/0/00010008, value: {"class":"Tamper Sensor","represent":"Tamper Sensor","val":"idle","value":0.0})
[19747/19748] bee_topic_issue_caller:101 - (topic: 0/080027A1F836/1234567890/3/0/00010008, value: {"class":"Tamper Sensor","represent":"Tamper Sensor","val":"open","value":255.0})
[19747/19748] bee_topic_issue_caller:101 - (topic: 0/080027A1F836/1234567890/3/0/00010008, value: {"class":"Tamper Sensor","represent":"Tamper Sensor","val":"idle","value":0.0})
^C[19747/19747] app_signal_handler:562 - (signum: 2)
[19747/19747] honeycomb_save:1672 - (json_f_mctt: /mctt_honeycomb.json)
[19747/19749] chainX_thread_handler_udp:3182 - udp-bind broken !!! (:6288, dbg: 2)
[19747/19747] app_stop:479 - Bye-Bye !!! (BEEX_123)
[19747/19747] timer_1sec_loop:358 - Bye-Bye !!! (BEEX_123)
[19747/19747] async_loop:437 - __________ Enter __________
[19747/19747] main:672 - Bye-Bye !!!

```



# 6. Documentation

> Run an example and read it.

# Appendix

# I. Study

# II. Debug

# III. Glossary

# IV. Tool Usage

# Author

> Created and designed by [Lanka Hsu](lankahsu@gmail.com).

# License

> [beeX9](https://github.com/lankahsu520/beeX9) is under the New BSD License (BSD-3-Clause).

