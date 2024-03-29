---
parser: v2
auto_validation: true
time: 15
tags: [ tutorial>beginner, software-product>sap-datasphere]
primary_tag: software-product>sap-datasphere
---

# Model Data with SQL in SAP Datasphere
<!-- description --> Get started with SQL views using the Data Builder in SAP Datasphere to create, visualize and manipulate data models.

## Prerequisites
- You have your SAP Datasphere tenant or you have signed up for a [SAP Datasphere free tier tenant](data-warehouse-cloud-1-begin-trial).
- You have imported data into your Space.


## You will learn
- How to create a SQL view in your Space
- How to preview and deploy a SQL view
- How to use SAP HANA-based SQL script language in SAP Datasphere


## Intro
SAP Datasphere is a flexible tool that allows you to model your data in whatever way you prefer: using graphical, drag-and-drop views, or using SQL statements. You can efficiently write SQL queries to manipulate data models and create SQL views in SAP Datasphere that will then feed business intelligence tools.
If you are unsure what data modeling means, or what a joins and unions are, please use our **community blog posts** to get familiar with these concepts:

• [Data Modeling in SAP Datasphere](https://blogs.sap.com/2021/07/20/data-modeling-in-sap-data-warehouse-cloud/)

• [Facts, Measures and Dimensions](https://blogs.sap.com/2021/07/22/facts-measures-and-dimensions/)

Please note that SAP Data Warehouse Cloud has evolved into SAP Datasphere. While some screenshots in this tutorial reference SAP Data Warehouse Cloud, the content applies to SAP Datasphere.


---

### Create a view using SQL


To start modeling your data using the graphical view in the Data Builder of SAP Datasphere, follow these steps:

1.	Go to the **Data Builder** in the menu of left-hand side of the SAP Datasphere welcome page and select the Space in which you want to model your data.

    <!-- border -->![DWC](DS_Homescreen_DataBuilder.png)

2.	Then, click on **New SQL View**.

    <!-- border -->![SQL View](T01%20-%20SQL_cropped.png)

3. You can see on the left side of the screen a list of your local and remote tables and views. In the center of the screen, you can see an area to input your SQL code. As you type your code, SAP Datasphere will offer suggestions.
> <!-- border -->![Suggestions](Suggestions_Cropped.png)
>
> Suggestions include SQL commands as well as table and column names found in your sources. This way, you can move faster and make sure you avoid typos on the way.

1. Below is an example of self-join in SQL code which fetches all the operators, address, postal code and state of electric charging stations in the same postal code. The table used as an example is `Charging_Stations_ECars`.

    ```SQL
    SELECT DISTINCT t1."Betreiber" AS "Operator 1",
    t2."Betreiber" AS "Operator 2",
    t1."Adresse",
    t1."Postleitzahl Ort" AS "Operator 1 Pincode",
    t2."Postleitzahl Ort" AS "Operator 2 Pincode",
    t1."Bundesland"
    FROM "Charging_Stations_ECars" t1,
    "Charging_Stations_ECars" t2
    WHERE t1."Betreiber" <> t2."Betreiber"
    AND t1."Postleitzahl Ort" = t2."Postleitzahl Ort"

    ```
    <!-- border -->![Code ](Code_Cropped.png)

> Exposing the SQL views makes the object available for consumption in SAP Analytics Cloud with which you can invoke business intelligence tools on your data and use them for data analysis. To do this you will have to define the data model type as a `Fact` in the model properties sidebar of the view and toggle on the option **Expose for consumption**. Upon deploying the current SQL view, you'll need to create the Analytic Model from the Model Properties screen. Deploy your Analytic Model. The Analytic Model can now be consumed within SAP Analytics Cloud.

> <!-- border -->![Expose](DSP_Fact.png)

You can also convert your **Graphical View** in the SQL statements. You can refer the step 4 of **[Preview and Transform Your Data in a Graphical View](data-warehouse-cloud-graphical2-datapreview)** for information on converting your graphical view to SQL statements.

### Preview and deploy SQL view


1.	Once you have the SQL code finished, you can click on the shield icon next to the deploy icon to validate your code. You will see a confirmation on the bottom of the screen if your code is valid or not.

    <!-- border -->![Shield](Shield_cropped.png)

2.	To preview the data, you can click on the view icon from the view dropdown menu at the top.

    <!-- border -->![View](Data_preview.png)

3.	You can use the sidebar on the right to add business semantics to your data model, just as you would using the graphical view. When you are ready and your code is valid, just save and deploy your data model.

    ![deploy](DSP_Deploy.png)



### Use SAP HANA-based SQL script language


If you are unsure about the **SAP HANA based SQL Script**, please refer our [SAP HANA database implementation of SQL](https://help.sap.com/viewer/791c41982ee345a19c4ec4b774222c4f/16.0.4.1/en-US/feca57aaf7d5431e827e104506bc19c1.html).

If you are already familiar with the **SAP HANA-based SQL Script** language, you will be pleased to know that you can re-use your existing skills and knowledge when creating data models in the SAP Datasphere.

With the SQL Script, you can define data intensive logic: use `control structures`, `variables`, create `IF` and `FOR` loops. These are just a few possibilities to name.

> Note that the use of SQL Script is currently limited to read-only user defined table functions, therefore **Data Definition Language (DDL)** or **Data Manipulation Language (DML)** are not currently supported.

&nbsp;
> **Well done!**
>
> You have completed the tutorial on Model Data with a SQL View in SAP Datasphere!
> Now it is time to continue learning. Please check out the other [SAP Datasphere tutorials available here] (https://developers.sap.com/tutorial-navigator.html?tag=products:technology-platform/sap-data-warehouse-cloud), and do not forget to follow the [SAP Datasphere tag](https://blogs.sap.com/tags/73555000100800002141/) in the SAP Community to hear about the most up to date product news.




---
