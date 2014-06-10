# gulp-folder

Gulp plugin that lets you work with folders and treat them as package names

## Install

```
npm install gulp-folder --save-dev
```

## Usage

```javascript
var gulp = require('gulp'),
	path = require('path'),
	folder = require('gulp-folder'),
	path = 'path/to/folder';

gulp.task('task', folder(path, function(folder){
	return gulp.src(path.join(path, folder, '*.js'))
		.pipe(concat(folder + '.js'))
		.pipe(gulp.dest(paths.dest));
}));
```

# Rationale

This gives you a perfect solution to build different packages out of folders.
Given this structure:

```
path
  to
    folder
	  main
	    jquery.js
		ember.js
	  secondary
	    plugin.js
```

it is very easy to build

```
dist
  folder
    main.js
	secondary.js
```