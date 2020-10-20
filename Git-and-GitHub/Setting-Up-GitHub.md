# Setting up Git and GitHub: A Beginners Guide (Linux)

These steps should work on any major Linux distribution if the following dependencies are installed:
* Git
* Openssh


## Git

* Run git
* `cd` to a folder that you want to use:
	` cd Work `
* Make a folder for the repository:
	` mkdir SpartaGlobal `
* Enter the folder:
	` cd SpartaGlobal `
* Generate a key:
	 `ssh-keygen -t rsa -b 4096 -C "your_email@email.com" `
	 N.B. If just using ` ssh-keygen `, without the arguments, defaults to 2048 and RSA anyway (2048 if enough)
* Make a passphase
* Ensure you have git-agent `eval $(ssh-agent -s)`, or ssh-agent running in the background set up *re-explain this bit*
* Add the key `ssh-add id_rsa.pub`:
	* Note that the keys by default are within the ~/.ssh/ directory, so unless you are already in the .ssh directory, use the filepath .e.g. `ssh-add ~/.ssh/id_rsa.pub`
* Go to your [Github](www.github.com) and go to `Settings`
* "SSH and GPG keys" => "New SSH Key"
* Back to terminal `cat id_rsa.pub`
* Copy the entire string you see in the terminal
* Paste it in your New SSH Key window and add an appropriate title, possibly the name of the machine you are working off
* Back to terminal test your SSH to GitHub
* Do to do the final ssh setup in the terminal:
 	`ssh -T git@github.com`
* When you get RSA Key fingerprint question, press <Enter> on `yes`
* If you decide to create the ssh-key in the directory of your repository, make sure you hide or move the id_rsa and id_rsa.pub to another folder

## Repos

* Go to [Github](www.github.com) to make a new repository
* Open previously made repository in bash etc.
* Initialise the repository with:
	`git init`
* If you have files in that folder use `git add <file_name>` or `git add *` to add all (using wildcard)
* Can make README.md if want to (though GitHub can make it when you initialise the repository originally)
	 `touch README.md`
* Edit the file using a text editor .e.g. nano, vim, gedit
* Commit all the files:
	 `git commit -m "commit message"`
* Makes the "main" branch (though not entirely necessary, as a 'master' branch is made by default):
	`git branch -M main`
* Link your folder to the github repo you've created (step 1):
	`git remote add origin git@github.com:USER_NAME/Repo_name.git`
* Upload all files:
	* `git push -u origin main` or `git push` if everything has been set up
* After making a change, feel free to commit it and then push to the repository on GitHub.
* N.B. Don't need to do initialisation if cloning straight from GitHub, and just need  to do the origin step
