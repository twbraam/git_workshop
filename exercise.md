# Group Exercises for Understanding GitHub

## Git Haiku

This is an exercise that works best with 3-4 people working from a single git repo. The aim is to demonstrate in a simple fashion how Github treats file merges, and how merge conflicts arise.
Your group is going to practice git flow, and get a little creative at the same time!

Preparatory steps:
* Nominate a repo owner
* Create a repo on github
* Add all the group as collaborators on the repo
* The repo owner should initialise the exercise by cloning the repo, and creating two files (haiku.md and one-line-test.md) on a local branch.
* haiku.md should have a one line introduction ("Hello World!" or similar) on line one, and a goodbye line ("Goodbye world!") however, the important part is to leave three blank lines for each member of the group. In a four person group, line 1 will say "Hello world!", lines 2-13 will be blank, and line 14 will have a goodbye message.
* one-line-test.md should have a "Hello world!" message on line one, and a single line of text on line 2 ("Replace me!").
* The repo owner should save these files and push them to a remote branch, and create a pull request to the master branch. Someone else should review it and approve it!

Now the fun begins...

* Each group member should clone the repo (or pull a fresh copy if they have already cloned it).
* The repo owner assigns each group member a block of three empty lines to work on (2-4, 5-7, 8-10, 11-13).
* Each group member then writes a haiku on their assigned three lines between the hello world message and goodbye world message.
* A [haiku](https://en.wikipedia.org/wiki/Haiku) is a three line Japanese poetry form, with five syllables on the first line, seven on the second, and five on the final line.
* To create a Haiku, creative minds can create their own. Otherwise, use [CHAT-GPT](chat.openai.com/) or [Bing (GPT-4)](https://www.bing.com/search?q=Bing+AI&showconv=1).
* Once each group member has penned their masterpiece, they should save it and push it to a remote branch on the repo.
* Everyone should create pull requests all at once - This simulates the worst possible case of four people trying to alter the same file at the same time.
* Once the pull requests have been created, each group member should take it in turn to review the merge requests.
* As you will see while merging, github can automatically merge each and every request, without issue, because it can detect that the file changes aren't deleting anything, and they aren't overwriting anything that has been committed since the pull request was created.
* But beware, this is the best case scenario for merge conflicts - the reason that you should pull and merge master copies on the local branch prior to pushing commits is that most merge conflicts involve people deleting or altering the work of others.

The second round begins in the same way. This time, the group works on the one-line-test.md file at the same time.
* Each group member should pull the updated master, and overwrite line 2 with something - anything - that comes to mind.
* Save changes and push to the remote origin, and then create simultaneous pull requests.
* As you take turns to merge another person's pull request with the master branch, you'll note that the first merge is fine - github has no problem with people overwriting files!
* The second attempt to merge another person's pull request will, however, cause an error. Github will instruct you that it cannot automatically merge the request, and that you will need to solve the problem on your local branch.
* Now each team member is going to have to pull the new master down to their local master branch, merge the master with their local branch, and push the result.
* This process will keep repeating! As you will see, it could take four people almost ten minutes to resolve the issues from attempting to write one line at the same time.
* Hopefully after this, you will understand why it is important to check the most up to date master branch before pushing to a remote branch, and creating a pull request to the master branch.
* You can run this test a second time, with each person waiting to pull the updated master, overwrite it in their local branch, and pushing to a remote branch to create a pull request to the master. As you will see, a little communication and co-ordination goes a long way!