**Understand the basic structure of a Kusto query**
We will learn about the basic structure of the Kusto Query Language (KQL) so that you can use it to analyze and interpret this dataset.We will connect to a dataset and learn about some of the most commonly used operators.

You'll use the Azure Data Explorer web interface to connect to the data. However, you can also use the Kusto Query Language itself in Log Analytics, Microsoft Sentinel, and other services. You'll only need to connect once, and you'll continue to use this data connection for all queries in the following units.

Use your Azure account to sign in to the Azure Data Explorer web UI. (https://dataexplorer.azure.com/clusters/help/databases/Samples)

In the left pane, select Query.

Select the Add button at the top of the tab, then select Connection.

In the dialog box, under Connection URI, enter help.

Select Add.
<img width="464" height="291" alt="image" src="https://github.com/user-attachments/assets/36a8b11f-d70c-48b0-bfca-9dba0f2b6cd9" />

**Return a specific number of rows by using the take operator**

Take operator returns a specific number of arbitrary rows.

<img width="731" height="362" alt="image" src="https://github.com/user-attachments/assets/487e8afa-7fa3-45ea-bd76-260cc3ac4864" />

**Select columns to return by using the project operator**

Project operator to define which columns you want to see in the output
<img width="730" height="380" alt="image" src="https://github.com/user-attachments/assets/89c54630-7404-4a69-b7db-43f4d7a7019e" />

==========================================================================================================


With the project operator, you can sum integer values from different columns and return the results in a new column. You can also rename columns to make them more meaningful to your analysis.

<img width="729" height="431" alt="image" src="https://github.com/user-attachments/assets/7e168d81-6305-4a51-b3a4-f5aa6b3d8751" />

=========================================================================================================


Use the project-away operator ----> You can remove specific columns by using the project-away operator, which indicates which columns to remove while leaving all remaining columns. You can also use a wildcard, such as | project-away *Id, to remove all columns that end in Id.

<img width="729" height="376" alt="image" src="https://github.com/user-attachments/assets/da291bc5-cb7e-4a42-a9f8-452aef35ac7a" />


**Filter data by using the where operator**

The where operator filters results that satisfy a certain condition. In this first example, you'll compare an integer column to a minimum value by using the numerical operator greater than (>). Specifically, you only want to see storms that damaged property, so you'll look at rows of data where the damage to property is greater than zero.


<img width="458" height="376" alt="image" src="https://github.com/user-attachments/assets/aca4f27f-0121-4498-a35a-e67907216c7a" />

=====================================================================================================


It looks like quite a few types of storms have caused damage all over the US. Let's narrow that down to storms that happened in a certain location, like the state of Florida.

<img width="352" height="368" alt="image" src="https://github.com/user-attachments/assets/66407239-d8a6-4715-8c3a-699e1cbd1956" />

=====================================================================================================


One of the event types in the last query's results is called Thunderstorm Wind. Let's see if there are any other kinds of wind that caused property damage in Florida. We'll search on a string match of wind by using the has operator. The has operator is a case-insensitive search that matches on a full term.

<img width="421" height="380" alt="image" src="https://github.com/user-attachments/assets/7510786b-1ba5-4ceb-aef9-e91ce8a6d0de" />


======================================================================================================

Let's look more closely at the damage done in the first half of the calendar year. It can be useful to limit your search to events within a specific time range. Some interfaces with Kusto Query Language have a dropdown time picker, but others require you to incorporate the date filter into the query itself.

Because time ranges are bounded by two extremes, it's most efficient to construct a query where you choose a value that's between these two times.

The syntax for constructing this date range is as follows:
where time between (datetime(value)..datetime(value))


<img width="512" height="377" alt="image" src="https://github.com/user-attachments/assets/50f2a753-b9cb-412c-9711-8f0931b2f361" />


**Reorder returned data by using the sort operator**


It's difficult to make sense of unordered data. Let's make it a bit easier to understand by organizing the order in which the results are presented. You want to know which events caused the highest damage to property, so you'll order the results by the field DamageProperty.


<img width="392" height="364" alt="image" src="https://github.com/user-attachments/assets/ffe31c4f-07df-4819-b6bb-3aa06ea7d504" />



====================================================================================================================


Each region has unique weather patterns, so now you want to know which events in each state made the most damage. To answer this question, you'll sort first on the state name and then on the damage within each state. The sort operator sorts in descending order by default, so you'll use asc to indicate that you want to sort the state names in ascending order.


<img width="431" height="434" alt="image" src="https://github.com/user-attachments/assets/1ac588f3-efd2-4ee2-a1de-05fa4a547995" />


====================================================================================================================

Instead of sorting and scanning the top for a certain number of results, you can use the top operator to show a specific number of top results. In fact, the top operator is more performant, so it's the preferred choice when you just want a certain number of top results.


<img width="358" height="370" alt="image" src="https://github.com/user-attachments/assets/76a4bf2a-cc23-47e1-999d-80cd2d6f11eb" />
