# BashSnippets

### Append to file
#### i.e.:
    echo "hello world" >> my_file.txt
    
### Redirect both stdout and stderr to a files
#### one file:
    kill -l 1234 > killouterr.txt 2> &1
    
#### two files:
    kill -l 1234 > killout.txt > killerr.txt
    
