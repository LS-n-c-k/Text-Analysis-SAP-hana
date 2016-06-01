![Standard Rev 90](C:/Users/Admin/Desktop/pic/capture2.png)

<h1><font color="orange"> SAP HANA Sentiment Analysis -Part2 </font></h1>
---------------------------------------------------------------------------
<h2><font color = "blue"> Run Text Analysis from SQL console </font></h2>


We will use EXTRACTION\_CORE\_VOICEOFCUSTOMER for text analysis
- Select HANA system -> Open SQL console

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part2/1.png)

- Copy the contents present in **createFullTextIndex.sql** into the SQL console of HANA system
![Standard Rev 90](C:/Users/Admin/Desktop/pic/part2/2.png)

- Run the SQL statements, Statements are successfully executed

<h2><font color="red">NOTE:</font></h2>

 - When we do the  Text analysis on HANA, Sentiment analysis is done automatically provide we use the **“EXTRACTION\_CORE\_VOICEOFCUSTOMER”**

 - Refresh the **catalog**, now you will able to find the generated table **$TA\_TWEETS\_FTI**

![Standard Rev 90](C:/Users/Admin/Desktop/pic/part2/3.png)


- Right click on **$TA\_TWEETS\_FTI** and select '**open DATA preview**'

![Standard Rev 90](C:/Users/Admin/Desktop/pic/part2/4.png)

- Go to analysis tab, In LABEL AXIS, select **TA\_TOKEN** and in VALUE AXIS, select **TA\_COUNTER** and the analysis is shown below

![Standard Rev 90](C:/Users/Admin/Desktop/pic/part2/5.png)



In the next tutorial we will filter only Sentiments from Text Analysis and analyse it using SAP UI5 graph







