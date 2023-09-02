---
  - name: ssh tunneling test
    hosts: rpi
    tasks:

    - name: Run command
      shell:
         "ssh -o GatewayPorts=true -L 8012:0.0.0.0:5001 192.168.1.251 -N"
      register: mycmd
      tags: mycmd

    - debug: msg="{{mycmd.stdout}}"