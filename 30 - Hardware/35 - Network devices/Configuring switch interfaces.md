[[Switch|Switches]] have physical ports, also called interfaces, that can be configured with several settings that may differ from interface to interface.

## Useful commands
- `interface <name>` - Select an interface to modify, short version is `int <name>`
- `interface range <name, range>` - Select multiple interfaces to modify at once, see [[#Configure multiple interfaces|configure multiple interfaces]] for more details; short version is `int ran <name, range>`
- `show interfaces status` - List the configuration of each interface

## Configure speed
Switch interfaces that can support multiple speeds (usually 10/100 and 10/100/1000 interfaces) will, by default, autonegotiate what speed to use. You can configure the speed with the `speed` interface subcommand.

Usually autonegotiation is ideal, but sometimes you may want to configure it manually, such as to avoid the chance that autonegotiation chooses a slower speed.

To do this, first enter terminal configuration mode with `conf t` or `configure terminal`. Next, select an interface using `interface <name>`, such as `interface FastEthernet 0/1`. To select a speed, use the `speed <value>` command, such as `speed 1000`. Finally, exit with `exit`.

Keep in mind that both sides of an Ethernet connection must use the same speed.

## Configure duplex
Similar to speed, interfaces can usually automatically choose a good duplex, the choices being [[Half-duplex|half]] or [[Full-duplex|full]]. When manually configuring duplex, you can choose auto, half, or full.

To change the duplex of an interface, first enter terminal configuration mode with `conf t` or `configure terminal`. Next, select an interface with `interface <name>` such as `interface FastEthernet 0/1`. To change the duplex, use the command `duplex <full/half/auto>`. Finally, exit with `exit`.

## Configure description
Each interface can have a description that makes it easier to see what each one does. This is only used by people and is irrelevant to the function of the switch and interface.

To change the description of an interface, first enter terminal configuration mode with either `conf t` or `configure terminal`. Next, select an interface with `interface <name>`, such as `interface FastEthernet 0/1`. To change the description, do `description <description>`, such as `description sales department, preset to 1000/full`. Finally, exit with `exit`.

## Configure multiple interfaces
To configure multiple interfaces at once, you use the `interface range` command in the place of the interface selection in the previous instructions. For example, you could do `interface range FastEthernet 0/11-20` to change

## Disable and enable interfaces
If you need to bring down an interface without travelling to the switch and shutting it down, there are a couple commands.

To disable an interface, first enter terminal configuration mode with `conf t`. Next, select an interface with `interface <name>`, such as `interface FastEthernet 0/1`. To disable the interface, simply type `shutdown`. Type `exit` when finished.

To enable an interface, enter terminal configuration mode with `conf t`. Next, select an interface with `interface <name>`, such as `interface FastEthernet 0/1`. To enable the interface, simply type `no shutdown`. Type `exit` when finished.

## Reset a configuration
To set a configuration back to its default value, you use the `no` version of the command. For example, when setting speed, instead of typing a speed value such as `speed 100`, you would type `no speed` to reset it. The default for speed is `speed auto`. The same is true for duplex configuration (`no duplex`) and description configuration (`no descriptio`)