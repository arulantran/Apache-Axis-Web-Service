# Apache-Axis-Web-Service
Creating Simple Web Service using Axis
I have attached my Eclipse project.
Detailed procedure follow the below link
http://blog.sencide.com/2011/06/create-web-service-using-apache-axis2.html

If you get errors on JSTL tags then add the following jar file in lib folder of WebInf diretory
http://www.java2s.com/Code/Jar/j/Downloadjstljar.htm


If you get error like "The ServiceClass object does not implement the required method" then do the folloeing step,
Made the below change to the WEB-INF->services->MyService -> META-INF -> services.xml

Initial services.xml

    <messageReceivers>
        <messageReceiver mep="http://www.w3.org/2004/08/wsdl/in-only" class="org.apache.axis2.rpc.receivers.RPCInOnlyMessageReceiver" />
        <messageReceiver  mep="http://www.w3.org/2004/08/wsdl/in-out"  class="org.apache.axis2.rpc.receivers.RPCMessageReceiver"/>
    </messageReceivers>

Update it with the following content 

    <messageReceivers>
        <messageReceiver mep="http://www.w3.org/ns/wsdl/in-only" class="org.apache.axis2.rpc.receivers.RPCInOnlyMessageReceiver" />
        <messageReceiver  mep="http://www.w3.org/ns/wsdl/in-out"  class="org.apache.axis2.rpc.receivers.RPCMessageReceiver"/>
    </messageReceivers>
