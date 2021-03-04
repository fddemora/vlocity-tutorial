# vlocity tutorial/notes

Vlocity Digital experience includes flex cards, omniscript, and lwc.   <br/>
Flex cards means the interface. Omniscript is the same but with a certain business process in mind such as paying a bill. Vlocity 
Digital experience uses lwc for fast and smooth experience. <br/><br/>

In Service management, there is DataRaptor, Integration Procedure, and calculations.<br/>
DataRaptor deals with the Salesforce data, so it can retrieve data and change data.<br/>
DataRaptor Extract deals with getting data and transforming.<br/>
DataRaptor Load deals with transforming and saving data to Salesforce.<br/>
Finally DataRaptor Transform transforms any data. <br/><br/>

Integration Procedure is a server side process, meaning faster execution time compared to the client. <br/>
Does this mean that DataRaptor is not server side?<br/><br/>


There are rules to determine wether to use DataRaptors or integration procedure.<br/>
Use DataRaptors if you need to read data from SObject.or write data to SObject, but not both.<br/>
The SObject you need to read from or write to have a defined relationship.<br/>
You only need to work with JSON or XML data. No SObjects involved.<br/>
You can perform any needed filtering, calculation, or reformatting of data values using one or a series of formulas.<br/>
You can make any needed changes to the data structure by mapping input JSON nodes to output JSON nodes. <br/><br/>

Use an integration procedure if: <br/>
You need to both read from and write to one or more SObjects, which means you need to call atleast two DataRaptors.<br/>
The SObjects you need to read from or write to have no defined relationship.<br/>
Transforming your data can’t be done using formulas alone.<br/>
JSON node mappings aren’t straightforward and/or require a series of steps.<br/>
You need to read from or write to multiple data sources types such as SObects, CSV files, external object, Apex classes…<br/>
You need to perform actions such as calling a REST API, sending an email, merging lists, handling errors, and so on. <br/><br/>

In short, use Integration Procedure over DataRaptor, and use Integration Procedure to call DataRaptor.<br/><br/>

I just realized that there are sample vlocity examples for me to compare if I get stuck. That’s good!<br/><br/>

Now for some naming conventions. <br/>
FlexCards - prefix Object Detail - team Account Details<br/>
OmniScripts type/prefixVerbObjectDetail - team/editAccount<br/>
Integration Procedures - type/prefixVerbObjectDetail - team/getAccountDetails<br/>
DataRaptors - prefixVerbObjectDetail - sampleGetAccountDetails<br/><br/>


