# General overview of Fork/Pull-Request:

The following steps describe the standard flow.

*Steps 1 and 2 are only necessary the first time we create a new fork and we configure our local copy*
## 1. Fork the repository via Web 
Using the web interface, we create a new `fork` of the main (Upstream) repository

## 2. Clone the Forked repository to our local machine
* Clone the forked repository
```
$ git clone [MyFork_URL_Repository]
```

* 2.1 We specify the upstream, i.e., the remote main repository. This is done *only ONCE* for a new local copy of our forked repository
```
$ cd [Directory_cloned_repository]
$ git remote add upstream [URL_MAIN_Repository]
```

## 3. Update our local copy of the fork with the latest version of the Upstream repository (a.k.a *Pull and Rebase*)

BEFORE any change in our local copy, we should always get the latest version of the Upstream repository and update our Fork. In this case the fork will be updated in the `master branch`

* Switch to the master branch
```
$ git checkout master
```

* Get the latest version of the `master` branch from the `upstream` and merge it with the local copy current branch (`master`)
```
$ git pull upstream master
```


## 4. Once our local copy is updated we push changes into the Fork:
* Push the merged local copy to update the fork
```
$ git push origin master
```
* Now we have an updated fork. If we check the web interface, our fork should be "even" with the upstream.

## 5. Create the new branch for the `feature` we are going to work on and Send the `Pull request`

* Create a new branch to work on, e.g., *feature_xyz*
```
$ git checkout -b feature_xyz 
```

* *Work on all changes and modify code in local repository ...*


* Add the files/directories with changes to be commited
```
$ git add FILE1, FILE2, ...
```

* We can verify which files are going to be commited
```
$ git status
```

* Commit changes with a message using option `-m` (*or use any local editor skipping `-m` option*)
```
$ git commit -m "Commit change xyz"
```


* Push the changes into the branch `feature_xyz` of the Fork
```
$ git push origin feature_xyz
```

* Go to our fork, via web, and send the `Pull Request` (green button)
---
If the Pull Request is accepted, our changes will be merged into the main repository (upstream). And remember, we can always verify that our fork has the latest changes of the upstream (steps 3 and 4):


```
$ git checkout master
```
```
$ git pull upstream master
```

```
$ git push origin master
```

Flow example *(extracted from the web)*:

![gitflow](gitflow.png)


**Important Note**: *The steps in this tutorial refer to `main` branch as `master` branch. The name of the `master` branch was recently changed in Github. If the forked/cloned repository refers to the main branch as the new name `main`, then just change the corresponding commands.*

