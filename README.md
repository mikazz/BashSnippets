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
    

### Conditionals

    if [ -z "$string" ]; then
      echo "String is empty"
    elif [ -n "$string" ]; then
      echo "String is not empty"
    fi
    
### Reading lines

    cat file.txt | while read line; do
      echo $line
    done
    
## Loops

#### Basic for loop

    for i in /etc/rc.*; do
      echo $i
    done
    
#### Ranges

    for i in {1..5}; do
        echo "Welcome $i"
    done

With step size

    for i in {5..50..5}; do
        echo "Welcome $i"
    done
