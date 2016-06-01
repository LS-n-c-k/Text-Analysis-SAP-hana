![Standard Rev 90](C:/Users/Admin/Desktop/pic/capture2.png)

<h1><font color="orange"> SAP HANA Sentiment Analysis -Part3 </font></h1>
---------------------------------------------------------------------------
<h2><font color = "blue"> Filter only Sentiments from Text Analysis and analyse it using SAP UI5 graph</font></h2>


Now we filter the **$TA\_TWEETS\_FTI** to fit with the below keywords and create a few sentiments like:


- WeakPositiveEmoticon


- WeakNegativeSentiment


- WeakNegativeEmoticon


- StrongPositiveSentiment


- StrongPositiveEmoticon


- StrongNegativeSentiment


- StrongNegativeEmoticon


- Sentiment


- Request


- NeutralSentiment


- MinorProblem


- MajorProblem




1.Open the SQL console on HANA server, copy the contents present in **filter.sql** and execute, you will get a view “**TWEETS\_TEXT**”  inside **TUTORIAL** schema with filtered data from the original text analysis table

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/3.png)

  Right click on TWEETS\_TEST and select 'open DATA preview'

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/2.png)



2.Go to **Analysis** tab, In LABEL AXIS, select **TA\_TOKENS** and in VALUE AXIS, select **TA\_COUNTER** and the analysis is as shown below

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/4.png)

3.Again in the **Analysis** tab, select **TA\_TYPE** in LABEL AXIS, and select **TA\_COUNTER** in VALUE AXIS and the analysis is as shown below

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/5.png)



<h4><font color = "blue"> Consume the view as oData service and show it on sapui5 graph</font></h4>


- Switch to ‘**project explorer**’. Go to File -> New -> Project -> "XS Project" -> Give the project name (In our example it's TextAnalysis)

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/6.png)

- Right click on your XS project(TextAnalysis) and create a new file call “.xsaccess” and ".xsapp".

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/1.png)

- Right click on your XS project(TextAnalysis) and create a new file call “service.xsodata”

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/8.png)

- Write the below code for service.xsodata file

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/9.png) 

- Save all files
- Select the project, Go to Team -> Share project -> select the HANA system -> Finish

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/10.png) 

- Go to project explorer, right click on your project(TextAnalysis) -> Team -> Activate all

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/11.png) 

- Run the xsodata service

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/12.png) 

- Here we've set the **EntitySet Name = "Analysis"**, we will be using this EntitySet name as the path name in the in the index.html and newIndex.html file to build the SAP UI5 graph 

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/13.png) 

1.Go to your project explorer, right click on your project file and create a new file call **index.html** to consume odata service 

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/14.png)

- In index.html file we are using **Bootstrap** to get extensive and beautiful documentation for common HTML elements, dozens of custom HTML and CSS components, and awesome jQuery plugins. It is the most popular HTML, CSS, and JavaScript framework for developing responsive, mobile-first websites
- In script tag we are setting the data model for service.xsodata service

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/Untitled.png)


- Create graph using sapui5
- To create a graph we are using **sap.viz.ui5** 
- In the graph we are using **TA\_TOKEN** for **dimensions**  and **TA\_COUNTER**  for **measures**
- To render the data from the xsodata service file, we are specifying the path as **/Analysis**

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/15.png)

- Save, Activate and run the index file for TA\_TOKENS and TA\_COUNTER and the SAP UI5 graph is as shown below:

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/16.png)



2.Again go to your project explorer, right click on your project file and create a new file call **newIndex.html** to consume odata service

- Again we are creating the graph for **newIndex.html**, for this graph we are using **TA\_TYPE** for **dimensions** and **TA\_COUNTER** for **measures**

- Save, Activate and run the index file for TA\_TOKENS and TA\_COUNTER and the SAP UI5 graph is as shown below:

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part3/17.png)





















