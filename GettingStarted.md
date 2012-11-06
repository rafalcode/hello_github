## Getting started with Git and Github

So you've decided to show off your coding skillz, you've used a little git and you've heard of the popular github site. This is a small account of the steps you'll have to go through.

## Preliminaries
Of course you'll have to have git set up on your local machine. And you will indeed have to create a userid on the github site. If you're like me you'll favour ssh for communicating with remote hosts, so as soon as you have your github account, yuo'll want to paste in your public key into the appropriate section of github's account settings.

## Global configure variables in you local user

```
git config --global user.name <mygithubuserid>
git config --global user.email <mygithubemail>
```
I'm not sure if these exactly need to be based on your github identity, because the documents don't say, and I actually suspect they don't have to be, but, as usual, it's best to err on the side of caution.

## Clarifying some ambiguous terms
The git repository will be represented by a filename with a **.git** extension on the Github website. Over on your local compute, you will probably have a subdirectory in which the repository's code and files can be found.

## Pulling a repository from remote
There may be a better way to do this, but a simple
```
git remote clone
```
will do, but this will also obtain for you the remote handle, probably called **origin** so althgouh the rest of the code will be fine, the remote handle may not be and you will need to remove it. See the next section.

## Spare a thought for the Remote handle
You do need to organize a type of channel from your local repository to the remote respository (probably github) and it's critical that this is matched with the communication possiblities, by which I mean the ssh you set up in the beginning.

The following command will let you see which remote handles are up. By the way, you need to be in the repository's subdirectory to see them properly, because they are - of course - specific to each repository.
```
git remote -v
```
the **git://** prefix on a remote handle is not what you will want when using ssh, so you will want to remove them. But first let's create a new remote handle for ssh
```
git remote add <remoteshortname> git@github.com:<githubuserid>/<reponanme>.git
```
Now you can go and delete the **git://** handle
```
git remote rm origin
```
I havenb't replaced **origin** here with a placeholder, because it's nearly always called origin.

## Branch navigation
If there's one thing that's almost too easy in git, it's to create and navigate to a new branch. It's as easy as:
```
git checkout -b <newbranchname>
```
To see on which branch you are sitting (which is a good way of thinking about it), you'll need the following command:
```
git branch
```

## You want a branch you create locally to be also on the remote repository.
This by no means is done automatically, and so you the following command to get the branch uo ther pr

## Routinely, you'll be doing this:
```
git add <list of changed file>
git commit -m "my comments for the latest patch"
git push <remotehandle
```
