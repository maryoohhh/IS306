# IS306 Data Management Communication and Networking

Chapter 1: Data and the Enterprise
-----------------------------------------

**Information is a key business resource**

<dl>
    <dt>Information</dt>
    <dd>is a business resource that is used in every aspect of a business</dd>
    <dd>supports day-to-day operational tasks and activities</dd>
    <dd>enables the routine administration and management of he business</dd>
    <dd>supports strategic decision making and future planning</dd>
</dl>

**The relationship between information and data**

> Information is *data placed in context*.

This implies that some information is the result of the the translation of some data using some processing activity, and some communication protocol, into an agreed format that is identifiable to the user. In other words, if data has some meaning attributed to it, it becomes information.

<dl>
    <dt>Data</dt>
    <dd>found in ISO/IEC 2382-1.1993 (Information Technology -Vocabulary - Part 1: Fundamental Terms)</dd>
    <dd>states that it is a re-interpretable representation of information in a formalised manner suitable for communication, interpretation, or processing</dd>
    <dd>covers all forms of data but, importantly, includes data held in information systems used to support the activities of an organization of all levels: operational, managerial, and strategic</dd>
</dl>

![Figure 1.1 The relationship between data and information](https://github.com/maryoohhh/IS306/blob/master/Images/Figure1-1.png)

**The importance of the quality of data**

>Information must be up to date, complete, sufficiently accurate for the purpose it is required, unambiguously understood, consistent, and available when it is required.

<dl>
    <dt>Good quality data</dt>
    <dd>data that is accurate, correct, consistent, complete, and up to date</dd>
    <dd>meaning must also be unambiguous</dd>
</dl>

**The common problems with data**

>Problems are generally caused by a combination of the proliferation of duplicate, and often inconsistent, occurrences of data, and the misinterpretation and misunderstanding of the data caused by the lack of a cohesive, enterprise-wide regime of data definition.

>Whenever it is possible for any item of information to be held as data more than once, there is a possibility of inconsistency.

Possible reasons for sharing information:
* when central reference data is used by independent operational units, such as product codes and product prices;
* when public domain datatypes are used and exchanged, for example when publicly available statistical data sets are to be used;
* when operational results need to be collated across several profit centres, for example to collate or compare the sales figures from stores within a supermarket chain;
* when the output from one system forms the input to another, for example the output of a forecasting systems is used by another system to determine resource and budget implications;
* when application systems performing a similar function for district autonomous units are required to harmonise their data to permit close collaboration, for example the command and control systems for the police, fire, and ambulance services need to *work together* in the event of an emergency

<dl>
    <dt>Database</dt>
    <dd>designed to provide effective and efficient suuport to the business are or the function that the information system is being designed to support by meeting the immediate data requirements for the business are or function as they are understood by the database designer</dd>
    <dd>very rare for a wider view of current or future data requirements to be taken</dd>
</dl>

**An enterprise-wide view of data**

> One of the difficulties often faced by a central team resposible for managing the data for the whole organization is bridging the gap between different departmental views. This requires patience and tact. It certainly requires authority, or access to appropriate authority, as the implementation of a solution may well involve cooperation with several managers within organization.

<dl>
    <dt>Enterprise Resource Planning (ERP)</dt>
    <dd>software that is supposed to provide a single integrated database that meets an organization's entire data needs fot the management of its resources</dd>
</dl>

**Managing data is a business issue**

Special responsibilities within organization:
* The finance department has special responsibilities for managing the organization's money including the allocation of budgets, managing investments, and accounting.
* The personnel department has special responsibilities for managing the organization's employee base including the provision of advice on legislation affecting personnel issues and the recruitment of staff.
* The estates department has special responsibilities for manging the building used by the organization including ensuring that the buildings meet legal requirements in respect of health and safety issues, buying, selling, and leasing of buildings and ensuring that the estate is adequately insured.
* The stores and maintenance department has special responsibilities for managing the organization's equipment including the provisions of a central purchasing function, the accounting for the equipment in use and the storage of equipment until it is required for use.
* The IT or IS department has special responsibility for data and information including the physical storage, distribution, security, backup, and archiving of data.

Chapter 2: Database Development
---------------------------------

**File Systems**

Before the advent of databases, any data that was required by an application program was stored in specially constructed files designed for and associated with the application programs. Each of these files would contain many records, with each record being collection of data values held in fields within the record. Each application programs becomes closely coupled to its data structure.

**Database Approach**

<dl>
    <dt>Database</dt>
    <dd>an organised way of keeping records in a computer system</dd>
    <dd>provide a means of overcoming the problems caused by storing data in files that are closely coupled with applications program</dd>
</dt>

![Figure 2.1 A model of a database system](https://github.com/maryoohhh/IS306/blob/master/Images/Figure2-1.png)

Model shows a number of user processes interacting with the general-purpose DBMS. It also shows that the DBMS interacts with two 'datastores', physical storage areas for data in files. One datastore is the database itself, providing persistent storage of the data required by the various user processes. The other datastore contains the data definition.

<dl>
    <dt>Schema</dt>
    <dd>set of data definitions</dd>
    <dd>contains the specification of the properties of all data in the associated database</dd>
    <dd>used by the DBMS to determine how the data in the associated database is to be processed</dd>
    <dd>is independent of the DBMS and the user processes and is normally expressed in terms of easily understood conceptual constructs</dd>
</dt>

> The data definitions are, therefore, not embedded in the application programs.

Advantages of database approach assuming database are properly designed and used:
* **Data independence** - there is a layer of software, the database management system, between the users and their applications and the stored data; this layer of software insulates the users from changes to the way that data is physically stored.
* **Integration and sharing of data** – a database can store all the data needed by many different business areas so that many users from different business areas can access the same database.
* **Consistency of data** – with the data being integrated in a database, the data inconsistency problems associated with separate application-specific data files are prevented.
* **Minimal data redundancy** – with many applications sharing an integrated set of data, the redundancy of data caused by duplication is avoided; there may, however, be some planned and controlled data duplication to meet specific requirements.
* **Uniform security and integrity controls** – since the controls necessary to maintain the security and integrity of the data are handled by the database management system software, these controls are applied uniformly to all users of the database. Security and integrity are explained in more detail in Chapter 8.
* **Data accessibility and responsiveness** – within the database there may be many different ways to access any required set of data; it is even possible to answer ad hoc queries in addition to the pre-planned queries encoded in the application programs.
* **Ease of application development and reduced program maintenance** – the application developers and those responsible for the future maintenance of those applications do not need to know and understand the way that the data is physically stored; instead, they only need to understand the conceptual constructs used in the schema.

Common functions that should be provided by all database management systems:

* **Data definition** – the ability to use easily understood conceptual constructs to define the way that the data is to be organised and structured within the database.
* **Constraint definition and enforcement** – the ability to define semantic constraints on the data (for example restrictions that are to be applied to data values) and then to enforce those constraints universally.
* **Access control** – the ability to define the rights of users to access all or some of the data and to prevent access by users without the appropriate rights.
* **Data manipulation** – the ability to retrieve and update data as well as the ability to perform calculations and structuring for presentation purposes.
* **Restructuring and reorganisation** – the ability to change a database in some way, either to logically restructure – that is, to change, add or delete some element of the data structure – or to physically reorganise how the data is stored – for example to add an index.
* **Transaction support** – the ability to ensure that a database is in a consistent state both before and after a transaction has been completed.
* **Concurrency support** – the ability to allow many user processes – and, therefore, many users – to access a database at the same time without conflict or interference.
* **Recovery** – the ability to return the database to a usable state after a hardware or software failure, including the return of the database to a consistent state if a transaction fails to complete.

> The first of these functions of a database management system is the ability to define the way that the data is to be conceptually organised and structured within the database. This is the ability to define the database schema.

**The three-level schema architecture**

![Figure 2.2 The three-level schema architecture](https://github.com/maryoohhh/IS306/blob/master/Images/Figure2-2.png)

The **schema at the logical level** is the central, and main, component of the architecture. It defines the properties of all the data. It includes the data definitions and the associated constraints, using the appropriate conceptual constructs – tables, object classes and so forth – appropriate to the database management system being used.

The **schema at the internal level** defines how the database is physically stored in files and how these files are accessed. The addition of indexes to speed retrieval may be viewed as an addition to the internal or storage schema.

**Each schema at the external level** defines the data required to support one or more user processes. Each schema at the external level may be viewed as a subset or an abstraction of the schema at the logical level, although it is not necessary for the same conceptual constructs to be used at both the logical and external levels.

<dl>
    <dt>Physical data independence</dt>
    <dd>separation between the schema at the logical level, where the data is conceptually visualised – tables and columns, object classes and so forth – and the schema at the internal level – where the way that the data is actually stored is known – provides a level of data independence</dd>
</dl>

**An overview of the database development process**

An important part of the overall development process is to understand and document those requirements so that the information system that is developed and eventually delivered does in fact help the users by meeting their requirements.

So for each system there are three facets that need to be considered: the information (or its associated data), the processes and the timing or sequencing.

![Figure 2.3 A simplified view of the database development process](https://github.com/maryoohhh/IS306/blob/master/Images/Figure2-3.png)

<dl>
    <dt>Physical design</dt>
    <dd>developing a schema using the appropriate conceptual constructs for the proposed database management system</dd>
    <dt>Script</dt>
    <dd>a listing in plain text of the commands needed by the database management system to build the database</dd>
    <dt>Small system</dt>
    <dd>a system to support a small, clearly defined community of users</dd>
    <dd>a data model developed purely from the perspective of the small part of the business that the information system will be developed to support</dd>
    <dd>takes no account of any corporate need to share information across the enterprise</dd>
    <dt>Entity</dt>
    <dd>an instance of an entity type, is usually defined as ‘something of significance to the business about which information is to be recorded’</dd>
    <dd>‘something’ may be physical, such as an employee or an item of equipment, or it may be conceptual, such as an order (although there may be a physical representation of the order on a piece of paper)</dd>
    <dd>may even be details of the specification of something else about which information is to be recorded</dd>
    <dt>Attribute</dt>
    <dd>a ‘detail that serves to qualify, identify, classify, quantify or express the state of an entity’</dd>
    <dt>Relationship</dt>
    <dd>is simply defined as ‘an association between two entity types’</dd>
    <dd>may exist between instances of the same entity type known as **recursive relationship**</dd>
    <dd>‘an association between two entity types, or between one entity type and itself’.</dd>
</dl>

![Figure 2.4 A conceptual data model diagram](https://github.com/maryoohhh/IS306/blob/master/Images/Figure2-4.png)

For example, consider the relationship between property and employee that is introduced in Figure 2.4. Reading this relationship from bottom to top – say from property to employee – we have the sentence:

> Each **PROPERTY** <ins>may be</ins> home address for <ins>one or more</ins> **EMPLOYEES**

The use of text formatting, bold small capitals, underlining and italics, to indicate the different elements of the sentence, which is constructed using the following rules:

* The word ‘Each’ is used because the box with the word ‘property’ inside it is an entity type (that is, it represents all instances of the type – all the properties) but we want to refer to a single instance of the type (that is, a single property).
* ‘Each’ is followed by the name of the entity type at the end from which we are starting the sentence – in this case **PROPERTY**.
* The term ‘<ins>may be</ins>’ is used because not every property has to be the home address for an employee – this is represented on the diagram by a dotted line at the **PROPERTY** end of the relationship; a dotted line is always read as ‘<ins>may be</ins>’.
* ‘home address for’ comes from the name of the relationship at the **PROPERTY** end of the relationship.
* The term ‘<ins>one or more</ins>’ is used because there is an inverted three-pronged arrowhead (known as a crow’s foot) at the **EMPLOYEE** end of the relationship – a crow’s foot is always read as ‘<ins>one or more</ins>’.
* The sentence ends with the name of the entity type at the end of the line; we make it plural so that the sentence reads easily, in this case **EMPLOYEES**.

Each relationship should also be read in the opposite direction. Reading the relationship from top to bottom – from employee to property – we have the sentence:

> Each **EMPLOYEE** <ins>must be</ins> resident at <ins>one and only one</ins> **PROPERTY**

This sentence is constructed as follows:
* ‘Each’ because we want to refer to a single instance of the type.
* **EMPLOYEE** from the name of the upper entity type.
* ‘<ins>must be</ins>’ because every employee has to be resident at a property (their home address) – this is represented on the diagram by the solid line at the **EMPLOYEE** end of the relationship and a solid line is always read as ‘<ins>must be</ins>’.
* ‘resident at’ comes from the name of the relationship at the employee end of the relationship.
* The term ‘<ins>one and only one</ins>’ is used because there is no crow’s foot at the far end, the **PROPERTY** end, of the relationship – the absence of a crow’s foot is always read as ‘<ins>one and only one</ins>’.
* **PROPERTY** comes from the name of the lower entity type.

The **ASSIGNMENT** entity type has a relationship to the **PROJECT** entity type as well as to the **DEPARTMENT** entity type. These two relationships are crossed by an arc at the **ASSIGNMENT** entity type end, indicating that they are mutually exclusive as far as **ASSIGNMENT** is concerned.

These mutually exclusive relationships are read as follows:

> Each **ASSIGNMENT** <ins>must be</ins> to <ins>one and only one</ins> **DEPARTMENT** OR to <ins>one and only one</ins> **PROJECT**

> Each **DEPARTMENT** <ins>may be</ins> staffed through <ins>one or more</ins> **ASSIGNMENTS**

> Each **PROJECT** <ins>may be</ins> staffed through <ins>one or more</ins> **ASSIGNMENTS**

**Relational data analysis**

Another much more formal approach to the analysis of data requirements that relies on there being some document or other existing record (such as a program file) that lists the items of data that are to be recorded which is then analysed using this process.

In the relational model of data, the data is recorded in a set of linked relations. The relation used as the main concept of the model is not the same as the relationship in a conceptual data model and it is inappropriate to use these two terms interchangeably in the data/database community, despite the fact that they are used interchangeably in general usage.

A relation has two parts – a heading and a body.

<dl>
    <dt>Heading</dt>
    <dd>consists of a set of attributes; the attribute in the relational model of data is a similar concept to the attribute we saw in the conceptual data model, although there are some differences</dd>
    <dt>Body</dt>
    <dd>is a set of elements that are called tuples</dd>
    <dt>Tuple</dt>
    <dd>a set of data values, one value for each of the attributes defined in the relation heading</dd>
    <dd>a set of attribute-name:attribute-value pairs</dd>
    <dd>et of values from which the individual values of an attribute may be taken is known as a domain</dd>
</dl>

![Figure 2.5 A relation shown as a table](https://github.com/maryoohhh/IS306/blob/master/Images/Figure2-5.png)

There are a number of rules associated with relations and these are:

* There is no significance to the order of the attributes within the relation heading; this is because the relation heading is a set of attributes and one of the properties of a mathematical set is that the elements of the set are unordered. The fact that in Figure 2.20 the attributes are arranged in a particular order from left to right is purely for presentational purposes; that order has no significance to the relation that Figure 2.20 is representing.
* Similarly, since the body of the relation is a set of tuples, there is no significance to the order of the tuples within the body of the relation. Again the fact that in Figure 2.20 the tuples are arranged in a particular order from top to bottom is purely for presentational purposes.
* Attributes within the relation heading should be unique; that is, there should be no duplication of attribute names within a relation.
There should be no attributes whose values can be derived from the values taken by other attributes, whether those attributes are in the same relation or in another relation.
* Relations have unique identifiers known as primary keys; the primary key comprises the attribute, or combination of attributes, whose values are the minimum required to uniquely identify each instance of the relation. The primary key of the relation represented in Figure 2.20 is the **Person Identifier** attribute; each person has a person identifier that is managed to be unique.
* No two tuples in a relation may have the same value of primary key. If the **Person Identifier** attribute is the primary key of the relation representing persons, no two persons can have the same personal identifier.
* In each tuple each part of the primary key must have a value. Every person must have a person identifier.
y The attributes of a relation represent characteristics that are determined by the primary key; that is, they describe the ‘thing’ defined by the primary key. The name of the employee with personal identifier P6793 is Barbara Watson, her date of birth is 6 December 1952 and her national insurance number is AA756242C.
* In any tuple no attribute may take more than one value; that is, each attribute is single-valued – there are no multiple-valued attributes within a relation.

**Normalisation**

> We use the process of relational data analysis – the development of a set of relations in third normal form – to develop a conceptual database design in which there will be no update anomalies when data is input into the database or later updated.

In general terms this means that for any piece of information there is only one place in the database where the data representing the information can be stored and that place is unambiguously recognised. This process of relational data analysis allows us to confirm that we are associating attributes that are all about one thing (person, product and so on) or concept (promotion, order, account, transaction and so on) of interest to the business.

**First normal form**

> The first stage in our normalisation process is to move from this un-normalised form to produce a set of relations that are in first normal form (often abbreviated to 1NF).

A relation is in first normal form if all the values taken by the attributes of that relation are atomic or scalar values – we say that the attributes are single-valued. This is to comply with the rule that there must not be any multiple-valued attributes in a relation.

![Figure 2.6 The first normal form relations](https://github.com/maryoohhh/IS306/blob/master/Images/Figure2-6.png)

**Second normal form**

> The next stage of our relational data analysis process is to move our relations to second normal form (2NF).

For a relation to be in second normal form it has to be in first normal form and, in addition, it must meet the condition that every attribute that is not part of the primary key is dependent on the whole of the primary key. More formally a relation is in second normal form if and only if it is in first normal form and every non-key attribute is irreducibly dependent on the primary key.

![Figure 2.7 The second normal form relations](https://github.com/maryoohhh/IS306/blob/master/Images/Figure2-7.png)

**Third normal form**

> We now need to move our relations from second normal form to third normal form (3NF).

For a relation to be in third normal form it has to be in second normal form and also has to meet the condition that every attribute that is not part of the primary key is not dependent on an attribute that is also not part of the primary key. More formally a relation is in third normal form if and only if it is in second normal form and every non- key attribute is nontransitively dependent on the primary key.

![Figure 2.8 The third normal form relations](https://github.com/maryoohhh/IS306/blob/master/Images/Figure2-8.png)

**Further normal forms**

<dl>
    <dt>Candidate keys</dt>
    <dd>all possible primary keys</dd>
    <dd>choice of which candidate key to use as a primary key is sometimes quite arbitrary, although there is often a clear preferred option</dd>
    <dt>Alternate keys</dt>
    <dd>candidate keys not selected to be the primary key</dd>
</dl>

> Boyce–Codd normal form is really just a stricter form of third normal form.

For most practical purposes Boyce–Codd normal form and third normal form are equivalent. The only exceptions occur when there are two or more candidate keys, where those candidate keys are composed of more than one attribute and where the multi-attribute keys overlap (that is, they share a common attribute). In this situation it is possible for update anomalies to occur at third normal form, but not if the relations are restructured to be in Boyce–Codd normal form.

![Figure 2.9 The employee interview relation](https://github.com/maryoohhh/IS306/blob/master/Images/Figure2-9.png)

This relation has three candidate keys as follows:
* **Interviewee Payroll Number** and **Interview Date**;
* **Interviewer Payroll Number**, **Interview Date** and **Interview Time**;
* **Room Number**, **Interview Date** and **Interview Time**.

![Figure 2.10 The equivalent Boyce-Codd normal form relations](https://github.com/maryoohhh/IS306/blob/master/Images/Figure2-10.png)

The first of these two relations has the following candidate keys:
* **Interviewee Payroll Number** and **Interview Date**, allowing us to determine the interview time and the payroll number of the interviewer;
* **Interviewer Payroll Number**, **Interview Date** and **Interview Time**, allowing us to determine the payroll number of the interviewee.

<dl>
    <dt>Surrogate keys</dt>
    <dd>many database developers prefer to use a meaningless primary key instead of constructing a primary key from real-world attributes such as **Payroll Number**, **Surname**, **Other Names** and **Date of Birth**</dd>
    <dd>if surrogate keys are to be used, it is still sensible to use relational data analysis to check normalisation using candidate keys involving appropriate real-world attributes</dd>
</dl>

**Roles of data model**

> Conceptual data models can be developed to understand the information requirements of a business and to form the basis for a physical database design to support the business.

A conceptual data model that is to be used to understand the information requirements of a business, or a business area, should be the result of the analysis of those information requirements alone. No design considerations should be included in the model. The model should be the result of pure analysis, untainted by design.

**Physical database design**

This ‘physical database design’ process has two stages:
* **first-cut database design** - the aim is to use the conceptual constructs of the logical-level schema of the target database management system to develop a design that matches the conceptual data model as closely as possible
* **optimised database design** - may be necessary for the database designer to enhance or move away from the first-cut design to improve the performance of the database

The two main strategies for improving performance of a database are to:
* make use of the built-in facilities of the database management system;
> Two facilities provided by most database management systems are the ability to cluster data and the ability to create indexes.

**Data clustering** means arranging data on the disk in such a way that logically related data is placed as closely together as possible. This improves performance because fewer disk access requests are required to answer queries on the database or to update data.

An **index** provides the database management system with an alternative way to access data other than searching through all the physical records associated with a particular logical table. A database index is analogous to the index at the back of this book. It enables the database management system to know where to go to access any particular piece of data. An index may be built on a single column or on multiple columns from the same table. Using an index improves retrieval performance by reducing the number of disk accesses required to query the data. Database update is, however, slowed down if data is indexed; each database update requires updating the index (which normally requires some restructuring of the complete index) as well as updating the main data file.

> Changes to the clustering of data and the addition or removal of indexes are the equivalent of altering the schema at the internal level of the three-level architecture.

These changes can be made without affecting the schema at the logical level and without affecting the application processes.

* compromise on the design of the logical schema
> A compromise to the design of the logical schema affects data independence. Such a compromise is often called **denormalisation**.

The rationale for this is that it provides only one place to store any item of data, reducing data redundancy and eliminating the possibility of data inconsistency (at least within that single database). This means, however, that data that may be logically related is dispersed throughout the database. Collecting this dispersed data together to answer any particular query can require a large number of disk access requests, which can in turn impact performance. Denormalisation can involve returning ‘repeating groups’ to their master table (or relation). It can also mean joining two tables that are often queried together. Introducing new columns to hold data that can be derived from other data already held elsewhere in the database can also be considered as denormalisation. An example of this would be the recording of the total cost of an order where the costs of the individual items ordered are already recorded. While denormalisation can improve retrieval performance, it can slow down update performance (data needs to be recorded in more than one place) and introduce the possibility of inconsistency (because the users or the application programs need to manage the duplicated updates). Denormalisation should, therefore, be avoided if possible; if used, all decisions to denormalise should be carefully documented.

Chapter 4: Corporate Data Modelling
-----------------------------------

> Irrespective of the reason for the development of the corporate data model, the 'corporate data model initiative' will only be successful if the intended role of the corporate data model is clearly understood across the whole enterprise.

There are a number of questions to be addressed when embarking on the development of a corporate data model:
* **What is the definition of ‘corporate’?** - means the entire enterprise
* **What is ‘corporate data’?** - covers all of the enterprise’s data requirements
* **Is the corporate data model to be used as ...**

**... a business model?** - expresses a view of data from the perspective of the business

**... a database design model?** - any optimisation to enhance the performance of one application program will almost certainly adversely affect the performance of other application programs

**... an interface design model?** - provides a standard with which all information systems must comply at their interfaces with other information systems. The intention is not to direct the design of the databases in the individual information systems, thus preventing optimisation to enhance performance, but to direct how data must be presented to other information systems when there is a requirement to share data with them

**THE NATURE OF A CORPORATE DATA MODEL**

Any requirement to store new ‘data items’ or to change the ‘business rules’ that apply to information or data means a change to the conceptual data model, with subsequent changes to the database structure and the application programs that access the structure.

The problem is often compounded because a database supporting a single system is normally optimised to improve the performance of the applications developed for that system.

In the worst case, the scale of the changes to the system required when the business processes change may be so prohibitively costly, in both time and money, that the systems start to constrain rather than enhance the business.

The scope of a corporate data model must extend beyond a single information system or business area. In my view any attempt to produce a corporate data model using an approach similar to the development of the conceptual data model of a single project is bound to fail, especially if the purpose of the initiative is to develop a corporate data model that forms the basis of the database design for all future systems. There are two interrelated reasons for this:
* Since the complexity of the corporate data model is proportional to the complexity of the enterprise, for a very complex organisation the corporate data model could be exceedingly large and exceedingly complex, requiring many years (or decades) of development. It is also very probable that because of its complexity and its size the finished product will be unintelligible to all except those who have been intimately involved in its development.
* Physical database design and application development must be postponed until the development of the corporate data model is completed. If it is not, the organisation will be continuously developing legacy systems as the development of the corporate data model overtakes the development of the systems.

A corporate data model, by definition, has to cover many different business areas. If the corporate data model is to be used as the basis for all future database design, it also has to be stable. A corporate data model, therefore, has to cope with:
* the different, sometimes conflicting, uses of information and data required by the different business areas;
* the uncertain nature of the future information and data requirements across the enterprise.

Information and data is used in many different ways by the many disparate business areas within an enterprise. In the development of a conceptual data model to support all of an enterprise’s activity – to inform the development of a large number of inter-operating systems – I believe that it will become necessary to develop a data model that is ever more generic or abstract in nature. Examples of the different uses of information that lead to this increasing ‘genericity’ of a corporate data model include:
* Differences between departments over the meaning of the term ‘customer’
* Overlapping roles

**HOW TO DEVELOP A CORPORATE DATA MODEL**

* **Attribute-trawling approach**

This approach involves studying all the existing information systems, collecting the data definitions from those systems (which are probably not documented, so will need to be extracted from the schema definitions held by the database management system) and, once all the definitions are collected, sorting them out so that good, reusable definitions are obtained.

There are three major problems with this approach:
* There may be some areas of the enterprise or some business processes that are not currently supported by information systems; there will, in consequence, be a gap in the analysis.
* It is well known that many information systems do not actually meet the users’ expectations or needs; the data definitions gathered during this exercise will, therefore, be of dubious quality.
* It is unclear how the data definitions will be analysed and compared; there may just be too many to be handled without automated support and such support is not readily available.

* **Joining project or area models**

This approach involves the independent modelling of the information or data requirements of the separate business areas within the enterprise.

The reason for failures is exactly because the models are developed independently of each other. Although the models may have been developed to common standards, the reason for the failure is the absence of a common ‘theme’ in the models. There are often no easily identifiable common points where the models could join. What is needed is a common theme.

* **Building top-down**

Building top-down implies the development of a single conceptual data model that, from its inception, is intended to cover the complete information and data requirements of the whole enterprise.

The best approach is to build the corporate data model ‘top- down’, starting from a core or framework model that represents the major objects and concepts of the business. It can then be used as a skeleton and ‘fleshed out’ with the requirements of the individual project or business areas.

**CORPORATE DATA MODEL PRINCIPLES**

* **develop the model ‘top-down’;**
* **give primacy to the core business;**

It is only possible to give primacy to the core business if that core business is clearly defined. For some enterprises this is not so and it is difficult to identify an initial focus for the modelling effort.
The developers of the corporate data model need to be aware that by giving primacy to the ‘core business’ there is a danger of the model becoming too focused, thus making it extremely difficult to include other business areas within the model later on.

* **cover the whole enterprise;**

Despite giving primacy to the core business, a corporate data model must be able to support the information needs across the full breadth of the enterprise. This ensures that the model covers all business viewpoints and that no data requirements are missed.

* **future-proof the model;**

The model must, therefore, represent the true underlying nature of the information and data used in the business and not how that information or data is used at the time of the analysis. Provided there are no major changes of business purpose, the underlying nature of the information or data used in the business is unlikely to change, but the way that information and data is used and processed is often subject to change.

* **develop co-operatively;**

Co-operation is essential. The data modellers must consult widely with subject-matter experts in the various business areas in the enterprise and with the technical people who are familiar with the existing information systems or who will be responsible for the development of future systems.

* **gain consensus, not perfection.**

The team should be prepared to publish and support a model that is deemed to be ‘fit for role’ by all business areas, even if it is not perfect.

Chapter 5: Data Definitions and Naming
--------------------------------------

**Elements of a Data Definition**

The elements of such a data definition framework could include:

* a name or label;

* any synonyms or aliases;

* a description or significance statement; y formats;

* valid value lists or validation criteria;

* valid operations;

* ownership details;

* usage details;

* source;

* comments;

* configuration information.

Each data item should also have a comprehensive and accurate description of the item. It is preferable if the description is held in the form of a significance statement – a statement of why the data item is deemed to be significant to the business. 

**Data Naming Conventions**

The typical data naming convention that I describe provides names for ‘data items’ constructed of three terms:

* a mandatory prime term that provides the context of the data, which normally means the entity type or table holding the ‘data item’;

* one or more optional modifier terms that are used to make the meaning of the data explicit;

* a mandatory class term that indicates the ‘class’ of the data.

**Problems associated with data naming conventions**

There are basically two problems with data naming conventions: they can be over- prescriptive and they may not deliver what is expected.

Chapter 10: Database Administration
-----------------------------------

**DBA Responsibilities**

Database administrators are responsible for:

* development and maintenance of technical standards covering the database administration function;

* physical database design;

* the management of the database management system software;

* database administration education and training.

**DBA Duties**

The duties of a database administrator include:

* management of the security of the database through the correct establishment of new users, the granting of appropriate access rights to users (see Chapter 8) and the investigation of security breaches;

* monitoring of the performance of the database and tuning to improve performance where necessary;

* guarding against catastrophic database failures by taking regular database backups (see Chapter 8) and rehearsing the associated recovery procedures;

* management of upgrades or changes to the database management system software, for example to take account of new features provided by the software.

**Performance Monitoring and Tuning**

The following actions within the control of the database administrator may be used to alter performance:

* the allocation of memory as buffer, or data cache, to store data that is often queried, to reduce the number of disk reads required;

* the allocation of tables, or parts of tables, to files and the allocation of those files to disk space;

* the extent to which database transactions are logged; writing to a log consumes resources, butcd  logs are essential in the event that the database needs to be recovered;

* the application of locks in multiuser situations so that when a user is accessing some data, that data is locked to prevent another user reading incomplete data or attempting to apply a conflicting update; minimising the possibility of deadlocks (two or more applications holding locks on data that others need to be able to proceed); or reducing the timeout interval (the time an application process can be suspended);

* the use of indexes and the clustering of data as discussed in Chapter 2.

Chapter 3: What is Data Management
-----------------------------------

At its simplest, data management is the management of data, information represented in a formalised manner suitable for communication, interpretation or processing.

> Data management is a corporate service which helps with the provision of information services by controlling or co-ordinating the definitions and usage of reliable and relevant data.

Without effective enterprise-wide data management in place within the organisation:
* The information systems within the enterprise cannot be interfaced.

* Data is not shared between the information systems.

* Communication breaks down and information gets lost.

* Data is unnecessarily transcribed and rekeyed.

* The wheel keeps being reinvented.

* The competitive edge of the organisation is reduced.

* Frustration sets in. 

The requirement for information is changing all the time. Where data is poorly or ambiguously defined, it may be difficult to respond to requests for new information or information presented in a different manner. Real business opportunities may be lost as a result of the inability to respond quickly to changing requirements.

**Data management responsibilities**

From the BCS Data Management Specialist Group definition it can be deduced that data management is a corporate service that:

* **strategically** supports the corporate definition, management and use of business data;

* **operationally** supports the development and maintenance of computerised information systems.

The key areas amongst these responsibilities are:

* achieving recognition of data, both structured and unstructured, as an enterprise-wide valuable business resource;

* improving the quality of the data held within the enterprise’s information systems and ensuring that there are procedures in place to maintain the quality of the data;

* facilitating information sharing across the business by the provision of corporate data definitions and support to the teams involved in systems development to ensure that these definitions are used;

* making the various levels of management within the business accountable for the development and ownership of data definitions – it is within the business, not in IT or IS, that the real meaning of data and information is known;

* achieving a single source for reference data to support all the information systems within the enterprise – this includes internal reference data such as product codes and prices as well as external reference data such as UN country codes.

**Data management activities**

To fulfil the above responsibilities, the data management function needs to identify the specific activities that it needs to carry out and then obtain sufficient resources to perform the activities. These activities are shown in Figure 3.1.

![Figure 3.1 Data management activities](https://github.com/maryoohhh/IS306/blob/master/Images/Figure3-1.png)

One of the principal tasks of data management is to develop the corporate data definitions for the organisation. Key to this is the development of a data model or a set of data models that encapsulate all of the business organisation’s information needs.

If data management is to be successful, it must influence the way that data is defined and handled in any new or replacement systems. It is very important, therefore, that the staff who are charged with the responsibility for data management interact with and support the staff involved in developing future information systems. 

![Figure 3.2 Data management deliverables](https://github.com/maryoohhh/IS306/blob/master/Images/Figure3-2.png)

**Roles within data management**

![Figure 3.3 The relationship between data management and information management](https://github.com/maryoohhh/IS306/blob/master/Images/Figure3-3.png)

**The benefits of data management**

Every organisation is different. It is useful to consider the potential benefits in two areas:

* those that are business related;

* those that are related to information technology and systems

**The relationship between data management and enterprise architecture**

There are a number of enterprise architecture frameworks publicly available including:

* US Department of Defense Architecture Framework (DoDAF);

* UK Ministry of Defence Architecture Framework (MODAF);

* Open Group Architecture Framework (TOGAF);

* Framework for Enterprise Architecture developed by John Zachman (also commonly known as the Zachman Framework).

The columns of the Framework for Enterprise Architecture are:

* the ‘what’ – the ‘inventory sets’ of the enterprise – this is the perspective that looks at the information and its representation as data used by the enterprise;

* the ‘how’ – the ‘process flows’ of the enterprise;

* the ‘where’ – the ‘distribution networks’ of the enterprise;

* the ‘who’ – the ‘responsibility assignments’ of the enterprise;

* the ‘when’ – the ‘timing cycles’ of the enterprise;

* the ‘why’ – the ‘motivation intentions’ of the enterprise.

The first five rows of the Framework for Enterprise Architecture are:

* the ‘executive perspective’ – the view of the business context planners with models for each column that document the scope of the enterprise;

* the ‘business management perspective’ – the view of the business concept owners with models for each column that document the business concepts within the enterprise, the business definition models;

* the ‘architect perspective’ – the view of the business logic designers with models for each column that document the system logic within the enterprise, the system representation models;

* the ‘engineer perspective’ – the view of the business physics builders with models for each column that document the technology of the enterprise, the technology specification models;

* the ‘technician perspective’ – the view of the business component implementers with models for each column that document the tools of the enterprise, the tool configuration models.

Chapter 7: Data Quality
------------------------

> The word quality means different things in different contexts.

**Issues associated with poor data quality**

These are:

* transaction rework costs, for example needing a department to deal with mishandled orders and shipments;

* costs incurred in implementing new systems, for example errors in data increase the cost of implementing an enterprise data warehouse;

* delays in delivering data to decision makers, for example having to manually massage information before it can be released to managers;

* lost customers through poor service, for example customers not returning because of receiving incorrect shipments;

* lost production through supply-chain problems, for example the wrong quantity of parts is ordered from a supplier.

**Causes of poor data quality**

Poor-quality data can arise for a number of reasons, some technical and some human (although even the technical reasons can probably be traced back to some human error):

* databases having inappropriate schemas;

* errors being made on data entry;

* data decaying over time;

* data being corrupted when moved between systems;

* lack of understanding of the data when it is used.

Databases must be designed with flexibility and data quality in mind, even if this is at the expense of performance.

**The dimensions of data quality**

There are two main dimensions of data quality – completeness and correctness. Completeness assesses the extent to which the data reflects the real-world situation. Correctness, on the other hand, assesses whether the data complies with the appropriate constraints and validation rules and whether it accurately reflects the real-world situation.

![Figure 7.1 The dimensions of data quality](https://github.com/maryoohhh/IS306/blob/master/Images/Figure7-1.png)

* **Input validation** – ensuring wherever possible that data is validated on input; it should be impossible to input an invalid date such as 35 October 2006 or to input a birth date for an employee that would imply that they were only two years of age when they started their employment with the company.

* **Integrity** – ensuring that data meets all the data integrity rules; no payroll numbers are duplicated for example.

* **Currency** – ensuring that data is up to date; that changes in employee circumstances have been recorded.

* **Duplication** – ensuring that there is no logical duplication of data and that any physical duplication is properly managed.

* **Inconsistency** – ensuring that data remains consistent; this is generally achieved by managing duplication correctly.

**Data model quality**

An easily applied qualitative model for the assessment of the quality of a data model amongst those reviewed in Information and Database Quality is that proposed by Michael Reingruber and William Gregory in The Data Modeling Handbook, which is shown in Figure 7.2.

![Figure 7.2 The five dimensions of data model quality](https://github.com/maryoohhh/IS306/blob/master/Images/Figure7-2.png)

In this model Reingruber and Gregory have augmented the correctness and completeness dimensions with two further orthogonal dimensions – the syntactic dimension and the semantic dimension. The syntactic dimension addresses how the modelling language and its syntax have been used while the semantic dimension addresses the relationship between the model and the data requirements of the business area that the model represents.

Applying these orthogonal dimensions together we get the four dimensions of syntactic correctness, syntactic completeness, conceptual correctness and conceptual completeness. Reingruber and Gregory have added a fifth overarching dimension that they call enterprise awareness.

This recognises that any data model for a specific business area or set of business processes should be seen as a subset of the enterprise or corporate data model. It is the enterprise awareness dimension that is most often overlooked by data modellers working as part of project teams involved in the development of information systems.

**Improving data quality**

![Figure 7.3 Total quality data management methodology](https://github.com/maryoohhh/IS306/blob/master/Images/Figure7-3.png)

1. The first process, P1, looks at the quality of the design of the databases (that is, the quality of the data definitions) and of the overall information architecture, both from a technical perspective and from a customer-satisfaction perspective.

2. The second process, P2, looks at the data itself. Again there is a technical perspective – does the data comply with the rules – and a customer-satisfaction perspective.

3.  The third process, P3, measures the costs of the poor-quality information in terms of reduced profit and revenue.

4. The fourth process, P4, cleans the existing data, giving corrected and good-quality data.

5. The fifth process, P5, improves the enduring information processes to ensure that the data is maintained at good quality.

6. The sixth process, P6, is about effecting a cultural transformation so that there can be a long-term improvement in information and data quality.

![Figure 7.4 The TEN STEPS process](https://github.com/maryoohhh/IS306/blob/master/Images/Figure7-4.png)

Chapter 9: Master data management
---------------------------------

**What is master data?**

At its most basic, master data management seeks to ensure that an organisation uses only one version of its ‘master data’ for all of its operations.

![Figure 9.1 The six data layers](https://github.com/maryoohhh/IS306/blob/master/Images/Figure9-1.png)

Metadata describes the types of data stored in a database, such as the table and column definitions for a database schema and the associated constraint definitions.

Reference data consists of the codes and their associated descriptions that are used to categorise other data found in a database or, perhaps, for relating data in a database to information found outside the organisation. The tables that hold this data may be called ‘lookup tables’. 

Transaction structure data represents the direct participants in a transaction such as suppliers, customers and products. Information about a transaction cannot be recorded unless the details of these participants already exist in the database.

Enterprise structure data is data that describes the structure of the enterprise, for example the organisational structure or the financial structure.

Transaction activity data is that data that is seen by many people as the prime purpose of information technology: the recording of the transactions or operations that are carried out by the organisation.

Transaction audit data is the data that keeps track of each transaction. This often involves the use of logs.

![Figure 9.2 Different data categories](https://github.com/maryoohhh/IS306/blob/master/Images/Figure9-2.png)

![Figure 9.3 The three master data layers](https://github.com/maryoohhh/IS306/blob/master/Images/Figure9-3.png)

![Figure 9.4 The relationship between business processes and master data](https://github.com/maryoohhh/IS306/blob/master/Images/Figure9-4.png)

**How do problems with master data occur**

Problems with what should be considered as master data occur because of two interrelated problems: the ‘silo’ mentality that exists in many organisations and the independent development of systems to support different ‘silos’.

The ‘silo’ mentality is common in many organisations where groups of employees concentrate on their own function within the organisation.

Information technology systems to support the different functions within an organisation are often independently designed or procured ‘off the shelf’. In each of these systems data will be defined and stored in different ways.

All of this can lead to inconsistent results.

With master data management we are concentrating the efforts of data management on the data with the highest value to the organisation.

**How do we manage master data**

The main technological tool that can be used for the management of master data is the Master Data Management (MDM) Hub, a database and software with two roles: to manage the master data that is stored in the database and to keep it synchronised with the transactional systems that use the master data.

![Figure 9.5 The MDM hub](https://github.com/maryoohhh/IS306/blob/master/Images/Figure9-5.png)

Taking this approach has some advantages such as:

* All systems use the same master data; there is no duplication.

* Duplicate information is easily detected since there is only one place where the master information is held.

However, there are disadvantages such as:

* It may not be possible to change the existing systems to use the new master data.

* The data model for the MDM Hub may be very large and complex.

* Not all of the systems that use the master data will need all of the attributes that have been included in the MDM Hub.

This approach has the advantage that no change to the existing system is required. Against this, the main disadvantage of this approach is that every query against master data results in a distributed query across all of the existing systems that contain the master data.

Another disadvantage of this approach is the need to know about all of the existing systems before implementing the MDM Hub. This can be overcome by developing the hub with a more generic structure but queries will then be more complex.
