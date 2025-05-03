There is 100+ touchscreens in posession of rolandecho's employer. They can be donated if there is beings that have will use them in a project. If none will take them, they might get thrown away.

Unfortunately they are all glued into a plastic case, seemingly impossible to remove with a heat gun because the glue has a higher melting point that the plastic case. Also the plastic case is emits an unpleasant when melted. A viable solution to using the displays is to saw off must of the case.

The touchscreen's only interface is this connector from Hirose: <https://www.hirose.com/de/product/document?clcode=CL0580-2412-8-60&productname=FH26W-39S-0.3SHW(60)&series=FH26&documenttype=Catalog&lang=de&documentid=D49355_en> <https://www.mouser.de/ProductDetail/Hirose-Connector/FH26W-39S-0.3SHW60?qs=vcbW%252B4%252BSTIppYpLJPh73gg%3D%3D>

J342

Level Shifter 3,3V => 2,8 V (display) & 1,8 V(touch )
3,7 V Raile direkt von Akku
3,3 V Raile

das Display kann auch mit 2 statt 4 DSI Lanes betreiben, 
das spart schonmal 4 differenzielle Leiter, 
aber dann müsst ihr die init-sequence im Treiber verändern.


Treiber panel-TSD-BV055HDE.c 
Display/DriverIC Datasheet 


Touch-Driver edt-ft5x06.c; 
ist aber zu 99% die Linux Mainline Kernel Version. 
Die einzige Änderung ist, dass der Touch-Treiber in seiner "probe()"-Funktion erst prüft, 
ob der Display-Treiber geladen wurde. Denn sonst hat der Touch-IC keinen Strom und wird nicht gefunden.

## usecase ideas

- handheld console
- general purpose touchscreen display via USB-C
- art project
	- some interesting shape that has touchscreens on all sides and together they display something knowing their physical location in relation to the other screens
- permanentely mounted touch screen computer e.g. for the home assistant UI

Incase the idea is to attach a computer to the touchscreen, one probably wants to design a PCB for use with a system on module like e.g. from Raspberry Pi or Rockchip.
