* To view the dependencies of your app and their exact version:

  `npm list --depth=0`

* To view info about a package before downloading from the command line:  

  `npm view <package_name>`

* If you're only intereseted in seeing the package dependencies:

  `npm view <package_name> dependencies`

* Or the various released versions:

  `npm view <package_name> versions`

* To change the version for your npm package use `version` command:

  `npm version <major | minor | patch>`

* To see what packages are outdated:

  `npm outdated`

* To update npm packages run the following command. Notice that this command does not update the major version. It only updates if minor or patch releases are available.

  `npm update`



