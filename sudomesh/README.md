### Sudo Mesh

 In order to get this repository, I  used

 ``` wget https://sudoroom.org/wiki/Special:AllPages > index.html  
  	 firefox index.html  
  	 subl list.md  
  	 copy from browser    
  	 paste
  	 delete everything above and below the <li> tags for the article list
  	 Ctrl+H will bring up the find & replace bar
  	 Press CTRL+Enter to indicate a newline character in the 'find' box
  	 Press ',' to make a list  
  	 save as list.md  
  	 Navigate to sudoroom.org/wiki/SpecialExport
  	 paste list from above 
  	 export list
  	 sudo apt install php php-xml pandoc   
     git clone https://github.com/philipashlock/mediawiki-to-markdown  
     cd mediawiki-to-markdown  DO
     mv ~/Downloads/Sudo+Room... .
     folow Readme  
```
### To DO:

Some PHP Error prevented conversions of like 1/2 the files on their wiki. Will fix later.