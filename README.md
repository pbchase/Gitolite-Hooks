Gitolite hooking system + hooks.
===

This is a very simple system for adding hooks to your gitolite repositories. Barely any public hooks here for now but will grow the list over time. Info on setting it up can be found at http://demonastery.org/2012/09/a-hooking-system-for-gitolite/.

*Most of these will probably need some editing to work with your setup, so make sure to check out the code before blindly running them.*

License.
---

Consider the scripts here to be in the public domain. However any contributions will be highly valued!

Available Hooks.
===

test-print
---

Prints out some information for debugging: Working directory, $GIT_DIR, $oldrev, $newrev, $refname.

update-redmine-repositories
---

Triggers your local Redmine instance to update all configured repository changesets. More info at http://demonastery.org/2012/10/a-redmine-hook/.

generate-documentation
---

Builds project documentation to /srv/documentation/PROJECT-NAME/ using Doxygen.

checkout
---

Checkout HEAD of the repository into /tmp/git/PROJECT-NAME/ for further manipulation.

jekyll
---

Use Bundler and Jekyll to build /tmp/git/PROJECT-NAME/jekylldocs/ to /tmp/git/PROJECT-NAME/htdocs/. Requires `checkout` hook to be specified before this one. Hook will not run if /tmp/git/PROJECT-NAME/jekylldocs/_config.yml is missing, so is safe to run on all web repositories.

nginx-deploy
---

Copies a checked out and built project from /tmp/git/PROJECT-NAME/ to /www/PROJECT-NAME. Will also symlink and reload Nginx configuration.
