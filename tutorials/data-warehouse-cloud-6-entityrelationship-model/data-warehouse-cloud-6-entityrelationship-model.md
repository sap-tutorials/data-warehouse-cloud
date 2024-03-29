---
parser: v2
auto_validation: true
time: 12
tags: [ tutorial>beginner, software-product>sap-datasphere]
primary_tag: software-product>sap-datasphere
---

# Create an Entity Relationship Model in SAP Datasphere
<!-- description --> An entity-relationship model (or E/R model) describes interrelated things of interest in a specific domain of knowledge. You can use an E/R model to better understand a subset of the entities in your space, and to communicate this information to other stakeholders.

## Prerequisites
 - You have [imported your dataset into your Space.](data-warehouse-cloud-5-import-dataset)

## You will learn
  - Overview of E/R Models
  - How to create an E/R Model
  - How to associate data columns
  - Finalise an E/R Model and deploy

  This tutorial is part of a mission, in which you try to help Best Run Bikes to to get a holistic view of their sales data by using the power of SAP Datasphere. You will get the sales data of Best Run Bikes and it is your mission to use the features of SAP Datasphere to help the bike suppliers make the best possible business decisions.

  This mission consists of 8 modules that contain the necessary steps you need to follow in your mission to help Best Run Bikes:

  1. [Sign up for a SAP Datasphere free tier tenant.](data-warehouse-cloud-1-begin-trial)
  2. [Get to know the SAP Datasphere interface](data-warehouse-cloud-2-interface)
  3. [Add users and assign roles](data-warehouse-cloud-3-add-users)
  4. [Create your Space](data-warehouse-cloud-4-spaces)
  5. [Import your datasets](data-warehouse-cloud-5-import-dataset)
  6. **You are here ->** [Create an entity relationship model](data-warehouse-cloud-6-entityrelationship-model)
  7. [Create a graphical view model](data-warehouse-cloud-7-graphicalview)
  8. [Define measures, business semantics and preview your data](data-warehouse-cloud-8-define-measures)

  You can also follow the steps in this tutorial by watching this video. Please note that SAP Data Warehouse Cloud has evolved into SAP Datasphere. While this video references SAP Data Warehouse Cloud, the content applies to SAP Datasphere.

  <iframe id="kmsembed-1_6zv80t8v" width="421" height="300" src="https://video.sap.com/embed/secure/iframe/entryId/1_6zv80t8v/uiConfId/30317401/pbc/122287171/st/0" class="kmsembed" allowfullscreen webkitallowfullscreen mozAllowFullScreen allow="autoplay *; fullscreen *; encrypted-media *" referrerPolicy="no-referrer-when-downgrade" sandbox="allow-downloads allow-forms allow-same-origin allow-scripts allow-top-navigation allow-pointer-lock allow-popups allow-modals allow-orientation-lock allow-popups-to-escape-sandbox allow-presentation allow-top-navigation-by-user-activation" frameborder="0" title="T06-Create an Entity Relationship Model in SAP Data Warehouse Cloud"></iframe>

---

### Understand the basics of E/R models


An E/R model provides a diagram for organising your data entities (tables and views) in relation to one another. You can:

•	Add entities from the repository or import them from a connection or a CSN file, as well as creating new entities directly.

•	Modify the properties of your entities including adding human-readable business names and creating associations directly in the diagram.

•	Save and deploy all the contents of your model with a single action.

The work that you do in an E/R model benefits all the users in your Space as they can use the entities that you import or enhance as sources in their views.

![ER Model](T06-Picture1.gif)

A data model is a way to organise the data and define the relationship between the data elements you have, to give it a structure. This structure must be aligned with your team's needs to generate reports and queries.


### Create an E/R model


1.	Go to the Data Builder and click on the **New Entity-Relationship Model** button.

    ![ER Model Icon](T06-Picture2.png)

2.	This takes you into the graphical modelling interface. Since you imported the sample data manually via CSV, then your data can be found under the **Repository**.
3.	Click and drag the table `SalesOrders` onto the canvas. This table holds information about customer orders.
4.	Next, click and drag the table `SalesOrderItems` to add more detailed information about your orders.

    ![SalesOrder and SalesOrderItems](T06-Picture3.png)

5.	With the data tables now in your modelling interface, you are now ready to create the relevant associations and deploy your E/R model.



### Associate data columns


After including the `SalesOrder` table and the `SalesOrderItems` tables from your Best Run Bikes dataset into the model, they must now be associated to each other.


1.	Click on the `SalesOrders` table and then click on the **Create Association** arrow icon.

2.	Drag it over to the `SalesOrderItems` table to create an association between the two tables.

    ![Association b/w tables](T06-Picture4.png)

3.	Ensure that the created association is between the columns `SalesOrderID` in the **Association Properties** panel.

4.	Drag and drop to connect the sales column from one table to the other if it's not done already.

    ![Association Properties](T06-Picture5.png)

5.	Next, click and drag the `BusinessPartners` table. This table contains information on Best-Run Bikes customers, which is useful when connected to the sales data. We'll go ahead and create an association to the `SalesOrders` table using the `PartnerID` column.

    ![BusinessPartners Table](T06-Picture6.png)

6.	Now add some geographical location information to the model. Drag the `Addresses` table onto the canvas.

7.	And now create an association between the `Addresses` and `BusinessPartners` tables using the `AddressID` column.

    ![AddressID Association](T06-Picture7.png)


### Save and deploy


You've now joined all the tables we will be using in this model. Type a name into the **Model Properties** panel and click on **Save**. And once that's completed, you can click on the deploy icon.

![Save](T06-Picture8.png)


![Deploy](T06-Picture9.png)

You have now created associations between the tables by creating an Entity-Relationship model. You can now use this model to create Graphical or SQL views and model your data accordingly.



---
