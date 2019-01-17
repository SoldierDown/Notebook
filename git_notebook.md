# Notebook
## Initialize a repo
	echo "# Name_of_Repo" >> README.md  
	git init  
	git add README.md
	git commit -m "init"
	git remote add origin <url>
	git push -u origin master
## Remember username and password
	git config credential.helper store

## Add submodule(e.g. from another repo) 
	git submodule add <url>
	git submodule init
	git submodule update
	
