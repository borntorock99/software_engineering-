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



2 Overall Description  
This section includes details about what is and is not expected of the BECS system in addition to which cases are intentionally unsupported and assumptions that will be used in the creation of the BECS system. 
 
2.1 	Product Perspective 
BECS is an online bookstore website which supports a number of functions for both the consumer and store's management.  
 
The website must be available to anyone using the Computer Science Department’s provided computer resources in the MSU Engineering Building and as such must work correctly in both Internet Explorer and Mozilla Firefox. As stated by the customer, there are no hardware or software requirements beyond these including, but not limited to, memory or specific software packages that need to be utilized nor software packages that need not be utilized. 
 
2.2 	Product Functions 
BECS will provide a number of functions; each is listed below. 
•	Maintain data associated with the inventory (a collection of books) 
•	A book has a title, author and price 
•	The inventory also keep track of the stock/quantity of each book 
•	Maintain records for many customers 
•	A customer can be either a member or non-member. 
•	A customer has a username (unique across all users), password (no restrictions), email address (no restrictions), and postal address (unverified.) 
•	Anyone may sign up for a customer account. 
•	Allow any customer to become a member. 
•	Show a listing of available books 
•	Books are to be displayed in ascending alphabetical order by title. 
•	Each book will list the following from left to right 
•	Title 
•	Author 
•	Price 
•	One exception is if the manager has already specified a stop-order for this book. 
•	Every book must either have stop-order enabled or disabled 
•	Allow manager to update stock quantities 
•	Allow manager to change any book's price 
•	Allow manager to view transaction logs 
•	Allow manager to create promotions 
•	A promotion is a percentage discount that can be applied to an entire order 
•	Promotions may only be used by member customers 
•	A promotion has an expiration date specified by the manager 
When a promotion is created, it is emailed to all member customers via the email address on record 
 
2.3 	User Characteristics 
The typical BECS user is simply anyone that has access to the Internet and a web browser in the computer science department at Michigan State University. It is assumed that the user is familiar enough with a computer to operate the browser, keyboard and mouse and is capable of browsing to, from and within simple websites [1]. 
2.4 	Constraints 
As stated by the customer, security is not a concern for this system. The database may store passwords in plain text and there doesn't need to be a password recovery feature nor lockout after numerous invalid login attempts. As such, the system may not work correctly in cases when security is a concern. These cases include those listed above in addition to lack of an encrypted connection when sending credit card information and forcing users to use “strong” passwords. A strong password is a password that meets a number of conditions that are set in place so that user's passwords cannot be easily guessed by an attacker. Generally, these rules include ensuring that the password contains a sufficient number of characters and contains not only lowercase letters but also capitals, numbers, and in some cases, symbols. 
 
The system may not behave correctly when used with Internet browsers other than Firefox and Internet Explorer. 
 
SCR 	"Software Cost Reduction (SCR) is a set of techniques for designing software systems developed by David Parnas and researchers from the U.S. Naval Research Laboratory beginning in the late 1970s." [7] 
Mode Class 	"A mode class is a finite state machine, with states called system modes" [8] 
System State 	The current state or mode that the system is in. The system must be in exactly one state at any moment in time. 
Event 	An event is any action that can trigger an action within the software system. Examples include but are not limited to changing values of variables or user-triggered events. 
Event Notation 	We may need to refer to both the old and new value of a 
	variable:  
Used primed values to denote values after the event  
@T(c) ≡ ¬c ^ c’ e.g. @T(y=1) ≡ y<>1 ^ y’=1  
@F(c) ≡ c ^ ¬c’  
A conditioned event is an event with a predicate  
@T(c) WHEN d ≡ ¬c ^ c’ ^ d [8] 
Controlled Variable 	A variable whose value can change throughout the lifetime of the system and whose value is critical and must be maintained correctly. 
Mode Transition 	When the mode (state) changes from one mode (described as the old mode) to a new mode. 
Mode Class Table 	Table consisting of a list of modes that the system can be in, modes that can be transitioned to, and the conditions required for the transition to occur. The table if formatted such that the first column lists the current mode (old mode) and the last column lists the new mode. The columns between the first and last columns each describe a specific event. 
Event Table 		An event table illustrates how an input event can affect a controlled variable. The first column shows modes and the 	
		last row shows the values that the controlled variable will be set to. The remaining cells are conditions required for a mode to affect the value of a controlled variable. 	
Condition Table 	A condition table shows the conditions (one of which must be met) in order for a controlled variable to be set to some specified value. The first column lists modes and the last row names the controlled variable and the values it is set to. 
 
 
 
 
 
Condition Table 	 	 
Mode 	Conditions 
AddPromotion 	TRUE 	FALSE PromotionAdded 	TRUE 	FALSE 
 
Mode Class 	 	 	 	 	 
Old Mode 	Login 	IsManager 	IsCustomer 	Logout 	New Mode 
UserLoggedOut 	@T 	t 	- 	- 	ManagerLoggedIn 
  	@T 	- 	t 	- 	CustomerLoggedIn 
ManagerLoggedIn 	- 	- 	- 	@T 	UserLoggedOut 
CustomerLoggedIn 	- 	- 	- 	@T 	UserLoggedOut 
 
Event Table 	 	 
@T(User::Login() == UserLoggingIn 	TRUE) 	never 
UserLoggingOut 	never 	@T(Logout() == 
TRUE) 
User::LoggedIn 	TRUE  	FALSE 
Condition Table 	 	 
Mode 	Conditions 	 
UserLoggedOut 	FALSE 	TRUE 
ManagerLoggedIn 	TRUE 	FALSE 
CustomerLoggedIn 	TRUE 	FALSE 
UserLoggedIn 	TRUE 	FALSE 
 
2.5 	Assumptions and Dependencies 
Client: 
We have assumed that all of the computer systems in the Engineering building labs are in proper working condition and that the user is capable of operating these system's basic functions including but not limited to being able to power on the system, login and open either Internet Explorer or Mozilla Firefox, and navigate the browser to the address of this BECS website. 
 
Provider: 
We have assumed that the BECS will be running on a properly working web server and database system with an Internet connection that allows this system to perform all communications with clients.  
 
Assumptions: 
•	There is no need for anyone to be able to order more than a single copy of a book (or any item) in a single transaction. 
•	The manager account’s username and password maybe hard coded. 
•	The manager cannot be a customer. 
•	Any user cannot edit their account information. 
 
2.6 	Approportioning of Requirements 
As stated by the customer, security is not a concern of this project. As such, it is beyond the scope of this system to encrypt personal user data, encrypt credit card information, prevent unauthorized login attempts, or any other concern of this nature. Additionally, the system is not responsible for the following: 
 
•	Verifying that credit card information is valid 
•	Verifying the email address provided by a user 
•	Storing additional information about a book beyond simply the title, name of author, and price 
•	Allowing users to edit their account details (username, password, mailing address, etc) 
Additionally, the system may need to later be extended to provide additional functions. One such example is added support for visually impaired users. In many cases a screen reading program is used and ensuring that page-layout reads from top-left to bottom-right in a logical manner would be required. 




3 Specific Requirements  
1.	Restrictions 
1.1.	User Side 
1.1.1.	Software 
1.1.1.1.	Internet Explorer or Mozilla Firefox 
1.1.2.	Hardware 
1.1.2.1.	Computer Science Department Laboratory Terminal 
1.2.	System Side 
1.2.1.	Software 
1.2.1.1.	Web-based application 
1.2.1.2.	Database information storage system 
2.	Data Structure 
2.1.	Book has these attributes 
2.1.1.	Unique ID (auto-increment starting at 1) 
2.1.2.	Title 
2.1.3.	Author 
2.1.4.	Price 
2.1.5.	Reorder Threshold 
2.1.6.	Stop-order Boolean value 
2.1.7.	Stock 
3.	System 	 
3.1.	Browse Inventory 
3.1.1.	Organization 
3.1.1.1.	Items Listed on single page 
3.1.1.2.	Items shown in tabular format 
3.1.1.3.	Each Item listing contains 
3.1.1.3.1.	Title 
3.1.1.3.2.	Name of Author 
3.1.1.3.3.	Price 
3.1.1.4.	Listing sorted by Ascending item Title 
3.1.1.5.	No individual Item pages 
3.1.2.	Interaction 
3.1.2.1.	Each Item has checkbox to mark selection 
3.1.2.2.	Single button to add all selected items to Shopping Cart 
3.2.	Search Inventory 
3.2.1.	Search available only by Title of book 
3.2.2.	Search is exact-match only 
3.2.2.1.	A text box to hold the credit card number 
3.2.2.2.	A button to complete the order 
3.2.3.	Order details sent via email after the checkout has completed  
3.2.4.	On order completion the inventory is decremented based on items purchased by user 
3.3.	Authentication System 
3.3.1.	User Levels 
3.3.1.1.	Manager (single, hardcoded user, no orders) 
3.3.1.2.	Customer (unlimited, open creation, unlimited orders) 
3.3.2.	Account Creation 
3.3.2.1.	Everyone is allowed to create an account 
3.3.2.2.	Required Information 
3.3.2.2.1.	Listed in section 2.2 
3.3.3.	Account Modification 
3.3.3.1.	Users are not able to modify any aspect of their account after creation 
(“it would be nice but not needed”) 
3.3.4.	Login and Logout 
3.3.4.1.	There is no lost-password recovery 
3.3.4.2.	Logging in allows one to logout 
3.3.4.3.	Logging in allows checkout 
3.3.4.4.	There is a 30-minute session time out after which a logged in user will be logged out automatically. 
3.4.	Promotions 
3.4.1.	Specifications 
3.4.1.1.	Applies to entire order 
3.4.1.2.	Percentage-off type promotion (x% off entire order) 
3.4.1.3.	Expiration occurs at manager specified date 
3.4.1.4.	Multiple coupons cannot be applied to same order 
3.4.1.5.	Non-member users cannot apply promotions to order 
3.4.2.	Creation 
3.4.2.1.	Promotion created by manager 
3.4.2.2.	Each promotion has a unique identifying number (can be auto generated) 
3.4.2.3.	Email containing promotion sent to all member users of the BECS system 
	3.7.2.4. 	 
3.4.3.	Deletion 
3.4.3.1.	Promotions are auto-deleted when the expiration date has passed 
3.5.	Order Logging 
3.5.1.	Specifications 
3.5.1.1.	Required Information: 
3.5.1.1.1.	Listed in section 2.4 
3.5.1.2.	A manager can view all past transactions from all users 
Order log entries are generated when a user successfully checks out their shopping cart 
 


4 Modeling Requirements  
 
Use Case Diagram 
 
The purpose of this diagram is to demonstrate how objects will interact with BECS and map out the basic functionality of the system.  Below is a list of the elements that you will see in the diagram on the next page as well what is included in the use case templates that follow. 
 
Actors 	Shown in the diagram as stick figures with a name underneath.  They represent elements that will be directly interacting with the system. 
Use Cases 	Oval shapes that have their names in the center.  These represent direct functionality within the system that must be implemented. 
Interactions 	Lines that connect the actors with the different Use Cases.  These show that there is some form of direct interaction between the actor and that specific functionality. 
Includes 	Dotted lines labeled “<<include>>” that connect two use cases and have an arrow pointing towards one.  This means that the use case without the arrow calls on the functionality of the use case with the arrow. 
Extends 		Dotted lines labeled “<<extend>>” that connect two use 	
		cases and have an arrow pointing towards one.  This means that the use case without the arrow takes all of the functionality of the use case with the arrow and adds extra functionality. 	
The System Boundary 	The large rectangle that contains the Use Cases.  Everything within the rectangle is what the system is responsible for implementing 
Use Case Template 		Describes the basic functionality and features of each use case and the can be found in the pages following the use case diagram. 	
Type 	A field in the use case template that states whether or not the use case is directly interacted with by an actor (Primary) or not (Secondary) as well as whether or not it is essential to having a functioning system. 
Cross Ref 	A field in the use case templates that states which one of the original requirements that particular use case satisfies. 
Use-Cases 	A field in the use case templates that state which other use cases must be executed prior to that particular use case. 

