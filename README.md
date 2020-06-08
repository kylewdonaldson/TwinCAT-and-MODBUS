# TwinCAT-and-MODBUS
MODBUS Interfacing with Twincat

Repo contains two Solutions implementing TwinCAT MODBUS functionality, one behaves as a slave and the other as a master. 

Some Notes on the TwinCAT MODBUS Service. 

1. MODBUS is a master / slave system, the twincat TS-6250 implementation allows a PLC to act as a master and also be queried and controlled 
   as a slave. The TcModBusSrv service runs in the background to facilitate the MODBUS communication through the use of Function Blocks
   in the MODBUS library, most (if not all) MODBUS fucntions have an analogous function block implementation in the library. 
   
2. Remember to open the TCP / UDP port used for Modbus (default is port 502), this must be open on both devices, ussually only relevant on
   the PLC side. 
   
3. When the TS-6250 function is installed on the machine (must be installed on both PLC's if using between two Beckhoff controllers), the 
   TcModbusSrvCfg.exe tool is installed, this tool generates an XML file controlling mapping between PLC variables and MODBUS addresses, 
   if the variables used for MODBUS interfacing on the PLC are named as per default this mapping file must be generated and the PLC GVL
   names editted accordingly. 
   
4. Remember to the Beckhoff Manual on Modbus if you get stuck, and check out InfoSys :)
   
5. A MODBUS tool such as QModMaster is a great aid to learning about MODBUS and debugging it.
   (http://domoticx.com/modbus-software-qmodmaster-windows/) 
  
6. RealPars have a good video series on MODBUS (https://www.youtube.com/watch?v=txi2p5_OjKU) 

7. The naming of the MODBUS interfacing variables in the default can be a little mind bending, good luck, I had to explain it to myself a 
   few times and then get a better engineer than myself to explain it to me too, then I only understood it for about a minute anyway. 
