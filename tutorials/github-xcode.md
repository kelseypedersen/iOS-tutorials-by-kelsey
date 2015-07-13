## How to Add an Xcode Project to Github

There are two main steps to creating tracking your project on Github.

```
1) Create a local repo (Git)
2) Create a remote repo (Github)
```

In your terminal, move to your project directory by using the command "cd". Once in your Xcode project directory, check the status of your files, add the files you are looking to track, and commit those files.

### Use the commands:
```
git status
git add FILENAME
git commit -v "COMMIT MESSAGE"
```

Once committed, you are ready to connect to your Github repository. If you haven't done so yet, create a repository on Github by clicking on the green new repository button on the homepage. Create the new repo. In the new repo, you will see a link in the lower righthand corner. It automatically generates a HTTPS clone URL, but we want the SSH link. Click on the SSH link below the URL. This will generate the SSH clone URL.

```
SSH clone URL e.g.: git@github.com:kpedersen00/iOS-tutorials-by-kelsey.git
```

### Use the commands:
```
git remote add origin git@github.com:kpedersen00/iOS-tutorials-by-kelsey.git
git push -u origin master
```

And now your Xcode project is added to Github!
