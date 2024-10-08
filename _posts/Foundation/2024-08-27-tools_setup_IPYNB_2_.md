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

    Project dir: /home/eroxyi/nighthawk
    Project: /home/eroxyi/nighthawk/EricY_CSA_Student
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
    Directory /home/eroxyi/nighthawk exists.
    Directory /home/eroxyi/nighthawk/EricY_CSA_Student exists.



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
    /home/eroxyi/nighthawk/EricY_CSA_Student
    
    list top level or root of files with project pulled from github
    404.html      Makefile       [0m[01;34m_includes[0m   [01;34m_sass[0m   index.md          test.py
    Gemfile       README.md      [01;34m_layouts[0m    [01;34m_site[0m   [01;34mnavigation[0m        verify.sh
    Gemfile.lock  README4YML.md  [01;34m_notebooks[0m  [01;34massets[0m  requirements.txt
    LICENSE       _config.yml    [01;34m_posts[0m      [01;34mimages[0m  [01;34mscripts[0m



```bash
# Extract saved variables
source /tmp/variables.sh

echo "Navigate to project, then navigate to area wwhere files were cloned"
cd $project
pwd

echo ""
echo "list all files in long format"
ls -al   # all files -a (hidden) in -l long listing
```

    Navigate to project, then navigate to area wwhere files were cloned
    /home/eroxyi/nighthawk/EricY_CSA_Student
    
    list all files in long format
    total 140
    drwxr-xr-x 16 eroxyi eroxyi  4096 Aug 27 18:22 [0m[01;34m.[0m
    drwxr-xr-x  3 eroxyi eroxyi  4096 Aug 27 11:57 [01;34m..[0m
    drwxr-xr-x  8 eroxyi eroxyi  4096 Aug 28 12:31 [01;34m.git[0m
    drwxr-xr-x  3 eroxyi eroxyi  4096 Aug 27 11:57 [01;34m.github[0m
    -rw-r--r--  1 eroxyi eroxyi   246 Aug 27 11:57 .gitignore
    drwxr-xr-x  7 eroxyi eroxyi  4096 Aug 27 16:56 [01;34m.venv[0m
    drwxr-xr-x  2 eroxyi eroxyi  4096 Aug 27 11:57 [01;34m.vscode[0m
    -rw-r--r--  1 eroxyi eroxyi   436 Aug 27 11:57 404.html
    -rw-r--r--  1 eroxyi eroxyi   122 Aug 27 11:57 Gemfile
    -rw-r--r--  1 eroxyi eroxyi  7554 Aug 27 12:16 Gemfile.lock
    -rw-r--r--  1 eroxyi eroxyi 11357 Aug 27 11:57 LICENSE
    -rw-r--r--  1 eroxyi eroxyi  3554 Aug 27 11:57 Makefile
    -rw-r--r--  1 eroxyi eroxyi 14171 Aug 27 11:57 README.md
    -rw-r--r--  1 eroxyi eroxyi    79 Aug 27 11:57 README4YML.md
    -rw-r--r--  1 eroxyi eroxyi   898 Aug 27 11:57 _config.yml
    drwxr-xr-x  4 eroxyi eroxyi  4096 Aug 27 11:57 [01;34m_includes[0m
    drwxr-xr-x  2 eroxyi eroxyi  4096 Aug 27 11:57 [01;34m_layouts[0m
    drwxr-xr-x  3 eroxyi eroxyi  4096 Aug 27 16:58 [01;34m_notebooks[0m
    drwxr-xr-x  3 eroxyi eroxyi  4096 Aug 27 11:57 [01;34m_posts[0m
    drwxr-xr-x  4 eroxyi eroxyi  4096 Aug 27 11:57 [01;34m_sass[0m
    drwxr-xr-x 11 eroxyi eroxyi  4096 Aug 28 11:55 [01;34m_site[0m
    drwxr-xr-x  5 eroxyi eroxyi  4096 Aug 27 11:57 [01;34massets[0m
    drwxr-xr-x  3 eroxyi eroxyi  4096 Aug 27 11:57 [01;34mimages[0m
    -rw-r--r--  1 eroxyi eroxyi   624 Aug 27 18:26 index.md
    drwxr-xr-x  2 eroxyi eroxyi  4096 Aug 27 11:57 [01;34mnavigation[0m
    -rw-r--r--  1 eroxyi eroxyi    57 Aug 27 11:57 requirements.txt
    drwxr-xr-x  3 eroxyi eroxyi  4096 Aug 27 12:16 [01;34mscripts[0m
    -rw-r--r--  1 eroxyi eroxyi    33 Aug 27 11:57 test.py
    -rw-r--r--  1 eroxyi eroxyi  3482 Aug 27 12:35 verify.sh



```bash
# Extract saved variables
source /tmp/variables.sh

echo "Look for posts"
export posts=$project/_posts  # _posts inside project
cd $posts  # this should exist per fastpages
pwd  # present working directory
ls -lR  # list posts recursively
```

    Look for posts
    /home/eroxyi/nighthawk/EricY_CSA_Student/_posts
    .:
    total 4
    drwxr-xr-x 6 eroxyi eroxyi 4096 Aug 28 11:55 [0m[01;34mFoundation[0m
    
    ./Foundation:
    total 56
    -rw-r--r-- 1 eroxyi eroxyi  2683 Aug 27 12:16 2024-08-21-sprint1_plan_IPYNB_2_.md
    -rw-r--r-- 1 eroxyi eroxyi  6369 Aug 27 12:16 2024-08-23-sprint1-hacks_IPYNB_2_.md
    -rw-r--r-- 1 eroxyi eroxyi 29785 Aug 28 11:55 2024-08-27-tools_setup_IPYNB_2_.md
    drwxr-xr-x 2 eroxyi eroxyi  4096 Aug 27 12:16 [01;34mA-pair_programming[0m
    drwxr-xr-x 2 eroxyi eroxyi  4096 Aug 27 12:16 [01;34mB-tools_and_equipment[0m
    drwxr-xr-x 2 eroxyi eroxyi  4096 Aug 28 11:55 [01;34m_IPYNB_2_.md_checkpoints[0m
    
    ./Foundation/A-pair_programming:
    total 24
    -rw-r--r-- 1 eroxyi eroxyi  5433 Aug 27 11:57 2023-08-16-pair_programming.md
    -rw-r--r-- 1 eroxyi eroxyi  3242 Aug 27 12:16 2023-08-16-pair_showcase_IPYNB_2_.md
    -rw-r--r-- 1 eroxyi eroxyi 10043 Aug 27 12:16 2023-08-17-pair_habits_IPYNB_2_.md
    
    ./Foundation/B-tools_and_equipment:
    total 92
    -rw-r--r-- 1 eroxyi eroxyi  8196 Aug 27 12:16 2023-08-19-devops_accounts_IPYNB_2_.md
    -rw-r--r-- 1 eroxyi eroxyi  4949 Aug 27 12:16 2023-08-21-devops_tools-home_IPYNB_2_.md
    -rw-r--r-- 1 eroxyi eroxyi 17367 Aug 27 12:16 2023-08-21-devops_tools-setup_IPYNB_2_.md
    -rw-r--r-- 1 eroxyi eroxyi 16130 Aug 27 12:16 2023-08-22-devops_tools-verify_IPYNB_2_.md
    -rw-r--r-- 1 eroxyi eroxyi 25977 Aug 27 12:16 2023-08-23-devops-githhub_pages-play_IPYNB_2_.md
    -rw-r--r-- 1 eroxyi eroxyi  7506 Aug 27 12:16 2023-08-23-devops-hacks_IPYNB_2_.md
    
    ./Foundation/_IPYNB_2_.md_checkpoints:
    total 4
    -rw-r--r-- 1 eroxyi eroxyi 2942 Aug 28 11:55 2024-08-27-tools_setup-checkpoint_IPYNB_2_.md



```bash
# Extract saved variables
source /tmp/variables.sh

echo "Look for notebooks"
export notebooks=$project/_notebooks  # _notebooks is inside project
cd $notebooks   # this should exist per fastpages
pwd  # present working directory
ls -lR  # list notebooks recursively
```

    Look for notebooks
    /home/eroxyi/nighthawk/EricY_CSA_Student/_notebooks
    .:
    total 4
    drwxr-xr-x 5 eroxyi eroxyi 4096 Aug 27 17:32 [0m[01;34mFoundation[0m
    
    ./Foundation:
    total 64
    -rw-r--r-- 1 eroxyi eroxyi  3509 Aug 27 11:57 2024-08-21-sprint1_plan.ipynb
    -rw-r--r-- 1 eroxyi eroxyi  9640 Aug 27 11:57 2024-08-23-sprint1-hacks.ipynb
    -rw-r--r-- 1 eroxyi eroxyi 37390 Aug 27 17:32 2024-08-27-tools_setup.ipynb
    drwxr-xr-x 2 eroxyi eroxyi  4096 Aug 27 11:57 [01;34mA-pair_programming[0m
    drwxr-xr-x 2 eroxyi eroxyi  4096 Aug 27 11:57 [01;34mB-tools_and_equipment[0m
    
    ./Foundation/A-pair_programming:
    total 16
    -rw-r--r-- 1 eroxyi eroxyi  3918 Aug 27 11:57 2023-08-16-pair_showcase.ipynb
    -rw-r--r-- 1 eroxyi eroxyi 11624 Aug 27 11:57 2023-08-17-pair_habits.ipynb
    
    ./Foundation/B-tools_and_equipment:
    total 112
    -rw-r--r-- 1 eroxyi eroxyi  9767 Aug 27 11:57 2023-08-19-devops_accounts.ipynb
    -rw-r--r-- 1 eroxyi eroxyi  5931 Aug 27 11:57 2023-08-21-devops_tools-home.ipynb
    -rw-r--r-- 1 eroxyi eroxyi 22859 Aug 27 11:57 2023-08-21-devops_tools-setup.ipynb
    -rw-r--r-- 1 eroxyi eroxyi 23150 Aug 27 11:57 2023-08-22-devops_tools-verify.ipynb
    -rw-r--r-- 1 eroxyi eroxyi 32309 Aug 27 11:57 2023-08-23-devops-githhub_pages-play.ipynb
    -rw-r--r-- 1 eroxyi eroxyi  9478 Aug 27 11:57 2023-08-23-devops-hacks.ipynb



```bash
# Extract saved variables
source /tmp/variables.sh

echo "Look for images, print working directory, list files"
cd $project/images  # this should exist per fastpages
pwd
ls -lR
```

    Look for images, print working directory, list files
    /home/eroxyi/nighthawk/EricY_CSA_Student/images
    .:
    total 88
    -rw-r--r-- 1 eroxyi eroxyi 30428 Aug 27 11:57 [0m[01;35meric.jpg[0m
    -rw-r--r-- 1 eroxyi eroxyi 15406 Aug 27 11:57 favicon.ico
    -rw-r--r-- 1 eroxyi eroxyi 34239 Aug 27 11:57 [01;35mlogo.png[0m
    drwxr-xr-x 3 eroxyi eroxyi  4096 Aug 27 11:57 [01;34mnotebooks[0m
    
    ./notebooks:
    total 4
    drwxr-xr-x 2 eroxyi eroxyi 4096 Aug 27 11:57 [01;34mfoundation[0m
    
    ./notebooks/foundation:
    total 364
    -rw-r--r-- 1 eroxyi eroxyi 310743 Aug 27 11:57 [01;35mcreate_repo.png[0m
    -rw-r--r-- 1 eroxyi eroxyi  29416 Aug 27 11:57 [01;35mpush.jpg[0m
    -rw-r--r-- 1 eroxyi eroxyi  17105 Aug 27 11:57 [01;35mstage.jpg[0m
    -rw-r--r-- 1 eroxyi eroxyi   6659 Aug 27 11:57 [01;35mwsl.jpg[0m



```bash
# Extract saved variables
source /tmp/variables.sh

echo "Navigate to project, then navigate to area wwhere files were cloned"

cd $project
echo "show the contents of README.md"
echo ""

cat README.md  # show contents of file, in this case markdown
echo ""
echo "end of README.md"
```

    Navigate to project, then navigate to area wwhere files were cloned
    show the contents of README.md
    
    # Introduction
    
    Nighthawk Pages is a project designed to support students in their Computer Science and Software Engineering education. It offers a wide range of resources including tech talks, code examples, and educational blogs.
    
    GitHub Pages can be customized by the blogger to support computer science learnings as the student works through the pathway of using Javascript, Python/Flask, Java/Spring.  
    
    ## Student Requirements
    
    Del Norte HS students will be required to review their personal GitHub Pages at each midterm and final.  This review will contain a compilation of personal work performed within each significant grading period.
    
    In general, Students and Teachers are expected to use GitHub pages to build lessons, complete classroom hacks, perform work on JavaScript games, and serve as a frontend to full-stack applications.
    
    Exchange of information could be:
    
    1. sharing a file:  `wget "raw-link.ipynb"
    2. creating a template from this repository
    3. sharing a fork among team members
    4. etc.
    
    ---
    
    ## History
    
    This project is in its 3rd revision (aka 3.0).
    
    The project was initially based on Fastpages. But this project has diverged from those roots into an independent entity.  The decision to separate from Fastpages was influenced by the deprecation of Fastpages by authors.  It is believed by our community that the authors of fastpages turned toward Quatro.  After that change of direction fastpages did not align with the Teacher's goals and student needs. The Nighthawk Pages project has more of a raw development blogging need.
    
    ### License
    
    The Apache license has its roots in Fastpages.  Thus, it carries its license forward.  However, most of the code is likely unrecognizable from those roots.
    
    ### Key Features
    
    - **Code Examples**: Provides practical coding examples in JavaScript, including a platformer game, and frontend code for user databases using Python and Java backends.
    - **Educational Blogs**: Offers instructional content on various topics such as developer tools setup, deployment on AWS, SQL databases, machine learning, and data structures. It utilizes Jupyter Notebooks for interactive lessons and coding challenges.
    - **Tools and Integrations**: Features GitHub actions for blog publishing, Utterances for blog commenting, local development support via Makefile and scripts, and styling with the Minima Theme and SASS. It also includes a new integration with GitHub Projects and Issues.
    
    ### Contributions
    
    - **Notable Contributions**: Highlights significant contributions to the project, including theme development, search and tagging functionality, GitHub API integration, and the incorporation of GitHub Projects into GitHub pages. Contributors such as Tirth Thakker, Mirza Beg, and Toby Ledder have played crucial roles in these developments.
    
    - **Blog Contributions**:  Often students contribute articles and blogs to this project.  Their names are typically listed in the front matter of their contributing post.
    
    ---
    
    ## GitHub Pages setup
    
    The absolutes in setup up...
    
    **Activate GitHub Pages Actions**: This step involves enabling GitHub Pages Actions for your project. By doing so, your project will be automatically deployed using GitHub Pages Actions, ensuring that your project is always up to date with the latest changes you push to your repository.
    
    - On the GitHub website for the repository go to the menu: Settings -> Pages ->Build
    - Under the Deployment location on the page, select "GitHub Actions".
    
    **Update `_config.yml`**: You need to modify the `_config.yml` file to reflect your repository's name. This configuration is crucial because it ensures that your project's styling is correctly applied, making your deployed site look as intended rather than unstyled or broken.
    
    ```text
    github_repo: "student_2025" 
    baseurl: "/student_2025"
    ```
    
    **Set Repository Name in Makefile**: Adjust the `REPO_NAME` variable in your Makefile to match your GitHub repository's name. This action facilitates the automatic updating of posts and notebooks on your local development server, improving the development process.
    
    ```make
    # Configuration, override port with usage: make PORT=4200
    PORT ?= 4100
    REPO_NAME ?= student_2025
    LOG_FILE = /tmp/jekyll$(PORT).log
    ```
    
    ### Tool requirements
    
    All `GitHub Pages` websites are managed on GitHub infrastructure and use GitHub version control.  Each time we change files in GitHub it initiates a GitHub Action, a continuous integration and development toolset, that rebuilds and publishes the site with Jekyll.  
    
    - GitHub uses `Jekyll` to transform your markdown and HTML content into static websites and blogs. [Jekyll](https://jekyllrb.com/).
    - A Linux shell is required to work with this project integration with GitHub Pages, GitHub and VSCode.  Ubuntu is the preferred shell, though MacOS shell is supported as well.  There will be some key setup scripts that follow in the README.
    - Visual Studio Code is the Nighthawk Pages author's preferred code editor and extensible development environment.  VSCode has a rich ecosystem of developer extensions that ease working with GitHub Pages, GitHub, and many programming languages.  Setting up VSCode and extensions will be elaborated upon in this document.
    - An anatomy section in this README will describe GitHub Pages and conventions that are used to organize content and files.  This includes file names, key coding files, metadata tagging of blogs, styling tooling for blogs, etc.
    
    ### Development Environment Setup
    
    Comprehensive start. A topic-by-topic guide to getting this project running is published [here](https://nighthawkcoders.github.io/portfolio_2025/devops/tools/home).
    
    Quick start.  A quick start below is a reminder, but is dependent on your knowledge.  Only follow this instruction if you need a refresher.  Always default to the comprehensive start if any problem occurs.
    
    #### Clone Repo
    
    Run these commands to obtain the project, then locate into the project directory with the terminal, install an extensive set of tools, and make.
    
    ```bash
    git clone <this-repo> # git clone https://github.com/nighthawkcoders/student_2025.git 
    cd <repo-dir>/scripts # cd student_2025
    ```
    
    #### Windows WSL and/or Ubuntu Users
    
    - Execute the script: `./activate_ubuntu.sh`
    
    #### macOS Users
    
    - Execute the script: `./activate_macos.sh`
    
    #### Kasm Cloud Desktop Users
    
    - Execute the script: `./activate.sh`
    
    ## Run Server on localhost
    
    To preview the project you will need to "make" the project.
    
    ### Bundle install
    
    The very first time you clone run project you will need to run this Ruby command as the final part of your setup.
    
    ```bash
    bundle install
    ```
    
    ### Start the Server  
    
    This requires running terminal commands `make`, `make stop`, `make clean`, or `make convert` to manage the running server.  Logging of details will appear in the terminal.   A `Makefile` has been created in the project to support commands and start processes.
    
    Start the server, this is the best choice for initial and iterative development.  Note. after the initial `make`, you should see files automatically refresh in the terminal on VSCode save.
    
      ```bash
      make
      ```
    
    ### Load web application into the Browser
    
    Start the preview server in the terminal,
    The terminal output from `make` shows the server address. "Cmd" or "Ctl" click the http location to open the preview server in a browser. Here is an example Server address message, click on the Server address to load:...
    
      ```text
      http://0.0.0.0:4100/student_2025/
      ```
    
    ### Regeneration of web application
    
    Save on ".ipynb" or ".md" file activiates "regeneration". An example terminal message is below.  Refresh the browser to see updates after the message displays.
    
      ```text
      Regenerating: 1 file(s) changed at 2023-07-31 06:54:32
          _notebooks/2024-01-04-cockpit-setup.ipynb
      ```
    
    ### Other "make" commands
    
    Terminal messages are generated from background processes.  At any time, click return or enter in a terminal window to obtain a prompt.  Once you have the prompt you can use the terminal as needed for other tasks.  Always return to the root of project `cd ~/vscode/student_2025` for all "make" actions.
    
    #### Stop the preview server
    
    Stopping the server ends the web server applications running process.  However, it leaves constructed files in the project in a ready state for the next time you run `make`.
    
      ```bash
      make stop
      ```
    
    ### Clean the local web application environment
    
    This command will top the server and "clean" all previously constructed files (ie .ipynb -> .md). This is the best choice when renaming files has created duplicates that are visible when previewing work.
    
      ```bash
      make clean
      ```
    
    ### Observe build errors
    
    Test Jupyter Notebook conversions (ie .ipynb -> .md), this is the best choice to see if an IPYNB conversion error is occurring.
    
      ```bash
      make convert
      ```
    
    ---
    
    ## Development Support
    
    ### File Names in "_posts", "_notebooks"
    
    There are two primary directories for creating blogs.  The "_posts" directory is for authoring in markdown only.  The "_notebooks" allows for markdown, pythons, javascript and more.
    
    To name a file, use the following structure (If dates are in the future, review your config.yml setting if you want them to be viewed).  Review these naming conventions.
    
    - For markdown files in _posts:
      - year-month-day-fileName.md
        - GOOD EXAMPLE: 2021-08-02-First-Day.md
        - BAD EXAMPLE: 2021-8-2-first-day.md
        - BAD EXAMPLE: first-day.md
        - BAD EXAMPLE: 2069-12-31-First-Day.md
    
    - For Jupyter notebooks in _notebooks:
      - year-month-day-fileName.ipynb
        - GOOD EXAMPLE: 2021-08-02-First-Day.ipynb
        - BAD EXAMPLE: 2021-8-2-first-day.ipynb
        - BAD EXAMPLE: first-day.ipynb
        - BAD EXAMPLE: 2069-12-31-First-Day.ipynb
    
    ### Tags
    
    Tags are used to organize pages by their tag the way to add tags is to add the following to your front matter such as the example seen here `categories: [Tools]` Each item in the same category will be lumped together to be seen easily on the search page.
    
    ### Search
    
    All pages can be searched for using the built-in search bar. This search bar will search for any word in the title of a page or in the page itself. This allows for easily finding pages and information that you are looking for. However, sometimes this may not be desirable so to hide a page from the search you need to add `search_exclude: true` to the front matter of the page. This will hide the page from appearing when the viewer uses search.
    
    ### Navigation Bar
    
    To add pages to the top navigation bar use _config.yml to order and determine which menus you want and how to order them.  Review the_config.yml in this project for an example.
    
    ### Blog Page
    
    There is a blog page that has options for images and a description of the page. This page can help the viewer understand what the page is about and what they can expect to find on the page. The way to add images to a page is to have the following front matter `image: /images/file.jpg` and then the name of the image that you want to use. The image must be in the `images` folder. Furthermore, if you would like the file to not show up on the blog page `hide: true` can be added to the front matter.
    
    ### SASS support
    
    NIGHTHAWK Pages support a variety of different themes that are each overlaid on top of minima. To use each theme, go to the "_sass/minima/custom-styles.scss" file and simply comment or uncomment the theme you want to use.
    
    To learn about the minima themes search for "GitHub Pages minima" and review the README.
    
    To find a new theme search for "Github Pages Themes".
    
    ### Includes
    
    - Nighthawk Pages uses liquid syntax to import many common page elements that are present throughout the repository. These common elements are imported from the _includes directory. If you want to add one of these common elements, use liquid syntax to import the desired element to your file. Here’s an example of the liquid syntax used to import: `{%- include post_list.html -%}` Note that the liquid syntax is surrounded by curly braces and percent signs. This can be used anywhere in the repository.
    
    ### Layouts
    
    - To use or create a custom page layout, make an HTML page inside the _layouts directory, and when you want to use that layout in a file, use the following front matter `layout: [your layout here]`.  All layouts will be written in liquid to define the structure of the page.
    
    ### Metadata
    
    Metadata, also known as "front matter", is a set of key-value pairs that can provide additional information to GitHub Pages about .md and .ipynb files. This can and probably will be used in other file types (ie doc, pdf) if we add them to the system.
    
    In the front matter, you can also define things like a title and description for the page.  Additional front matter is defined to place content on the "Computer Science Lab Notebook" page.  The `courses:` key will place data on a specific page with the nested `week:` placing data on a specific row on the page.  The `type:` key in "front matter" will place the blog under the plans, hacks(ToDo), and tangibles columns.
    
    - In our files, the front matter is defined at the top of the page or the first markdown cell.
    
      - First, open one of the .md or .ipynb files already included in either your _posts|_notebooks folder.
    
      - In the .md file, you should notice something similar to this at the top of the page. To see this in your .ipynb files you will need to double-click the markdown cell at the top of the file.
    
      ```yaml
      ---
      toc: true
      comments: true
      layout: post
      title: Jupyter Python Sample
      description: Example Blog!!!  This shows code and notes from hacks.
      type: ccc
      courses: { csa: {week: 5} }
      ---
      ```
    
    - The front matter will always have '---' at the top and bottom to distinguish it and each key-value pair will be separated by a ':'.
    
    - Here we can modify things like the title and description.
    
    - The type value will tell us which column this is going to appear under the time box supported pages.  The "ccc" stands for Code, Code, Code.
    
    - The courses will tell us which menu item it will be under, in this case, the `csa` menu, and the `week` tells it what row (week) it will appear under that menu.
    
    end of README.md



```bash
echo "Show the shell environment variables, key on left of equal value on right"
echo ""

env
```

    Show the shell environment variables, key on left of equal value on right


    
    SHELL=/bin/bash
    PYTHONUNBUFFERED=1
    WSL2_GUI_APPS_ENABLED=1
    project=/home/eroxyi/nighthawk/EricY_CSA_Student
    APPLICATION_INSIGHTS_NO_DIAGNOSTIC_CHANNEL=1
    WSL_DISTRO_NAME=Ubuntu
    PYTHON_FROZEN_MODULES=on
    ELECTRON_RUN_AS_NODE=1
    VSCODE_AMD_ENTRYPOINT=vs/workbench/api/node/extensionHostProcess
    NAME=Code
    PWD=/home/eroxyi/nighthawk/EricY_CSA_Student
    LOGNAME=eroxyi
    MOTD_SHOWN=update-motd
    NOTEBOOK_BASH_KERNEL_CAPABILITIES=image,html,javascript
    project_dir=/home/eroxyi/nighthawk
    HOME=/home/eroxyi
    LANG=C.UTF-8
    WSL_INTEROP=/run/WSL/843_interop
    LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
    WAYLAND_DISPLAY=wayland-0
    VSCODE_L10N_BUNDLE_LOCATION=
    posts=/home/eroxyi/nighthawk/EricY_CSA_Student/_posts
    LESSCLOSE=/usr/bin/lesspipe %s %s
    VSCODE_HANDLES_SIGPIPE=true
    TERM=xterm-256color
    LESSOPEN=| /usr/bin/lesspipe %s
    USER=eroxyi
    PYTHONIOENCODING=utf-8
    notebooks=/home/eroxyi/nighthawk/EricY_CSA_Student/_notebooks
    DISPLAY=:0
    SHLVL=2
    PAGER=cat
    project_repo=https://github.com/Be1uga4life/EricY_CSA_Student
    VSCODE_CWD=/mnt/c/Users/achtu/AppData/Local/Programs/Microsoft VS Code
    XDG_RUNTIME_DIR=/run/user/1000/
    PS1=PROMPT_BGXPOKUCZNTU\[\]>
    WSLENV=ELECTRON_RUN_AS_NODE/w:
    
    VSCODE_WSL_EXT_LOCATION=/mnt/c/Users/achtu/.vscode/extensions/ms-vscode-remote.remote-wsl-0.88.2
    XDG_DATA_DIRS=/usr/local/share:/usr/share:/var/lib/snapd/desktop
    PATH=/home/eroxyi/.vscode-server/bin/fee1edb8d6d72a0ddff41e5f71a671c23ed924b9/bin/remote-cli:/home/eroxyi/.local/bin:/home/eroxyi/Summer2024/langchain-crash-course/google-cloud-sdk/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/lib/wsl/lib:/mnt/c/Program Files/WindowsApps/MicrosoftCorporationII.WindowsSubsystemForLinux_2.2.4.0_x64__8wekyb3d8bbwe:/mnt/c/Program Files (x86)/VMware/VMware Player/bin/:/mnt/c/Windows/system32:/mnt/c/Windows:/mnt/c/Windows/System32/Wbem:/mnt/c/Windows/System32/WindowsPowerShell/v1.0/:/mnt/c/Windows/System32/OpenSSH/:/mnt/c/Program Files/Git/cmd:/mnt/c/Users/achtu/AppData/Local/Microsoft/WindowsApps:/mnt/c/Users/achtu/AppData/Local/Programs/Microsoft VS Code/bin:/snap/bin
    DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus
    VSCODE_NLS_CONFIG={"userLocale":"en","osLocale":"en","resolvedLanguage":"en","defaultMessagesFile":"/home/eroxyi/.vscode-server/bin/fee1edb8d6d72a0ddff41e5f71a671c23ed924b9/out/nls.messages.json","locale":"en","availableLanguages":{}}
    HOSTTYPE=x86_64
    PULSE_SERVER=unix:/mnt/wslg/PulseServer
    VSCODE_HANDLES_UNCAUGHT_ERRORS=true
    OLDPWD=/home/eroxyi/nighthawk/EricY_CSA_Student/images
    VSCODE_IPC_HOOK_CLI=/run/user/1000/vscode-ipc-ba1ec4eb-05f0-40e1-b55f-e546ec106fab.sock
    _=/usr/bin/env



```bash
# Extract saved variables
source /tmp/variables.sh

cd $project

echo ""
echo "show the secrets of .git config file"
cd .git
ls -l config

echo ""
echo "look at config file"
cat config
```

    
    show the secrets of .git config file
    -rw-r--r-- 1 eroxyi eroxyi 306 Aug 27 12:26 config
    
    look at config file
    [core]
    	repositoryformatversion = 0
    	filemode = true
    	bare = false
    	logallrefupdates = true
    [remote "origin"]
    	url = https://github.com/Be1uga4life/EricY_CSA_Student.git
    	fetch = +refs/heads/*:refs/remotes/origin/*
    [branch "main"]
    	remote = origin
    	merge = refs/heads/main
    	vscode-merge-base = origin/main

