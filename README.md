# BashSnippets

### Append to file
#### i.e.:
    echo "hello world" >> my_file.txt
    
### Redirect both stdout and stderr to a files
#### one file:
    kill -l 1234 > killouterr.txt 2> &1
    
#### two files:
    kill -l 1234 > killout.txt > killerr.txt
    
    
### Cut and find top 100 lines from file
#### file: dump.txt
#### separator: ":"
    cut -f 2 -d ":" dump.txt|sort|uniq -c|sort -r|head -n 100
    
