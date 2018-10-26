# software_engineering-
online book store (SRS) -- report



1 Introduction  
The Software Requirements Specification is designed to document and describe the agreement between the customer and the developer regarding the specification of the software product requested  Its primary purpose is to provide a clear and descriptive “statement of user requirements” that can be used as a reference in further development of the software system. This document is broken into a number of sections used to logically separate the software requirements into easily referenced parts.  
 
This Software Requirements Specification aims to describe the Functionality, External Interfaces, Attributes and Design Constraints  imposed on Implementation of the software system described throughout the rest of the document. Throughout the description of the software system, the language and terminology used should unambiguous and consistent throughout the document. 
1.1 	Purpose 
Defining and describing the functions and specifications of the Book E-Commerce System (BECS) is the primary goal of this Software Requirements Specification (SRS). This Software Requirements Specification illustrates, in clear terms, the system’s primary uses and required functionality as specified by our customer. 

 
1.2 	Scope 
The software system being produced is called Book E-Commerce System or BECS. It is being produced for a customer interested in selling books via the Internet. This system is designed to “provide automation support” [2] for the process of placing books for sale on the Internet and facilitating the actual sale. This system is largely cross-platform and is available to anyone using the Computer Science Department’s provided computer resources in the MSU Engineering Building. The system will be run on a central server with each user having a remote user interface through a web browser to interact with it The Book E-Commerce System will allow any user to create an account to become a customer. The customer, through the process of account creation, will have the option to become a member of the site. The system will allow customers to browse, search, select, and add books to a shopping cart. Then, provided they have books in their shopping cart, check out books in shopping cart and decrement the stock that the inventory the system maintains. 
 
1.3 	Definitions, acronyms, and abbreviations 
BECS 	Book E-Commerce System 
Barcode 	A unique identifier assigned to single items 
Book 	An instance of an Item that has these additional attributes: Title, Author 
Button 	A user interface element that allows a User to click and inform the system to take an action 
Checkbox 	A user interface element that allows a User to inform the system that he/she selected a particular item 
Checkout 	The process a Customer goes through to purchase an Item 
CRUD 	Create, Retrieve, Update, Delete 
Customer 	A person that is a user of the system but has created an account 
Inventory 	An object that holds items available for purchase by the Customer 


Item 	An individual entity in the inventory which has several descriptive attributes:  
	Barcode, Price, Reorder Threshold, Stock 
Manager 	A single person that has the ability to create, retrieve, update and delete items in the store. This person cannot simultaneously act as a Customer and Manager. 
Member 	A person that is a customer of the system and has requested to be sent promotions 
Promotion 	An item-wide percentage-off price discount applied to a Member's shopping cart 
Reorder 	The system process that automatically orders new stock of an item 
Reorder Threshold 	The numeric value of an item's stock that must be reached before the system will order additional quantities of the item 
Session 	The time which a User is actively using the system 
Shopping Cart 	An object that lists a Customer's selected Items, their applied promotions and gives them an option to check out 
SRS 	Software Requirements Specification 
Stock 	The quantity of any particular item the inventory has on hand 
Text Box 	A user interface element that allows a User to input text to the system 
Transaction 	The information related to a customer's purchase that is logged 
User 	The person who operate the software product. 
 
1.4 	Organization 
This Software Requirements Specification document is divided in to multiple subsections. The first section includes explanations of the Purpose, Scope and Organization of the document. The first section also handles the description of projectspecific words, acronyms and abbreviations that will be used in the document. The second section of the document is separated into the following five different sections, each detailing specific details of system uses and their corresponding actions: Product Perspective, Product Functions, User Characteristics, Constraints, Assumptions and Dependencies, Apportioning of Requirements




