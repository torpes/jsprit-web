#jsprit-web - 

jsprit-web is the web interface to JSprit api [Vehicle Routing Optimization Algorithm]. 

Web Api Endpoint - https://jsprit.herokuapp.com/vrp/getRoutes
Method - Post
Parameters - 
	messengers - These are the vehicles [XML Format]
	e.g. 		<messengers>
					<item>
						<type>messenger</type>
						<id>A</id>
						<x>13750</x>
						<y>57578</y>
					</item>
				<messengers>
	envelop - These are the shipments which are to be picked from one location and to be dropped on other location [XML Format]
	e.g. 		<envelopes>
					<item>
						<name>envelope</name>
						<id>1</id>
						<pickup_x>13745</pickup_x>
						<pickup_y>55419</pickup_y>
						<deliver_x>13883</deliver_x>
						<deliver_y>55756</deliver_y></item>
					</item>
				</envelopes>
Output - 
	Optimized solution in xml format
	


Sample Request Format - 
messengers : <messengers><item><type>messenger</type><id>A</id><x>13750</x><y>57578</y></item><item><type>messenger</type><id>B</id><x>15104</x><y>53410</y></item></messengers>

envelop : <envelops><item>  	<name>envelope</name> 	<id>1</id> 	<pickup_x>13745</pickup_x> 	<pickup_y>55419</pickup_y> 	<deliver_x>13883</deliver_x> 	<deliver_y>55756</deliver_y>  	</item>  <item>  	<name>envelope</name> 	<id>2</id> 	<pickup_x>13745</pickup_x> 	<pickup_y>55419</pickup_y> 	<deliver_x>13883</deliver_x> 	<deliver_y>55756</deliver_y>  	</item>  <item>  	<name>envelope</name> 	<id>3</id> 	<pickup_x>15738</pickup_x> 	<pickup_y>57396</pickup_y> 	<deliver_x>35996</deliver_x> 	<deliver_y>79499</deliver_y>  	</item>  <item>  	<name>envelope</name> 	<id>4</id> 	<pickup_x>12045</pickup_x> 	<pickup_y>60418</pickup_y> 	<deliver_x>19349</deliver_x> 	<deliver_y>57118</deliver_y>  	</item></envelops>

Output :
<?xml version="1.0" encoding="UTF-8"?>
<problem xmlns="http://www.w3schools.com"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.w3schools.com vrp_xml_schema.xsd">
     <problemType>
          <fleetSize>FINITE</fleetSize>
     </problemType>
     <vehicles>
          <vehicle>
               <id>B</id>
               <typeId>messengerType</typeId>
               <startLocation>
                    <id>[x=15104.0][y=53410.0]</id>
                    <coord x="15104.0" y="53410.0"/>
               </startLocation>
               <endLocation>
                    <id>[x=15104.0][y=53410.0]</id>
                    <coord x="15104.0" y="53410.0"/>
               </endLocation>
               <timeSchedule>
                    <start>0.0</start>
                    <end>1.7976931348623157E308</end>
               </timeSchedule>
               <returnToDepot>false</returnToDepot>
          </vehicle>
          <vehicle>
               <id>A</id>
               <typeId>messengerType</typeId>
               <startLocation>
                    <id>[x=13750.0][y=57578.0]</id>
                    <coord x="13750.0" y="57578.0"/>
               </startLocation>
               <endLocation>
                    <id>[x=13750.0][y=57578.0]</id>
                    <coord x="13750.0" y="57578.0"/>
               </endLocation>
               <timeSchedule>
                    <start>0.0</start>
                    <end>1.7976931348623157E308</end>
               </timeSchedule>
               <returnToDepot>false</returnToDepot>
          </vehicle>
     </vehicles>
     <vehicleTypes>
          <type>
               <id>messengerType</id>
               <capacity-dimensions>
                    <dimension index="0">15</dimension>
               </capacity-dimensions>
               <costs>
                    <fixed>0.0</fixed>
                    <distance>1.0</distance>
                    <time>0.0</time>
               </costs>
          </type>
     </vehicleTypes>
     <shipments>
          <shipment id="3">
               <pickup>
                    <location>
                         <id>[x=15738.0][y=57396.0]</id>
                         <coord x="15738.0" y="57396.0"/>
                    </location>
                    <duration>0.0</duration>
                    <timeWindows>
                         <timeWindow>
                              <start>0.0</start>
                              <end>1.7976931348623157E308</end>
                         </timeWindow>
                    </timeWindows>
               </pickup>
               <delivery>
                    <location>
                         <id>[x=35996.0][y=79499.0]</id>
                         <coord x="35996.0" y="79499.0"/>
                    </location>
                    <duration>0.0</duration>
                    <timeWindows>
                         <timeWindow>
                              <start>0.0</start>
                              <end>1.7976931348623157E308</end>
                         </timeWindow>
                    </timeWindows>
               </delivery>
               <capacity-dimensions>
                    <dimension index="0">1</dimension>
               </capacity-dimensions>
          </shipment>
          <shipment id="2">
               <pickup>
                    <location>
                         <id>[x=13745.0][y=55419.0]</id>
                         <coord x="13745.0" y="55419.0"/>
                    </location>
                    <duration>0.0</duration>
                    <timeWindows>
                         <timeWindow>
                              <start>0.0</start>
                              <end>1.7976931348623157E308</end>
                         </timeWindow>
                    </timeWindows>
               </pickup>
               <delivery>
                    <location>
                         <id>[x=13883.0][y=55756.0]</id>
                         <coord x="13883.0" y="55756.0"/>
                    </location>
                    <duration>0.0</duration>
                    <timeWindows>
                         <timeWindow>
                              <start>0.0</start>
                              <end>1.7976931348623157E308</end>
                         </timeWindow>
                    </timeWindows>
               </delivery>
               <capacity-dimensions>
                    <dimension index="0">1</dimension>
               </capacity-dimensions>
          </shipment>
          <shipment id="1">
               <pickup>
                    <location>
                         <id>[x=13745.0][y=55419.0]</id>
                         <coord x="13745.0" y="55419.0"/>
                    </location>
                    <duration>0.0</duration>
                    <timeWindows>
                         <timeWindow>
                              <start>0.0</start>
                              <end>1.7976931348623157E308</end>
                         </timeWindow>
                    </timeWindows>
               </pickup>
               <delivery>
                    <location>
                         <id>[x=13883.0][y=55756.0]</id>
                         <coord x="13883.0" y="55756.0"/>
                    </location>
                    <duration>0.0</duration>
                    <timeWindows>
                         <timeWindow>
                              <start>0.0</start>
                              <end>1.7976931348623157E308</end>
                         </timeWindow>
                    </timeWindows>
               </delivery>
               <capacity-dimensions>
                    <dimension index="0">1</dimension>
               </capacity-dimensions>
          </shipment>
          <shipment id="4">
               <pickup>
                    <location>
                         <id>[x=12045.0][y=60418.0]</id>
                         <coord x="12045.0" y="60418.0"/>
                    </location>
                    <duration>0.0</duration>
                    <timeWindows>
                         <timeWindow>
                              <start>0.0</start>
                              <end>1.7976931348623157E308</end>
                         </timeWindow>
                    </timeWindows>
               </pickup>
               <delivery>
                    <location>
                         <id>[x=19349.0][y=57118.0]</id>
                         <coord x="19349.0" y="57118.0"/>
                    </location>
                    <duration>0.0</duration>
                    <timeWindows>
                         <timeWindow>
                              <start>0.0</start>
                              <end>1.7976931348623157E308</end>
                         </timeWindow>
                    </timeWindows>
               </delivery>
               <capacity-dimensions>
                    <dimension index="0">1</dimension>
               </capacity-dimensions>
          </shipment>
     </shipments>
     <solutions>
          <solution>
               <cost>42388.9129328627</cost>
               <routes>
                    <route>
                         <driverId>noDriver</driverId>
                         <vehicleId>A</vehicleId>
                         <start>0.0</start>
                         <act type="pickupShipment">
                              <shipmentId>4</shipmentId>
                              <arrTime>3312.4952830155094</arrTime>
                              <endTime>3312.4952830155094</endTime>
                         </act>
                         <act type="pickupShipment">
                              <shipmentId>3</shipmentId>
                              <arrTime>8084.364204098736</arrTime>
                              <endTime>8084.364204098736</endTime>
                         </act>
                         <act type="deliverShipment">
                              <shipmentId>4</shipmentId>
                              <arrTime>11706.049585243818</arrTime>
                              <endTime>11706.049585243818</endTime>
                         </act>
                         <act type="deliverShipment">
                              <shipmentId>3</shipmentId>
                              <arrTime>39599.2704462344</arrTime>
                              <endTime>39599.2704462344</endTime>
                         </act>
                         <end>39599.2704462344</end>
                    </route>
                    <route>
                         <driverId>noDriver</driverId>
                         <vehicleId>B</vehicleId>
                         <start>0.0</start>
                         <act type="pickupShipment">
                              <shipmentId>1</shipmentId>
                              <arrTime>2425.481807806441</arrTime>
                              <endTime>2425.481807806441</endTime>
                         </act>
                         <act type="pickupShipment">
                              <shipmentId>2</shipmentId>
                              <arrTime>2425.481807806441</arrTime>
                              <endTime>2425.481807806441</endTime>
                         </act>
                         <act type="deliverShipment">
                              <shipmentId>1</shipmentId>
                              <arrTime>2789.6424866283037</arrTime>
                              <endTime>2789.6424866283037</endTime>
                         </act>
                         <act type="deliverShipment">
                              <shipmentId>2</shipmentId>
                              <arrTime>2789.6424866283037</arrTime>
                              <endTime>2789.6424866283037</endTime>
                         </act>
                         <end>2789.6424866283037</end>
                    </route>
               </routes>
          </solution>
          <solution>
               <cost>42388.9129328627</cost>
               <routes>
                    <route>
                         <driverId>noDriver</driverId>
                         <vehicleId>A</vehicleId>
                         <start>0.0</start>
                         <act type="pickupShipment">
                              <shipmentId>4</shipmentId>
                              <arrTime>3312.4952830155094</arrTime>
                              <endTime>3312.4952830155094</endTime>
                         </act>
                         <act type="pickupShipment">
                              <shipmentId>3</shipmentId>
                              <arrTime>8084.364204098736</arrTime>
                              <endTime>8084.364204098736</endTime>
                         </act>
                         <act type="deliverShipment">
                              <shipmentId>4</shipmentId>
                              <arrTime>11706.049585243818</arrTime>
                              <endTime>11706.049585243818</endTime>
                         </act>
                         <act type="deliverShipment">
                              <shipmentId>3</shipmentId>
                              <arrTime>39599.2704462344</arrTime>
                              <endTime>39599.2704462344</endTime>
                         </act>
                         <end>39599.2704462344</end>
                    </route>
                    <route>
                         <driverId>noDriver</driverId>
                         <vehicleId>B</vehicleId>
                         <start>0.0</start>
                         <act type="pickupShipment">
                              <shipmentId>1</shipmentId>
                              <arrTime>2425.481807806441</arrTime>
                              <endTime>2425.481807806441</endTime>
                         </act>
                         <act type="pickupShipment">
                              <shipmentId>2</shipmentId>
                              <arrTime>2425.481807806441</arrTime>
                              <endTime>2425.481807806441</endTime>
                         </act>
                         <act type="deliverShipment">
                              <shipmentId>1</shipmentId>
                              <arrTime>2789.6424866283037</arrTime>
                              <endTime>2789.6424866283037</endTime>
                         </act>
                         <act type="deliverShipment">
                              <shipmentId>2</shipmentId>
                              <arrTime>2789.6424866283037</arrTime>
                              <endTime>2789.6424866283037</endTime>
                         </act>
                         <end>2789.6424866283037</end>
                    </route>
               </routes>
          </solution>
     </solutions>
</problem>


	
	