# Modbus-TCP-for-Deye-Inverter
An easy way to connect Home Assistant with Deye inverter using Modbus TCP.


With this simple project I wanted to find a more industrial way to connect a Deye inverter with Home Assistan.
Cheap and without any welding.


**The Hardware:**

1. The first thing is a RS485 converter. There are Ethernet, Wifi, POE, dual channel, in plastic, metal casing... There are many to choose from and they are cheap.

    I have used an RS232/485/422 TO POE ETH (B) from the Waveshare brand:


![Image](https://github.com/user-attachments/assets/fbfd1f9b-85a3-4d66-bf55-3fb990694605)



![Image](https://github.com/user-attachments/assets/f74ff8bf-3d07-4fa2-853d-0e5379ff8f26)

2. A RJ45 cable. That's all.






**The Instalation:**

First Steps:

It is necessary to configure the following parameters in RS485 to eth (with you IPs):

![Image](https://github.com/user-attachments/assets/5247a332-cc89-4c3d-9cc4-ebc2c6e98cf4)

![image](https://github.com/user-attachments/assets/fb4bbce3-dcb7-4373-8d88-11b81d2ccb54)



Second Step:

Cut the RJ45 and connect:
- Orange Cable -->  RS485 A
- Orange/White  Cable --> RS485 B
- Green/White Cable --> Signal Ground.


Third Step:

On Home Assistant, put put the Modbus.yaml and Templates.yaml files next to the Configuration.yaml.

Edit Configuration.yaml:

`modbus: !include modbus.yaml`

`template: !include template.yaml`


Thats all!
Developer Tools -> YAML -> Verify Configuration -> Restart


When you restart, if you search for the Inverter entities, you should see all of these:

![Image](https://github.com/user-attachments/assets/f023be1f-0f07-466d-93a6-340ec511d81e)


Notes:
1. They are only reading sensors, I have not been able to make the switches and selectors work, it is on the pending list.
2. I have based myself on the sensors in @slipx06's project. They were much better organized than in Deye's documentation.

To do list (I would be very grateful if you help me with these points):
1. Make Switches functional. Now they only show the state they are in.
2. Make selectors with drop-down menus. Now they only show the information about what is selected.


![Image](https://github.com/user-attachments/assets/7024b207-596a-46c3-acd5-7acc75337a14)

3. Make the entire schedule part work. Now it only shows the information about how it is configured.


![Image](https://github.com/user-attachments/assets/6b96ee3a-6ac7-46c4-a3fd-6b18f89d937a)




Well, I hope you like it, you find it useful and we can improve it.

Thank you!
