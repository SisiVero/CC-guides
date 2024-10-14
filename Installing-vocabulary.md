# Integrating Vocabulary into Your Web Project

## Description
This guide will walk you through the steps to add the Creative Commons Vocabulary design system to your web project.

---

## Steps to Add Vocabulary to Your Website

1. **Clone the Vocabulary Repository:**
   Begin by cloning the Vocabulary repository to your local machine.  
   [Vocabulary Repository](https://github.com/creativecommons/vocabulary)

2. **Locate the `src` Folder:**
   Once the repository is cloned, navigate to the cloned folder and locate the `src` directory.

3. **Copy the `src` Folder:**
   Copy the entire `src` folder. This contains the necessary files for Vocabulary's styles and components.

4. **Navigate to Your Project Folder (e.g., LegalDB):**
   Go to the project folder where you want to add Vocabulary. For example, if you are working on the LegalDB project, navigate to that folder.

5. **Paste and Rename the `src` Folder:**
   Inside your project, go to the `static` folder (or the appropriate folder for static assets in your project). Paste the `src` folder here and rename it to `vocabulary` to keep things organized.

---

## Steps to Connect the Added Vocabulary to Your Website

1. **Locate the Static Folder:**
   Find the `static` folder in your project.

2. **Ensure the `src` or `vocabulary` Folder is Pasted:**
   Make sure the `src` (renamed to `vocabulary`) is pasted in the `static` folder.

3. **Identify the HTML Template with the `<head>` Tag:**
   Look for the HTML template that contains the `<head>` tag.

4. **Check How Static Files Are Connected:**
   For example, in LegalDB, you might find a line like:  
   ```html
   <link rel="stylesheet" href="{% static 'webpack_files/css/index.css' %}" type="text/css">


## Additonal Links
For additional information , click this link: https://opensource.creativecommons.org/ to learn more. 

Regards,
Joy Aruku