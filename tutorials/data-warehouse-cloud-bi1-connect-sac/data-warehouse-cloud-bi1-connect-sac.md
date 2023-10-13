---
parser: v2
auto_validation: true
time: 10
tags: [ tutorial>intermediate, products>sap-analytics-cloud]
primary_tag: software-product>sap-datasphere
---

# Connect SAP Analytics Cloud to SAP Datasphere
<!-- description --> With SAP Datasphere and SAP Analytics Cloud together, you can handle complex analytics scenarios based on hybrid system architectures. Learn how to connect SAP Analytics Cloud to SAP Datasphere in this tutorial.

## Prerequisites
 - You have [signed up for a SAP Datasphere free tier tenant](data-warehouse-cloud-1-begin-trial) or are an existing SAP Datasphere customer.
 - You have access to an SAP Analytics Cloud tenant.

Please note that SAP Data Warehouse Cloud has evolved into SAP Datasphere. While some screenshots in this tutorial reference SAP Data Warehouse Cloud, the content applies to SAP Datasphere.

## You will learn
  - How to connect SAP Analytics Cloud to SAP Datasphere

---

### Ensure entities in SAP Datasphere are consumable


In order to ensure the data entities and models created in your SAP Datasphere tenant are consumable by SAP Analytics Cloud, it is important to expose them for consumption.

If the entity was created in the data builder, simply click on the entity and set the **Expose for Consumption** toggle to **ON** as below.

  ![Consumable](T05 5.png)

If the entity was created in the business builder, the toggle shows up as a **Allow public data access** checkbox in it's properties tab. Simple click on the data entity to open it, and ensure the checkbox is ticked.

  ![Consumable](T05 6.png)


### Link SAP Datasphere and SAP Analytics Cloud tenants


>Until now, SAP Datasphere delivered an embedded version of SAP Analytics Cloud with a five user license, but most of our customers either already had an existing SAP Analytics Cloud tenant or needed far more than the embedded 5 user license. Therefore, starting February 2021, customers that purchase SAP Datasphere will then become two separate tenants, one for SAP Datasphere and one for SAP Analytics Cloud.

You can connect SAP Datasphere as a remote live connection to any SAP Analytics Cloud system. SAP Datasphere and SAP Analytics Cloud need to be on different tenants.

1.	To link the SAP Analytics Cloud to the SAP Datasphere tenant, navigate to **Configuration** on the bottom left, and select **Tenant Links**.

2.	Here, you can enter the link to your SAP Analytics Cloud tenant.

In SAP Analytics Cloud, you can now create stories using SAP Datasphere data as a source and combine it with additional data (e.g. from a file).

>If required any number of SAP Datasphere systems from multiple tenants can be connected to any SAP Analytics Cloud system. Any SAP Datasphere can be connected to any SAP Analytics Cloud as a live data connection. For more information, see the [official SAP Datasphere documentation](https://help.sap.com/viewer/00f68c2e08b941f081002fd3691d86a7/release/en-US/ad4281e2875949f0b4d45d1072ff4c38.html).

When you link your tenants, you'll enable the product switch in the top right of the shell bar, and be able to easily navigate between them.

  ![Switcher](DSP.png)

>**Well done!**

> You have completed the 1st tutorial of this group! Now you know how to connect SAP Analytics Cloud to SAP Datasphere.

> Learn in the next tutorial [how to create a database user in SAP Datasphere.](data-warehouse-cloud-intro8-create-databaseuser)




### Test yourself




---
