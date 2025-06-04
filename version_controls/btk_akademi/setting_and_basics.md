### Instructor: Atıl Samancıoğlu

∑ Git repos in GitHub website - their relation

Version control = Git

 ### **Git matters**

🛡️ Prevents catastrophic loss ("I deleted important code!")

🔍 Full history of every change (who/when/why)

👥 Enables team collaboration (multiple developers)

🧪 Safe experimentation (create branches to test ideas)

🔄 Sync work across machines

```bash
git config --global user.name "Arzunur Köroğlu"
git config user.name #for checking

git config --global user.email arz....@hotmail.com
git config user.email
```

### Basic Terms 

**commit**

**branch**

working file -git add-> index/staging -git commit-> local repository 

```bash
git status --for checking if it is wroking on that file

git init --if it is not working start it, always check git status first if you delete it with rmv -rf .git --you have to initialise again

git commit -m "your message"

git log
```
### Secret File 

-Dont put the local file this

gitignore

```bash
touch .gitignore

\\or

echo ".DS_Store" >> .gitignore
git add .gitignore
git commit -m "Ignore system files"

```
#Next step: Go to file .gitignore and write your file that you want to add eg. "gizli.txt" and then save it

#echo ".DS_Store" >> .gitignore

echo: A Bash command that prints text to the terminal or redirects it to a file.

>>: The append redirect operator that adds text to the end of a file (creates the file if it doesn't exist).

What it does:

Adds the line .DS_Store to your .gitignore file.

→ This tells Git to ignore all .DS_Store files forever.

![Versiyon Kontrolleri Git ve GitHub](https://github.com/user-attachments/assets/0c739f92-835f-4fa4-8875-f8c3b29ce3cc)


-->git branch feat-->git commint-->git switch master<--
git switch master-->git commit -->git merge feat (now they tied up again)

git branch --seeing the branches!

```bash
bash-3.2$ git branch feature
bash-3.2$ git status
On branch main
nothing to commit, working tree clean
bash-3.2$ git branch
  feature
* main
bash-3.2$ git switch feature
Switched to branch 'feature'
bash-3.2$ git branch
* feature
  main
bash-3.2$ git log

#feature de bakşak bir yere gçeitn gibi düşün!
```

git merge feature --> commit mesajı yaz "Merge breach feature"-->main içinde feature oldu

