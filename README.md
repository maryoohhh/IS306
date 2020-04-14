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
