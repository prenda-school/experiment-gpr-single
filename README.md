# experiment-gpr-single
Part of "Experimenting with GitHub Packages".

This is a repository publishing a single package. ("gpr" = "GitHub Packages registry"; comes from their workflow action)

### Guide (specific to our organization)
**Scenario 1:** New respository. 
  - Follow the "Quickstart" source below. 
    - Where applicable, replace _`YOUR_USERNAME`_ with `@prenda-school`.
    - In Step 8, prefer to use the `"publishConfig"` option instead of the `.npmrc` option.

**Scenario 2:** Existing repository.
  - Edit the `"name"` field in the `package.json` file to be of format `"@prenda-school/REPOSITORY_NAME"`
  - Edit the `package.json` file and specify the `publishConfig` key: 
```json
"publishConfig": {
   "@prenda-school:registry": "https://npm.pkg.github.com"
 }
 ```
   - If necessary, add or modify your deployment workflow file to run the follow step in the appropriate job:
```yml
- run: npm publish
  env:
    NODE_AUTH_TOKEN: ${{secrets.GITHUB_TOKEN}}
 ```

#### Sources: 
- Quickstart: https://docs.github.com/en/packages/quickstart
  - Biases towards GH Packages personal repo view.
    - @_YOUR_USERNAME_ = @_prenda-school_ (organization username)
  - Personal authentication concerns are bypassed by using workflow action
  - Once published, wait a minute for it to appear as a connected package under the repository homepage (and organization profile -> packages tab).
- Reference: https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#publishing-a-package
  - Prefer "[Publishing a package using publishConfig in the package.json file](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#publishing-a-package-using-publishconfig-in-the-packagejson-file)" since it's a self-explanatory field, and one less file (but there's no harm in having both).

#### See more 
- [repository publishing multiple packages](https://github.com/prenda-school/experiment-gpr-multiple)
- [repository consuming (installing) packages from gpr and npm registry](https://github.com/prenda-school/experiment-gpr-consumer)
