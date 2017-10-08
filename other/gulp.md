## Gulp basics
Build tool, running the tasks to build websites.
- compiling SASS to css
- optimizing assets (e.g.: CSS, JS, images)
- reloading the browser whenever a file change is saved

### Installation
Prerquisite: node
Save ```gulp``` as a dev dependency inside the project.
```
npm install gulp --save-dev
```

### Simple gulp tasks
Basic syntax for gulp tasks:
```
gulp.task('task-name', function(){
    //TODO something
  })
```

Simplest example:
```
const gulp = require('gulp');

gulp.task('hello', ()=>{
  console.log("Hello!");
  });
```

More realistic example:

Load the files that you want to process with `gulp.src`, pipe them through a gulp plugin, and save the results to the path specified in `gulp.dest`.
```
gulp.task('task-name', function(){
  return gulp.src('source-files')
    .pipe(aGulpPlugin())
    .pipe(gulp.dest('destination'))
  })
```

### Compile Sass to CSS

## References
1. (CSS trick on gulp)[https://css-tricks.com/gulp-for-beginners/]
