Bashit: a poor man's Bash debugger
=======

For more debugging woes, check out [the Bash Debugger Project](http://bashdb.sourceforge.net/).
This is a just a simple, poor man's debugger. E.g. given the script:

    NAME="Antonio"
    echo "My name is $NAME"
    echo -n "What is yours? "
    read

here is a sample debug session:

    $ ./poor_man_debugger.sh script_to_debug.sh first_arg second_arg (arguments are ignored in this case)
    [./poor_man_debugger.sh:17] source "$1" "${*:2}" $ (hit Enter to run the program)
    [script_to_debug.sh:2] NAME="Antonio" $ (hit Enter to execute the first line)
    [script_to_debug.sh:3] echo "My name is $NAME" $ echo $NAME (this will inspect a variable!)
    Antonio
    [script_to_debug.sh:3] echo "My name is $NAME" $ (hit Enter to execute the second line)
    My name is Antonio
    [script_to_debug.sh:4] echo -n "What is yours? " $ (hit Enter to execute the second line)
    What is yours? [script_to_debug.sh:5] read $ ^C (hit Ctrl-C to quit)
