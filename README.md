# [PyData Tel Aviv JupyterLab Extension Tutorial](https://telaviv2023.pydata.org/cfp/talk/3JNZUQ/)

## [The slides can be found by clicking here.](https://github.com/DanielGoldfarb/pydjlx/blob/main/Slides.pdf)  
### Note that GitHub only displays a few slides at a time, so I suggest that after clicking the above link, then click the download button on the right side of that page to download the whole slide deck.

---
---

## Steps in Detail:

## Step 0: Copier Extension Template (basic do-nothing extension)
1. ```bash
   # create the conda environment
   conda create -n jlx --override-channels --strict-channel-priority -c conda-forge -c nodefaults jupyterlab=4 nodejs=18 git copier=7 jinja2-time
    ```
2. ```bash
   # activate the conda environment:
   conda activate jlx
   ```
3. ```bash
   # copier copy <template> <destination>
   copier copy https://github.com/jupyterlab/extension-template pydjlx   
   ```
4. ```bash
   # cd into the project directory
   cd pydjlx

   # take a look at the files that were created by the copier template:
   ls -l  
   ```
5. ```bash
   # optionally create a git repository for the extension package:
   git init
   git add .
   git commit -m 'step0: template extension'
   ```
6. ```bash
   # install our extension's dependencies so that we can build the extension:
   jlpm install

   # confirm that yarn.lock and node_modules were created:
   ls -ltr 
   ```
7. ```bash
   # build the extension
   jlpm run build
   # Did the build end with "... compiled successfully in ... ms"?
   ```
8. ```bash
   # list currently installed extensions:
   jupyter labextension list
   # note that the above out also shows the directory where the isntalled extensions were found.
9. ```bash
   # install our extension as a symbolic link:
   jupyter labextension develop --overwrite ./

   # confirm the install:
   jupyter labextension list
10. ```bash
    # Open another command/linux window, 
    # activate our conda environment, and run jupyter lab:

    conda activate jlx
    jupyter lab
    ```
11. **Confirm that you see "Jupyterlab extension pydjlx is activated!"**  
    1. In the browser window where JupyterLab is running, ***open the browser console***
    2. In Chrome, the console is under "More Tools" --> "Developer Tools".
    3. Confirm that you see **"Jupyterlab extension pydjlx is activated!"**  

---

## Next, for each of Steps 1 through 7:
### 1. Make the [**code change indicated below:**](https://github.com/DanielGoldfarb/pydjlx/blob/main/README.md#code-changes).
### 2. **`jlpm run build`**
### 3. Refresh browser, and test.

## Code Changes:
* [**Step1 :** Create a command in the command registry](https://github.com/DanielGoldfarb/pydjlx/commit/651a7b19ed62a9ff7ef6951a54d94abbd52cb12c)
* [**Step2 :** Execute command from ICommandPalette](https://github.com/DanielGoldfarb/pydjlx/commit/47ae7a17d8e9bbf7756e97707c82a6c30dfe0d37)
* [**Step3a:** Split out activate function](https://github.com/DanielGoldfarb/pydjlx/commit/89b32227e57be1e4ca7a48676139fab3dd810274)
* [**Step3b:** Add widget to main area](https://github.com/DanielGoldfarb/pydjlx/commit/e540b2105f45180967e6f9bc2fce373a51ff5d28)
* [**Step4 :** Style the widget](https://github.com/DanielGoldfarb/pydjlx/commit/e329c978798e195b921bd8ba542f0dbfd9503427)
* [**Step5a:** Execute command from the Launcher](https://github.com/DanielGoldfarb/pydjlx/commit/37d9f6ebdceaa2949f9fa7e599c737eb80a989d4)
* [**Step5b:** jlpm add @jupyterlab/launcher](https://github.com/DanielGoldfarb/pydjlx/commit/e42e500d6e2f58c82ac73b2a3672a894d6be8033)
* [**Step6 :** Execute command with arguments](https://github.com/DanielGoldfarb/pydjlx/commit/4af11ebe839e1aa4297a0d535c548ba5026bf6b6)
* [**Step7a:** Create Side-bar widget with buttons](https://github.com/DanielGoldfarb/pydjlx/commit/905fc1cbb98dc37ee9ecaf984a964b6b5ebba6f6)
* [**Step7b:** Style side-bar widget](https://github.com/DanielGoldfarb/pydjlx/commit/5af8bba9f3ba371a337c8380503792a2bb6384d7)
* [**Step7c:** Add event listeners on buttons](https://github.com/DanielGoldfarb/pydjlx/commit/098ffcffef9d1085a928e39114f512a30f8d38b8)
