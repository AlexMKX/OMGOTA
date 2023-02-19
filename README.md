# OpenMqttGateway OTA role

## Usage

``` 
    - hosts: omg_builder
      gather_facts: false
      roles:
        - role: OMGOTA
          vars:
            wifi_ssid: 'your wifi'
            wifi_pass: 'example password'
            ota_pass: 'ota and CAP pasword'
            mqtt_server: 'mqtt server hostname or ip'
            mqtt_pass: 'mqtt server password'
            nodes:
              - name: rfgw-22
                ip: 192.168.0.1
                mac: 94:b9:7e:d5:00:22
              - name: rfgw-11
                ip: 192.168.0.2
                mac: 94:b9:7e:d5:00:11
```