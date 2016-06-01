![Standard Rev 90](C:/Users/Admin/Desktop/pic/capture2.png)

<h1><font color="orange"> SAP HANA Sentiment Analysis -Part1 </font></h1>
---------------------------------------------------------------------------
<h2><font color = "blue"> Getting the data and import to HANA </font></h2>


- Get the airline dataset from [**kaggle**](https://www.kaggle.com/), before that you need to **sign up** or **sign in** to your account
  - Download the **Twitter US Airline Sentiment** dataset from the given [**link**](https://www.kaggle.com/crowdflower/twitter-airline-sentiment) by clicking on the **Download Data**

![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/0.png)

 - Tweak the tweets.csv file

    1. From original tweet.csv, remove all columns apart from "airline", "name", "text","tweet_created" and "tweet_location"

    2. Add "Id" column for key value

![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/tweet.png)




- Import the tweets.csv file to HANA Server using flat file
   - On HANA studio,Go to File ->  Import ->SAP HANA Content -> Data From Local file -> Next 

![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/1.png)
   
   - Choose your HANA server and press **Next**

![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/2.png)

   - We will get **Define Import properties** tab
   
   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/3.png)
   
   

-  Browse the file **tweets.csv** from the system
  
   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/4.png)

After uploading the file we will get **Define Import properties** tab, inside the tab we need to make the below mentioned changes:  


- Define file encoding as **Default**


- Define field delimitor as **Comma(,)**


- Check **Header row exist**


- check **Import all data**


- In Target table, select **new schema -> TUTORIAL**


- Give a table name as ‘**NewTweets**’ -> **Next**
  
   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/5.png)


   - In manage table definition and Data Mapping
       1. In mapping menu, select one by one
       2. In target table, select Id as Key value -> Next
   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/6.png)
       3. You will get a summary screen -> Finish
   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/7.png)

       4. Importing of data will be getting  started
       5. Import complete message will appear in job log, double click and you will get a job details

   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/8.png)
   ![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/9.png)

   6.We’ve successfully imported data from **tweet.csv** to the HANA table **NewTweets** for text analysis

   7.Go to catalog of your HANA system, open **TUTORIAL** schema -> **Tables** ->right click on **NewTweets** -> open **DATA preview**

![Standard Rev 90](C:/Users/Admin/Desktop/pic/part1/10.png)



We’ll use this table for text analysis in the next tutorial