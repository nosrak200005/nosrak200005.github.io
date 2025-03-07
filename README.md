
# Hosting a Static Resume Website Using Pelican and GitHub Pages

## Statement of Purpose:
This document serves as a detailed guide for anyone looking to deploy and maintain a static website using Pelican and GitHub pages. This guide is meant to be very simple and easy to follow so that anyone with basic technical knowledge is able to follow. The intended audience for this guide is someone who has basic knowledge of files, folders, and simple command line operations but is new to tools like Git, Pelican, and GitHub Pages.  
This guide is designed to help users set up a professional, lightweight, static website that follows the best practices in technical writing in order to setup a website for an online resume. It also demonstrates how Etters core principles like “Use Lightweight Markup”, “Use Distributed Version Control”, and “Make Static Websites” can be applied in practice. By using markup languages, distributed version control, this guide aligns with industry-wide standards practices which allow for a much more efficient, scalable, and professional online resume.

---

## Prerequisites:
Before we start creating your static site you need to install or setup the following:

1. **Git**  
   As recommended by Etters “Use Distributed Version Control” principle, we rely on Git which will track changes as well as make collaboration easier.  
   If not installed on your device yet, please download and install it from here: [https://git-scm.com/](https://git-scm.com/)  
   After installing, open command prompt and verify it installed successfully by typing:
   ```
   git --version
   ```

2. **Python**  
   Python is required for running Pelican and can be installed here: [https://www.python.org/downloads/release/python-3132/](https://www.python.org/downloads/release/python-3132/) if not already installed or on old firmware.  
   Verify installation or update status by typing:
   ```
   python --version
   ```

3. **Pelican**  
   This guide uses Pelican for static site generation because Etter repeatedly recommends static site generators for their speed and simplicity.  
   To install Pelican with markdown support please type the following command in command prompt and type:
   ```
   python -m pip install "pelican[markdown]"
   ```

4. **GitHub account**  
   As recommended by Etters approach to “Publish Frequently”, were going to use GitHub pages to host our site. Create an account at [https://github.com/](https://github.com/) if you do not have one already.

5. **Resume In Markdown**  
   Following the “Use Lightweight Markup” principle by Etter you are going to write your Resume in Markdown to easily edit, version, and publish to static site generators like Pelican. You are able to create Markdown files in many text editors.

---

## Instructions:

### 1. Create a Local Pelican Website

**a. Navigate to a folder where you want your Pelican project.**  
For example, type:
```
cd C:\Users\YourName\Documents\MyPelicanSite
```

**b. Run the Pelican QuickStart**  
Type:
```
pelican-quickstart
```

**c. The following questions will then pop up please enter the following:**
>Where do you want to create your new web site? [.] (click enter)  
>What will be the title of this web site? (enter the name of site you want)  
>Who will be the author of this web site? (enter your name)  
>What will be the default language of this web site? [English] (click enter)  
>Do you want to specify a URL prefix? e.g., https://example.com (type: Y)  
>What is your URL prefix? (see above example; no trailing slash) (type your domain name from GitHub here which would be https://yourname.github.io)  
>Do you want to enable article pagination? (Y/n) (type Y)  
>How many articles per page do you want? [10] (type the number of pages your want)  
>What is your time zone? [Europe/Rome] type (America/Winnipeg)  
Do you want to generate a tasks.py/Makefile to automate generation and publishing? (Y/n) (type y)  
>Do you want to upload your website using FTP? (y/N) (type N)  
>Do you want to upload your website using SSH? (y/N) (type n)  
>Do you want to upload your website using Dropbox? (y/N) (type n)  
>Do you want to upload your website using S3? (y/N) (type n)  
>Do you want to upload your website using Rackspace Cloud Files? (y/N) (type n)  
>Do you want to upload your website using GitHub Pages? (y/N) (type y)  
>Is this your personal page (username.github.io) (y/N) (type Y)

After you type this in your local website template should be created.

### 2. Add your Markdown Resume

**a. Create your Resume In Markdown**  
- In a text editor, write your resume in Markdown and save it as `resume.md`

**b. Place `resume.md` in the content folder**  
- Move your `resume.md` file into the content folder which is in the root of the directory of your Pelican Site. This way, pelican can process it when building the site.  
- This aligns with Etters “Don’t Duplicate” Principle, since you keep only one source file for your resume

### 3. Generate your local website

**a. Run the Pelican Build Command**  
In command prompt navigate to the root folder of your Pelican site and type:
```
pelican content
```

**b. Preview the Website Locally**  
Type:
```
pelican --listen
```
This should host your website locally and you are able to view it at [http://localhost:8000/](http://localhost:8000/). You should see your site, including a link or page for your resume.md

### 4. Upload your site to GitHub Pages

**a. Initialize Git**  
In command prompt type:
```
git init
```

**b. Add a Remote Origin:**  
On GitHub create a repository named `YourUserName.github.io`  
- Now connect it locally by typing:
  ```
  git remote add origin https://github.com/YourUserName/YourUserName.github.io.git
  ```
- Confirm it works by typing:
  ```
  git remote -v
  ```

**c. Add and Commit Files**  
- Stage Everything by typing:
  ```
  git add .
  ```

**d. Commit:**  
```
git commit -m "Initial Pelican site"
```

**e. Set your default branch to main:**  
```
git branch -M main
```

**f. Then push:**  
```
git push -u origin main
```
- If prompted, log into GitHub and afterwards your Pelican source will be on GitHub  
- After a few minutes your site will be hosted at https://YourUserName.github.io

---

## Further Resources
- **Pelican Documentation** - Official Pelican documentation, covering themes, plugins, and advanced configuration.  
- **GitHub Pages Guide** - Learn more about hosting static sites on GitHub.  
- **Markdown Cheat Sheet** – Markdown tutorial with examples  
- **Modern Technical Writing – Andrew Etter** - Etter’s short book on efficient, modern documentation techniques.

---

## Frequently Asked Questions (FAQ)
**Why use Markdown instead of writing raw HTML?**  
Markdown is simpler, more readable, and widely supported in static site generators. Unlike raw HTML, Markdown allows users to write in a clean format without worrying about syntax errors. This is also recommended by Etter’s to keep the process lightweight.

**Why doesn’t my site update immediately after pushing to GitHub Pages?**  
GitHub pages may take several minutes to publish. Clearing your browser cache or forcing a refresh can help.

---

## Credits
- **Created by:** Karson Perche  
- **Peer Reviewed by:** Colin Courney and Krupal Patel
````