## Git

* Run git (Linux/Mac) or gitbash (Windows)
* `cd` to a folder that you want to use:
	` cd Work `
* Make a folder for the repository:
	` mkdir SpartaGlobal `
* Enter the folder:
	` cd SpartaGlobal `
* Generate a key:
	 `ssh-keygen -t rsa -b 4096 -C "your_email@email.com" `
	 N.B. If just using ` ssh-keygen `, defaults to 2048 and RSA anyway (2048 if enough)
* Make a passphase
* Ensure you have git-agent `eval $(ssh-agent -s)`, or ssh-agent running in the background set up
* Add the key `ssh-add key.ssh`
* Go to your [Github](www.github.com) and go to `Settings`
* "SSH and GPG keys" => "New SSH Key"
* Back to terminal `cat key.ssh.pub`
* Copy the entire thing you see in terminal
* Paste it in your New SSH Key window and add a title
* Back to terminal test your SHH to GitHub
* Do to do the final ssh setup:
 	`ssh -T git@github.com`
* When you get RSA Key fingerprint question => `yes`
* Hide your `key.ssh` and `key.ssh.pub` somewhere safe:
	* Usually shows up as id_rsa and id_rsa.pub in the ~/.ssh/ folder if made on Linux etc, so don't have to worry about hiding it since it will not be in the repository.

## Repos

* Go to [Github](www.github.com) make a new repo
* Open previously made repository in bash etc.
* `git init` => Initialize a repo
* If you have files in that folder use `git add <file_name>` or `git add *` to add all (using wildcard)
* Can make README.md if want to (though GitHub can make it when you initialise the repository originally)
	- `touch README.md`
* Edit the file using a text editor .e.g. nano, vim, gedit
* `git commit -m "commit name"` => Commit all the files
* `git branch -M main` => Makes the "main" branch
* `git remote add origin git@github.com:USER_NAME/Repo_name.git` => Link your folder to the github repo you've created (step 1)
* Upload all files:
	* `git push -u origin main` or `git push` if everything has been set up
* After making a change, feel free to commit it and then push to the repository on GitHub.
* N.B. Don't need to do initialisation if cloning straight from GitHub, and just need  to do the origin step
