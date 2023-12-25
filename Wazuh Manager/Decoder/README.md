## Wazuh Log Decoder
Wazuh Manager is incredibly effective in parsing data and decoding a variety of log formats to provide deeper understanding of the endpoint that are being monitored. There are a ton of preconfigured log decoders included. Wazuh is yet unable to decode all kinds of logs, nevertheless. Wazuh therefore provides you with the ability to create and develop your own custom log decoding capability for new log types. 
![wazuh-log decoder](https://documentation.wazuh.com/current/_images/log-data-collection1.png)
## Custom Decoder
Customize the Wazuh decoders to fit your needs and enhance detection capabilities. To achieve this, you can:
* Modify the default decoders.
* Add new custom decoders.
## Add New Custom Decoder
To add new custom decoder in wazuh, you may add new file at `/var/ossec/etc/decoders/local_decoder.xml` or go to wazuh manager UI and nevigate Managements>Decoders>Custom decoders
![add decoder](./images/custom_decoder.png)
After that then click on add new decoder button to add you new custom decoder.
![add decoder](./images/custom_decoder1.png)
In this time, I'm giving you a little hints about the syntax of custom log decoder. but you have to write your own code blocks to fullfill your need. I am also adding my own written custom decoder for a specific endpoints log. so you may use that or rewrite them according to your needs.
Sample decoding code like this:
```
<decoder name="example">
  <program_name>^example</program_name>
</decoder>

<decoder name="example">
  <parent>example</parent>
  <regex>User '(\w+)' logged from '(\d+.\d+.\d+.\d+)'</regex>
  <order>user, srcip</order>
</decoder>
```
> Note: Before use custom decoder as permanant, you must test it.
