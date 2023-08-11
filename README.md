# OpenMqttGateway OTA role

## Usage

requirements.yml
```
collections:
  -  community.docker
roles:
  - name: OMGOTA
    src: git+https://github.com/AlexMKX/OMGOTA.git
```
omg-ota.yml
``` 
- hosts: omg_builder
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
            ip: >-
                {{lookup ("ansible.builtin.pipe","host -4 rfgw-22  | awk '{print $4}' ")}}
          - name: rfgw-11
            ip: >-
                {{lookup ("ansible.builtin.pipe","host -4 rfgw-11  | awk '{print $4}' ")}}
        options:
            - '-DZmqttDiscovery "HADiscovery"'
```