This website is built using Hugo and Hugo Blox, deployed with GitHub Pages. You can edit and commit directly on GitHub's codespace (only minor text edits), or locally (recommended for stability) by following these steps.

## 1. Set up for local development

### Windows
- Install Scoop, the Windows package manager

    ```pwsh
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    iwr -useb get.scoop.sh | iex
    # Press `Y` and Enter if asked `Do you want to change the execution policy?`. 
    ```
- Install Hugo and its dependencies

    ```pwsh
    scoop bucket add extras
    scoop install git go hugo-extended nodejs quarto
    ```

### Mac
- Install Homebrew, the Mac package manager

    ```pwsh
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
    ```
- Install Hugo and its dependencies
    ```pwsh
    brew update && brew upgrade
    brew install git golang hugo node quarto
    ```

Clone the repository and enter project folder
```bash
git clone https://github.com/shaunhoang/cml-site.git
cd ../cml-site/ # adjust accordingly
```
Inititalise project
```bash
hugo mod tidy
```
To start development server (available on `http://localhost:1313/`)
```bash
hugo server
```

## 2. Adding a Blog Post 

Blog posts are in markdown format. Render `index.md` documents from `.qmd` or `.ipynb` formats **locally before pushing** the changes to GitHub repo for build. 

1. Create a post in a new folder in `content/blog/`. The source file must be named `index` for correct rendering. E.g.
    - Markdown: `content/blog/my-post/index.md`, or
    - Quarto: `content/blog/my-post/index.qmd`, or
    - Jupyter: `content/blog/my-post/index.ipynb`
2. Include YAML front matter at the top of the `.md` and `.qmd` file (or first cell for `.ipynb` in `raw` format).
    ```yaml
    ---
    ### Required
    title: New Post
    date: 2025-05-02
    authors: # names must match names in content/authors for correct linkage
    - Shaun Hoang
    - Thomas Murat
    summary: The summary that will show up in the preview card
    draft: false
    featured: true

    ### Optional
    tags:
    - Mobility Patterns
    - Machine Learning

    # If the post is linked to any project under content/project/, add the folder's name(s), e.g. ['ai4ci','ntem']. Otherwise, leave blank.
    projects: [] 

    # Add collaterals which will show up as clickable buttons on the post
    url_code: ''
    url_pdf: ''
    url_slides: ''
    url_video: ''
    ---
    ```
3. Add a featured image in the same folder, must be named `featured.jpg`

4. Execute and render `.qmd` and `.ipynb` to `.md` locally. If the file is already `index.md` and has no executable codes, skip to next step.
    - Run from root folder (e.g. `C:\...\cml-site>`)
      ```bash
      quarto render content/blog/my-post/index.qmd  
      # or quarto render content/blog/my-post/index.ipynb
      ```
    - Verify `index.md` and `index_files/` were generated inside the folder. 

5. Commit and push to GitHub

    ```bash
    git add .
    git commit -m "Add post"
    git push
    ```

## 3. Adding members and projects

To be added

## 4. Updating publications

To be added
