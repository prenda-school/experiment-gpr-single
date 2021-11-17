# experiment-gpr-single
Part of "Experimenting with GitHub Packages".

This is a repository publishing a single package. ("gpr" = "GitHub Packages registry"; comes from their workflow action)

#### Sources: 
- Quickstart: https://docs.github.com/en/packages/quickstart
  - Biases towards GH Packages personal repo view.
    - @_YOUR_USERNAME_ = @_prenda-school_ (organization username)
  - Personal authentication concerns are bypassed by using workflow action
  - Once published, wait a minute for it to appear as a connected package under the repository homepage (and organization profile -> packages tab).
- Reference: https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#publishing-a-package
  - Prefer "[Publishing a package using publishConfig in the package.json file](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#publishing-a-package-using-publishconfig-in-the-packagejson-file)" since it's a self-explanatory field, and one less file (but there's no harm in having both).
  - Under these directions, the `(package.json)["respository"]` field was changed from
```json
  "repository": {
    "type": "git",
    "url": "git+https://github.com/prenda-school/experiment-gpr-single.git"
  },
```
to
```json
  "repository": "git://github.com/prenda-school/experiment-gpr-single.git",
```

#### See more 
- [repository publishing multiple packages](https://github.com/prenda-school/experiment-gpr-multiple)
- [repository consuming (installing) packages from gpr and npm registry](https://github.com/prenda-school/experiment-gpr-consumer)
