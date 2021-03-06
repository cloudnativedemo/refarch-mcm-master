# Reference Architecture for IBM Multi-Cloud manager

Git project to share deliverables of multi-cloud manager.

## Cookbook for MCM Solution Architects

## Viewing the Cookbook

The HTML-readable version of the cookbook is available via https://pages.github.ibm.com/CASE/refarch-mcm/.

## Building the Cookbook locally

The Cookbook for ICP Solution Architects is written to support [MkDocs](https://www.mkdocs.org/) and can be built into a book-readable format by following standard Markdown writing styles and MkDocs build processes.

1. Install MkDocs locally following the [official documentation instructions](https://www.mkdocs.org/#installation).
2. Clone the code and serve pages locally as follows:
	```bash
	git clone git@github.ibm.com:CASE/refarch-mcm.git
	cd refarch-mcm/cookbook
	mkdocs serve
	```
3. Go to http://127.0.0.1:8000 in your browser.

## Pushing the Cookbook to GitHub Pages
**FORK** this repository first, then clone it as follows:
```bash
export GITHUB_USERNAME=PUT_YOUR_GITHUB_USERNAME_HERE
git clone git@github.ibm.com:${GITHUB_USERNAME}/refarch-mcm.git
cd refarch-mcm/cookbook
```

1. Ensure that all your local changes to the `master` branch have been committed and pushed to the remote repository.
   1. `git push origin master`
2. Ensure that you have the latest commits to the `gh-pages` branch.
	```bash
	git checkout gh-pages
	git pull origin gh-pages
	git checkout master
	```
3. Run `mkdocs gh-deploy` from the [cookbook](cookbook/) directory.  Note that the `gh-deploy` command will fail if you do not have the latest commits to the branch pulled locally.
	* If you have git remote links for both this repository and your fork, you will need to run the command with an extra flag. For example, here is a local clone of the code that has 2 remote repos: `fabio` (fork) and `origin` (main repo):
	```bash
	fabio	git@github.ibm.com:fabiogomez/refarch-mcm.git (fetch)
	fabio	git@github.ibm.com:fabiogomez/refarch-mcm.git (push)
	origin	git@github.ibm.com:CASE/refarch-mcm.git (fetch)
	origin	git@github.ibm.com:CASE/refarch-mcm.git (push)
	```
	* To deploy the MkDocs pages to the `fabio` repo, you will need to run the command as `mkdocs gh-deploy -r fabio`
4. Open `https://pages.github.ibm.com/${GITHUB_USERNAME}/refarch-mcm/` to see 

## IMPORTANT: Contributing to this Repository
If you would like to contribute to this repository, please do the following:
* Fork this repository.
* Commit your updates.
* Push your updates to `master` branch in your fork.
* Open a Pull Request (PR) against the `master` branch on this repository.
* Assign either @gangchen or @fabiogomez as reviewers.

The PR will only be merged after at least one of the above reviewer approves the PR. 

### Contributing new Page Updates (MkDocs)
If you are submitting new content updates to the MkDocs page, you will need to do the following additional steps to the PR:
* Make sure you have built and pushed the MkDocs page to your fork as explained in [Pushing the Cookbook to GitHub Pages](#pushing-the-cookbook-to-github-pages).
* Put a link to your page in the PR so that reviewers can see what the content updates look like before merging the PR.

Once the PR is merged to `master` branch, one of the reviewers will be responsible for deploying the new content updates to the main repo's `gh-pages` branch.