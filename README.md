# Notion+Kindle-ReadingNotes
Automatically Form clipping in Kindle into a formatted note with Notion
## Background
Trying to make *_Reading Notes_* with Notion based on the contents in Kindle's clipping but unwilling to waste time on searching words and copying sentences, I stretch myself to get related knowledge and code a scipt in Python to make it automatic.
### Format
![](https://tva1.sinaimg.cn/large/008eGmZEly1gmtc219rx1j310q0iy400.jpg)

## Work
1. Get contents from Kindle
  No matter whether you mark a word or a sentence in your kindle, it will add some words to a file `My Clipping.txt` in your Kindle ( `note_path='/Volumes/Kindle/documents/My Clippings.txt' `), conforming to following form (5 lines).  
    ```   
    Book Name
    Pages | Date
  
    word/sentence you have marked
    =========
    ```  
    So it is for us to abstract the note we want.  
    Except for getting the contents:  
  + Divide the content into words/phrases and sentences stored in `words` and `sentences`
  + Delete all contents in `My Clipping.txt` when running the scipt assuming that I will note with notion as soon as having read an article.  
  ( Referring to loadclip.py for details )  
2. Find the sense for words
  I code a simple python-spider to get sense from YoudaoDic web site.  
  ( Referring to getMean.py for details )
3. Add a new note to the Table in Notion.  
  For this part, I use a package [notion-py](https://github.com/jamalex/notion-py). It's comprehensible to treat a notion page as a `tree`.  
  ( Referring to notionNote.py for details )
## How to use
1. Download the Notion-English-ReadingNote repository
2. Connect your Kindle and Computer using an USB cable
3. Replace the notion page address in `notionNote.py` line 23  

    `page = client.get_collection_view("<Your page address>")`  
4. Run `notion.py`
5. Great ! A note has been made😇

Welcome to Try and Give some opnions !
