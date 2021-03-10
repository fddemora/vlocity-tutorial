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


## VPE3 FlexCards Overview
After completing VPE3, I must be able to explain or do: <br/>
the features and capabilities of FlexCards<br/>
use the data source wizard to select and configure a data source for flexcards<br/>
navigate the flexcard designer's UI<br/>
drag and drop elements onto a flexcard canvas<br/>
configure element properties and style elements in the flexcard<br/>
embed a child flexcard inside a parent flexcard<br/>
configure a flyout to display additional information on a flexcard<br/>
configure conditions that determine when different flexcard states display<br/>
build a lightning console to display generated flexcard lightning web components <br/><br/>

Here are additional things to have learned in VPE3: (Exercise Guide)<br/>
Use the data source wizard to select and configure a data source<br/>
Navigate the flexcard designer's UI <br/>
Drag and drop elements onto a flexcard canvas <br/>
Use the menu element to display a list of actions on a flexcard <br/>
Use a Vlocity Action to link an OmniScript to a flexcard <br/>
Use an OmniScript Action to link an OmniScript to a flexcard <br/>
Make a collapsible block <br/>
Clone a flexcard <br/>
Launch an OmniScript in a modal window <br/>
Configure a field to display a date properly <br/>
Push data from a parent flexcard to a child flexcard <br/>
Configure a data source for displaying external data <br/>
Add an image to a Flexcard <br/>
Create a table <br/>
Configure a Flyout action <br/>
Configure conditions that determine when different flexcard states display <br/>
Build a lightning console <br/><br/>


Flexcards are actually lightning web components! <br/>
Flexcards are able to have different states depending on a condition <br/>
Flexcards are also able to conditionally display or not <br/>
Flexcards are able to be embedded inside an omniscript? The flexcard is able to get data from the omniscript. <br/>
Flyouts is basically a flexcard the appears when an action is clicked on the flexcard <br/><br/>

Flexcard teamMasterAccount was created. It used an integration procedure (teamGetMasterAccountDetails)that returned back stub data(Set Values). JSON value was filtered for accounts only. <br/>

### (FlexCards) exam expectations - 20%
Given a set of requirements, determine appropriate data sources, fields, and actions to configure on flexcards <br/>
Explain the JSON data structure that supports FlexCards <br/>
Given a set of functional requirements for FlexCards, match these requirements to FlexCards functionality. <br/>
I do note nothing tested on classic cards. On another note, there are 60 questions with a pass score of 70%. There should be about 12 questions on flexcards. <br/><br/>






## Notes from documentation

IDX Workbench with vsCode is preferred over Salesforce DX because then it's possible to migrate vlocity components and compare source and target files. It's a tool for migration. IDX Workbench with visual studio though or with Salesforce DX vsCode...<br/>

The following migrations are supported:<br/>
One Vlocity org to another<br/>
Vlocity org to git repository <br/>
git repository to vlocity org <br/>
vlocity process library to vlocity org<br/>
JSON file to a git repository or vlocity org <br/><br/>

In IDX, you define a repository or source org, the target org or repository, and the components to be migrated. This means that I use vsCode to push my code to git. From there I connect git as a source and a vlocity org as the target. <br/>
