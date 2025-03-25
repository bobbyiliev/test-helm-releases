# Simple Test for Helm Charts releases

To deploy the Helm Chart to GitHub Pages, prepare a `gh-pages` branch with the Helm Chart files.

```bash
git checkout --orphan gh-pages
git rm -rf .
git commit --allow-empty -m "Initialize gh-pages branch"
git push origin gh-pages
```

This creates a new branch empty branch `gh-pages` and pushes it to the remote repository which will be used to host the Helm Chart files.

The workflow file `.github/workflows/helm_release.yaml` is triggered when changes are made to the chart files in the `main` branch.

The workflow will build the Helm Chart and deploy it to the `gh-pages` branch. If a release with the same version already exists, the workflow will skip the deployment.
