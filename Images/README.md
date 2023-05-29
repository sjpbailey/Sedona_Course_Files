# Universal Devices WiFi Pool NodeServer

## Based on the Contemporary Controls BASpi-6U6R and or the BASpi-Edge-SYS6U6R BACnet/IP Wi-Fi/IP Control Devices

* This controllers can be used to control low voltage switchable devices for any advanced control sequence attached via ethernet or Wi-Fi IP.

## Reasons

* The purpose of this Nodeserver is to replace a conventional time clock pool control systems. This custom control through the ISY for your Pool and general Home automation for multiple control operations, WiFi, IP, BACnet. there is no internal logic in the Contemporary Controls BASpi device all interlocks for heat are done within this poly all other control is done through the ISY programming.

* It utilizes Contemporary Controls BASpi-6U6R or the BASpi-Edge-6U6R BACnet control Modules. Using the IntellicommII interface from Pentiar for High and Low Speed settings for a Penteir Intelliflo VFD pump.
Valve control for sweep or skim control it utilizes a Intermatic Actuator and a Jandy valve (or equivilent).
Heat output for boiler or solar heating using a 24vac relay.
Light output for pool light.
Inputs for Pump Status, Outside air, Pool, Boiler, Solar temperatures, an optional PSI input for filter pressure. BOILER WILL NOT RUN WITHOUT PUMP RUNNING AND PUMP STATUS ON!

* Have more than one pool? Just edit the parameter "key" nodes value to match the number of pools you have, then for each BASpi-6u6r added you will then need to add the IP Address for "value" to match each BASpi-6u6r controller, pooip_0-5 is already in the key just add your IP Address(es).
* You can add up to six (6) pools or nodes with this node serer. Please see the last image below for an example of my pool.
* This also uses the main energy saving device the Itelliflo pump by Pentiar. It incorporates the Intellicomm II interface for two speed options. If you do not have the Intelliflo you can also be used with across the line start stop of existing pumps with an interface low voltage relay. However using a variable flow pump is the main reason you will be saving energy as my pool run at around 450-600 watts daily for 6 hours and is very clean. I am sure there are relay interfaces for other variable flow/spped pumps I have not looked into and that is up to you because the start stop capibillity is provided.

* All switching is 24vac or lower for all outputs on the Edge or BASpi-6u6r device!

* ALL OUTPUTS ARE LOW VOLTAGE 24VAC OR LESS, USE THE APPROPRIATE INTEFACE RELAY FOR SWITCHING ABOVE 24VAC!!

Please see links below for information & configuration of this Device within Contemporary Controls GUI.

[Intelliflo Pump](https://www.pentair.com/en-us/products/residential/pool-spa-equipment/pool-pumps/intelliflo_vsf.html)

[Intellicomm II](https://github.com/sjpbailey/udi-poly-baspool-python-master-v3/blob/ee737e521417fd444bea6171df800e65cc61c6c0/Archive-images/IntelliComm_II_Interface_Adapter_English.pdf)

[Intermatic Actuator](https://github.com/sjpbailey/udi-poly-baspool-python-master-v3/blob/a71b7edee69c9a22be34a150c644335e8ad80910/Archive-images/Intermatic-valve-actuator.pdf)

[Jandy Valve](https://github.com/sjpbailey/udi-poly-baspool-python-master-v3/blob/a71b7edee69c9a22be34a150c644335e8ad80910/Archive-images/Jandy-valve.PDF)

![CAD Wiring](https://github.com/sjpbailey/udi-poly-baspool-python-master-v3/blob/a70bd778c9fcdfd42ddf0ad7fae1f9bfd7dbe54f/Archive-images/Pool-CAD.png)

* This Network BAS series will include in the near future custom home control for Garage Door, Well Pump Control, HVAC, VVT, Boiler, along with any custom control you create utilizing the pip bascontrolns module <https://pypi.org/project/bascontrolns/>.

* This controller sits on a Raspberry Pi. You can easily add it to your ISY after you configure its ipaddress. You can also use a USB camera for visual ability using VLC or VCN on your rasperry pi.

* Pool ISY Control

![Pool Control](https://github.com/sjpbailey/udi-poly-baspool-python-master-v3/blob/96c5c65bc36aceb86f044b4f204713e52e2a0818/Archive-images/ISY_Pool_Control.png)

* Pool ISY Program Example

![Pool Program](https://github.com/sjpbailey/udi-poly-baspool-python-master-v3/blob/fc46203d14edef54d4c23816dbc5d4e4677cbfad/Archive-images/ISY_Pool_Program_Skim.png)

### BASpi-SYS6U6R and the BASpi-Edge DIY BacNet Control Device by Contemporary Controls

* Main
[Contemporary Controls BASpi DIY](https://www.ccontrols.com/basautomation/baspi.htm)
* BASpi 6U6R Controller
[Contemporary Controls BASpi Edge 6U6R](https://www.ccontrols.com/basautomation/baspiedge.php)
* BASpi 6U6R Controller
[Contemporary Controls BASpi 6U6R](https://www.ccontrols.com/pdf/ds/BASPI-datasheet.pdf)
* BASpi 6U6R Installation
[Contemporary Controls BASpi 6U6R Install](https://www.ccontrols.com/pdf/BASpi-hardware-install-guide.pdf)
* BASpi 6U4R2A Controller
[Contemporary Controls BASpi 6U4R2A](https://www.ccontrols.com/pdf/ds/BASPI-AO2-datasheet.pdf)
* BASpi 6U4R2A Installation
[Contemporary Controls BASpi 6U4R2A Install](https://www.ccontrols.com/pdf/TD180600.pdf)
* BASpi Controller Configuration
[Contemporary Controls BASpi Configuration Quick Start](https://www.ccontrols.com/pdf/is/BASPI-QSGuide.pdf)

#### Input Configuration

* You must configure your inputs for the appropriate device attached

[Universal Input Configuration Video](https://www.youtube.com/watch?v=hTd1mR7npP4)

* Python 3.7.7

* Supported Nodes
  * Up to 36 Universal Inputs
  * Up to 36 Binary Outputs
  
##### Configuration

###### Defaults

* Default Short Poll:  Every 2 minutes
* Default Long Poll: Every 4 minutes (heartbeat)

###### Requirments

* requests
* bascontrolns >= 0.0.3
* udi_interface

###### User Provided

* Enter the number of pool nodes you desire 0-5
* Enter your IP address for up to six (6) BASpi-SYS6U6R controller,
* Config: key = poolip_* (* = 0-5) this value is provided, Value = Enter Your BASpi IP Address, Example: key poolip_0  value 192.168.1.47.
* Save and restart the NodeServer

* Pool Polyglot Configuration

![BASPOOL Polyglot Configuration](https://github.com/sjpbailey/udi-poly-baspool-python-master-v3/blob/4c1e490fcd107386464fbba1d0ce24e7f741988c/Archive-images/Polyglot-config.png)
