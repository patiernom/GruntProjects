# GruntProjects
Module for load project from json configuration file


## Installation
The easiest way is to keep `grunter-projects` as a devDependency in your `package.json`.
```json
{
  "devDependencies": {
    "grunt": "~0.10",
    "grunter-projects": "0.0.1"
  },
  "projectsConfig": "./config/projects.json"
}
```

You can simple do it by:
```bash
npm install grunter-projects --save-dev
```

## Configuration
```js
// Gruntfile.js
var packageJSON = grunt.file.readJSON('package.json');
grunt.initConfig({
    pkg: packageJSON,
    projects: require('grunterprojects')(packageJSON),  // Project configuration.
});
```


## Usage
You can use it into grunt task 
```js
// customGruntTask.js
var myDir = grunt.config('projects').projectDirectory
```

Or you can invoke grunt and run task of specific project
```bash
grunt --project MyCustomProject
grunt myCustomTask --project MyCustomProject 
```

----
    
## License
MIT    