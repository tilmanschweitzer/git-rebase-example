# git-rebase-example

    set -x
    mkdir git-rebase-example
    cd git-rebase-example
    git init
    
    echo "# git-rebase-example
    " > README.md
    git add README.md
    git commit -m "Add README.md"
    
    # Create branch-A-B-C with three commits
    git checkout -b branch-A-B-C
    
    echo "A" > A.txt
    git add A.txt
    git commit -m "Add A.txt"
    
    echo "B" > B.txt
    git add B.txt
    git commit -m "Add B.txt"
    
    echo "C" > C.txt
    git add C.txt
    git commit -m "Add C.txt"
    
    
    # Switch back to master and create branch-D
    git checkout master
    git checkout -b branch-D
    
    echo "D" > D.txt
    git add D.txt
    git commit -m "Add D.txt"
    
    # Switch back to master and create branch-E
    git checkout master
    git checkout -b branch-E
    
    echo "E" > E.txt
    git add E.txt
    git commit -m "Add E.txt"
    
    # Switch back to master, empty readme an create branch-readme-conflict
    git checkout master
    
    git checkout -b readme
    
    echo "" > README.md
    git commit -a -m "Clean README.md"
    
    git checkout -b readme-conflict
    
    echo "This is the first line of the readme.
    
    This line should produce a conflict.
    
    This is the last line of the readme.
    " > README.md
    
    git commit -a -m "Changed README.md"
    
    # Switch back to readme and change README.md
    git checkout readme
   
    echo "This is the first line of the readme.
    
    Just one differing line can produce a conflict.
    
    This is the last line of the readme.
    " > README.md
    
    git commit -a -m "Changed README.md"
