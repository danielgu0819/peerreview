## Welcome to Peer Review Project

It is a funny topic, using data science typical processing methods to reveal the value of peer review between original and published papers.  

  _figure 1 data analysis flow_ 
  
![image](https://github.com/danielgu0819/peerreview/blob/master/images/dataprocess.jpg?raw=true)

## Methodology 

1. Scraping data from web site   
2. Analyzing pdf file for preprint papers and published papers  
   such as word cloud and sentiment analysis    
![image](https://github.com/danielgu0819/peerreview/blob/master/images/wordcloud.jpg?raw=true) ![image](https://github.com/danielgu0819/peerreview/blob/master/images/sentiment.jpg?raw=true)

3. Building prediction model, find correlation among published status and factors 
4. This project has 4 codes and some output files, using R and Python, detail code description could be found in "Code description.txt" and below  




## Codes description 

This topic including 4 codes, it is also the running sequence, describing as following 

1, **biorxiv.Rmd** (R code)  
   - This code's functions  
   &ensp;  to scrap preprint papers from https://www.biorxiv.org   
   &ensp;  to download all preprint pdf files  
   &ensp;  to save information to biorxiv.csv(basic information) and biorxiv-pdf.csv(basic information + pdf analysis information)    

   - This code's parameters(could be found in code)   

   | Seq |   Parameters         |   Description                                                              |
   |-----|:--------------------:| --------------------------------------------------------------------------:|
   |  1  |   initial pages link |   https://www.biorxiv.org/search/quan%252Blong%252Bcanada                  |
   |  2  |   NumPage            |   20, means  to scrap data from 20 web pages                               |
   |  3  |   PDF_DIR            |   E:/Ucalgary/internship-proj/rcode/pdf files, save pdf files              |
   |  4  |   CSV_DIR            |   E:/Ucalgary/internship-proj/rcode, run all codes                         |
   |  5  |   WORD_COUNT         |   10, means to neglect this word if frequency less 10                      |
         
         
<br /><br />2, **pe2.ipynb** (Python code)   
   Why use python here?   There are two reasons    
   
   &ensp; &ensp; Because the web site https://www.biorxiv.org has pesudo element for published papers link (some preprint papers have already been published) , using R is difficult to crawl data, but python is very easy.     
   
   &ensp; &ensp; After obtaining the published files' link, we can not download paper directly, because the published web sites are various, and many of them need to pay or sign in before download. So under instructor's advice, we could download this files from library of university of calgary. Python could simulate operating browser to find and download files.    
   
   &ensp; &ensp; But, this code can not be run smoothly, not only because the library web site is not stable, but also because 
   the code offten meeting exception. So, in fact, I run it together with adjusting it mannuly. 
   You could optimize it:) or you could integrate all of four codes in one python file.   
   
   The code's core parts are    
   - to use selenium for pseudo element extraction 
   - to use firefox browser and my username/password login library url 
   - to find the each pdf file's link and download
   - output files is biorxiv-pdf2.csv   
    
     
3, **biorxiv3.Rmd** (R code)    
   There are three functions 
   - to analyze published pdf files, the methods similar like biorxiv.Rmd
   - to build knn prediction model and correlation analysis
   - output file biorxiv-pdf3.csv   
  
  
4, **biorxiv-senti.Rmd**    
   This code is independent code, get sentiment data for preprint pdf files and published pdf files.  
   output are
   - biorxiv-senti-data.csv, biorxiv-senti-data.pdf  for preprint  pdf files
   - biorxiv-senti-data2.csv biorxiv-senti-data2.pdf for published pdf files
    
    
## Support or Contact   
* Instructor: Associate Professor  Dr. Quan Long   
Department of Biochemistry and Molecular Biology, University of Calgary

* Author: Huaien Gu   
Data Science MSc Program, University of Calgary 
danielgu0819@gmail.com 


 
