# ERROR_TRUNK_IN_CISCO
An interface whose trunk encapsulation is “Auto” can not be configured to “trunk” mode.
## Problem
- If you try and change a ports status, to make it a trunk port, you may see this error;
```sh
Switch(config-if)#switchport mode trunk
Command rejected: An interface whose trunk encapsulation is "Auto" can not be configured to "trunk" mode.
```

## Solution
- I don’t know if this is a throwback to when we had ISL trunking and 802.1q, but you need to specify the encapsulation before you can specify a trunk.
```sh
Petes-Switch(config-if)#switchport mode trunk
Command rejected: An interface whose trunk encapsulation is "Auto" can not be configured to "trunk" mode.
Petes-Switch(config-if)#switchport trunk encapsulation dot1q
Petes-Switch(config-if)#switchport mode trunk
Petes-Switch(config-if)#
```
**Souce**: [petenetlive](https://www.petenetlive.com/KB/Article/0001167)
