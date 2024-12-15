## Instructions for Setting Up and Using the Repository

This is a Portfolio template, and the instructions are mostly around working with the yml and setting up the website portfolio to be live.
This steps would also show you h0ow to manage and constantly update your portfolio. The QMD files are mostly empty, but you can add anything you want to them as the goal of this portfolio is to showcase what you can do. 


## the following is a short list of what is cover in the index.qmd file 
1. **Using the Template and Cloning the Repository**
   - Select “Use as template,” name it, and set it to public.
   - Configure GitHub Pages:
     - **Branch**: main
     - **Folder**: docs
     - Save and verify the site goes live.

2. **Setting Up the R Project**
   - Create an R project for the portfolio.
   - Verify the connection to the repository:
     ```
     git remote show origin
     ```
   - Push changes to GitHub to build the site using GitHub Pages.

3. **Editing and Customizing**
   - Update `.qmd` files to showcase your portfolio.
   - Render locally and push changes to publish updates.

4. **Optional: Working with Python Code**
   - Enable Python chunks in `python.qmd` by removing the `#` from `{python}`.
   - Set up Python environment:
     - Check environment:
       ```R
       library(reticulate)
       py_config()
       ```
     - Create and load a virtual environment:
       ```R
       virtualenv_create("env")
       use_virtualenv("env", required = TRUE)
       ```
   - Install Python libraries:
     ```R
     shell("pip install -r requirements.txt")
     py_install(c("pandas", "numpy", "matplotlib"))
     ```
   - Update the `requirements.txt` file:
     ```R
     shell("pip freeze > requirements.txt")
     ```
   - Render `python.qmd` to validate Python code execution in RStudio.

5. **Adding New Tabs**
   - Add a new tab (e.g., "Resume") by updating `_quarto.yml`:
     ```yaml
     text: "My Resume"
     file: resume.qmd
     ```
   - Create and render the `resume.qmd` file.
   - Push changes to update the site.

6. **Adding a Project Tab with Multiple Files**
   - Update `_quarto.yml` with navbar and sidebar code.
   - Create a folder with `.qmd` files for the tab.
   - Render and push to update the site.

7. **Working with Python Code and Environment in RStudio**
   - Check the active Python environment:
     ```R
     library(reticulate)
     py_config()
     ```
   - Install and manage Python libraries as needed.
   - Render `.qmd` files containing Python code.

