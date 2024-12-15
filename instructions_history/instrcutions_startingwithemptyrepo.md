This are notes I use when building this portfolio from an empty repository.


Portfolio template steps
1.	Video to create the github repository with readme.md file, and how to create r studio project
a.	The r studio project created the .gitignore and Portfolio_Template.Rproj files
i.	This seem to have settings required for r studio to connect to github.
2.	Adding the required files in order for the site to be built
a.	_quarto.yml
b.	Index.qmd
c.	styles.css (this file is empty but reference in the _quarto.yml)
d.	This files are not needed but use in the _quarto.yml for a png
i.	Images (folder)
3.	Adding a new tab to the portfolio. I’m adding a resume
a.	In the _quarto.yml file add, under the navbar, and this two lines of code
- text: "My Resume"
  file: resume.qmd
b.	Add/create the qmd file for your resume to the root folder
i.	Render the resume.qmd file
c.	Update yml links
i.	Build > render website
ii.	Or run this code in the console or terminal: quarto render --execute _quarto.yml
d.	Push to github and the site should be updated with your new tab.
4.	Adding python code files via R studio.
a.	Create python env for this project
i.	Or load if already one. Most likely not
ii.	Check to see correct env is loaded
b.	Install needed python libraries
i.	Or run code to install libraries in requirements.txt file 
c.	Run a qmd with python code and render it (do other steps when adding new files to the site)
d.	Create/update the requirements.txt file
e.	Push to git hub




Part 1.
1.	In your repository page, create a new repository
a.	Not using a template for this one
b.	Choose owner, for this one should just be you. 
c.	Name your repository
d.	Click on Add a README file and hit Create repository
e.	Only file currently is the README.md file
2.	Creating new project in R studio for your new repository
a.	On the main github page for your repository. Click on the green rectangle for code and copy the URL
b.	Create new project in R-studio
i.	Open up r studio, and create a new project
ii.	Click on Version Control - then on Git and paste the url in the Repository URL: section
iii.	Under Create project as subdirectory, make sure your path is in your hardrive. 
iv.	Create Project
c.	This steps should have created the .gitignore, Portfolio_template, and two normally hidden folders (.git and .Rproj.user [.Rproj.user folder (this doesn't affect your files, but clears RStudio's cache for the project).] )
i.	.gitignore settings
1.	The non-working project ignores files like .Rhistory, .RData, and .Ruserdata. These are harmless and irrelevant for website rendering or Build tab visibility.
2.	This is interesting to know this files are ignore because I use em all the time so it pays to research this. 
ii.	
Part 2
1.	Add the _quarto.yml, index.qmd and styles.css files need to build the website. 
a.	Other files can be added but this are the only ones needed for this template
i.	You can edit as much as you want here and add anything you want. I’m just showing what is required for this template to be built. Limit editing if unfamiliar with github pages. 
b.	Render Website
i.	Run this command in the console
1.	quarto::quarto_render()
2.	restart r studio. (this code can also be ran in an r chunk as well)
ii.	The goal of this command is to let r studio know this is a _site and gives the option to build site and render website (option next to git)
c.	Render the website using the build option in r studio
i.	After using the manual render site, github should now have an option to build > render website. 
1.	Render website use this code
quarto::quarto_render()

2.	Push to github
a.	Once you render the index file, push to github ( git add . ---- git commit -m”update” ---- git push)
b.	On the github repository, go to settings/pages and under branch
i.	Set Branch to main and set folder to /docs and hit save
1.	Once you hit save, github will know to deploy the site.
c.	If done correctly the site should be live. 


Part 3
Not to complicated

Part 4. Working with Python code, enviroment, and requirements.txt files in R-studio
step 1. Check what environment is active (likely a global environment)
library(reticulate)
py_config()

step1.7: create virtual env if needed (basically needed in any new device)
library(reticulate)  # I wonder if the line below can stand alone
virtualenv_create("env") # env is the name which can be anything, but will use env for instructions

step 1.5: load env for project if needed, so use code from step 1 to make sure the new env is loaded. If not use this to load the new env. Again replace env with the actual name you gave your env.
library(reticulate)
use_virtualenv("env", required = TRUE)

Step 2. Install python libraries 
library(reticulate)
py_install(c("pandas", "numpy", "matplotlib"))

step 2.1: run python code/file and render python files

Note that when rendering an .ipynb Quarto will not execute the cells within the notebook by default (the presumption being that you have already executed them while editing the notebook). 

Step 3 : creates/updates the requirements.txt file
shell("pip freeze > requirements.txt")





Part 5

Step 1: 
Adding tab with a sidebar for multiple qmd files
	- add tab to navbar and sidebar code to _quarto.yml
Step 2: 
Add qmd for the main tab, add folder with qmd files for main tab
