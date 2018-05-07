# BashSnippets

### Append to file
#### i.e.:
    echo "hello world" >> my_file.txt
    
### Redirect both stdout and stderr to a files
#### one file:
    kill -l 1234 > killouterr.txt 2> &1
    
#### two files:
    kill -l 1234 > killout.txt > killerr.txt
    
    
    

### Conditionals

    if [ -z "$string" ]; then
      echo "String is empty"
    elif [ -n "$string" ]; then
      echo "String is not empty"
    fi

## File operations

### Output the number of lines
    wc -l

### Remove first n lines from file
    sed -i '1,n' file.txt



### Reading lines

    cat file.txt | while read line; do
      echo $line
    done
    
### Cut and find top 100 lines from file
file: dump.txt
separator: ":"

    cut -f 2 -d ":" dump.txt|sort|uniq -c|sort -r|head -n 100    
    
    
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
    
## Functions

### Defining functions

    myfunc() {
        echo "hello $1"
    }
    # Same as above (alternate syntax)
    function myfunc() {
        echo "hello $1"
    }
    myfunc "John"
    
### Returning values

    myfunc() {
        local myresult='some value'
        echo $myresult
    }
    result=$(myfunc)
    
### Raising errors

    myfunc() {
      return 1
    }
    if myfunc; then
      echo "success"
    else
      echo "failure"
    fi

## Git

    git commit && git push
    git commit || echo "Commit failed"
