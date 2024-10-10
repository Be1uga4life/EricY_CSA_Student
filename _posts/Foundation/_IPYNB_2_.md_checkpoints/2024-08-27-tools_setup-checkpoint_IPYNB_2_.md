---
layout: post
title: Tools Verification
description: Verify Installation of tools
type: issues
comments: True
---

```bash
cat <<EOF > /tmp/variables.sh
export project_dir=$HOME/nighthawk
export project=\$project_dir/EricY_CSA_Student
export project_repo="https://github.com/Be1uga4life/EricY_CSA_Student" 
EOF

source /tmp/variables.sh

# Output shown title and value variables
echo "Project dir: $project_dir"
echo "Project: $project"
echo "Repo: $project_repo"
```

    Project dir: /home/eroxyi/EricY_CSA_Student
    Project: /home/eroxyi/EricY_CSA_Student/EricY_CSA_Student
    Repo: https://github.com/Be1uga4life/EricY_CSA_Student



```bash
# Extract saved variables
source /tmp/variables.sh

echo "Using conditional statement to create a project directory and project"

cd ~    # start in home directory

# Conditional block to make a project directory
if [ ! -d $project_dir ]
then 
    echo "Directory $project_dir does not exist... making directory $project_dir"
    mkdir -p $project_dir
fi
echo "Directory $project_dir exists." 

# Conditional block to git clone a project from project_repo
if [ ! -d $project ]
then
    echo "Directory $project does not exist... cloning $project_repo"
    cd $project_dir
    git clone $project_repo
    cd ~
fi
echo "Directory $project exists."
```

    Using conditional statement to create a project directory and project
    Directory /home/eroxyi/EricY_CSA_Student does not exist... making directory /home/eroxyi/EricY_CSA_Student
    Directory /home/eroxyi/EricY_CSA_Student exists.
    Directory /home/eroxyi/EricY_CSA_Student/EricY_CSA_Student does not exist... cloning https://github.com/Be1uga4life/EricY_CSA_Student
    Cloning into 'EricY_CSA_Student'...
    remote: Enumerating objects: 876, done.[K
    remote: Counting objects: 100% (205/205), done.[K
    remote: Compressing objects: 100% (177/177), done.[K
    remote: Total 876 (delta 49), reused 31 (delta 28), pack-reused 671 (from 1)[K
    Receiving objects: 100% (876/876), 39.48 MiB | 18.96 MiB/s, done.
    Resolving deltas: 100% (154/154), done.
    Directory /home/eroxyi/EricY_CSA_Student/EricY_CSA_Student exists.



```bash
source /tmp/variables.sh

echo "Navigate to project, then navigate to area wwhere files were cloned"
cd $project
pwd

echo ""
echo "list top level or root of files with project pulled from github"
ls
```

    Navigate to project, then navigate to area wwhere files were cloned
    /home/eroxyi/EricY_CSA_Student/EricY_CSA_Student
    
    list top level or root of files with project pulled from github
    404.html  README.md      [0m[01;34m_layouts[0m    [01;34massets[0m      requirements.txt  verify.sh
    Gemfile   README4YML.md  [01;34m_notebooks[0m  [01;34mimages[0m      [01;34mscripts[0m
    LICENSE   _config.yml    [01;34m_posts[0m      index.md    style.scss
    Makefile  [01;34m_includes[0m      [01;34m_sass[0m       [01;34mnavigation[0m  test.py

