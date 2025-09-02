# Git Training

## Purpose

To develop proficiency and familiarity with Git.


## Requirements

Ensure you have the following dependencies and environment setup before proceeding.

### For Windows

Install Git on your computer

CLI:
```
winget install --id Git.Git -e --source winget
```

GUI:

- Download and install throught the [Git](https://github.com/git-for-windows/git/releases/download/v2.51.0.windows.1/Git-2.51.0-64-bit.exe) executable.

### For Linux

RHEL:
```
dnf install git
```

DEB:
```
apt install git
```

## Configure Git

### For Windows

```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## Personal Repository

### Create Repository

- Go & login to [Github](https://github.com)
- On the top right of the page, click on the plus button and select `New repository`
- Give your repository any name you like and make sure that the repository is public
- Also make sure that the `Initialize this repository with a README` is *NOT* checked


### Working with a Repository
- Create a folder called git
- Under that folder created a folder with the `myProject`
- Go into that folder & create a file
- Open a terminal & navigate to where the file was created
- Run `git init`. 

<details>
<summary> What just happened? </summary>

You've just told your computer that you want git to watch the `myProject` folder and to keep track of any changes. This also allows us to run git commands inside of the folder. (Warning:  Be very careful to make sure you're in the right directory when you run `git init`!)
</details>

- Run `git remote add origin [Repository URL goes here]`. You can get your URL from going to repository you made earlier in your browser and copying the address.

<details>

<summary> What just happened? </summary>

Basically, we tell our computer "Hey, I created this repo on GitHub, so when I push, I want my code to go to this GitHub repo." Now whenever you run `git push origin master` your computer knows that origin is pointing to your repo you made on GitHub and it pushes your changes there.
</br>
( If you accidentally DID initialize your repository with a README, you must do a `git pull origin master` first - to get the README file on your computer - before you'll be able to push. )
</details>


## Post-Configuration

<details>
<summary>Toggle</summary>

Toggle text
</details>

---
>>> [!tip] Tip title
Operational information to help a user be more successful.
>>>

>>> [!note] Note title
Hightlights information that users should take into account, even when skimming.
>>>

>>> [!important] Important title
Curcial information necessary for users to succeed.
>>>

>>> [!caution] Caution title
Negative potential conquences of an action.
>>>

>>> [!warning] Warning title
Critical content demanding immediate user attention due to potential risks.
>>>

## References
- [DevMountain](https://github.com/DevMountain/learn-git)
- [Git First-Time Setup](https://git-scm.com/book/ms/v2/Getting-Started-First-Time-Git-Setup)