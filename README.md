# Gulp-scss
gulpjs complier scss to css with browser sync

# Some notes

1. npm install gulp-cli -g
2. npm install gulp
3. npm i
4. npm init
5. npm install --save-dev gulp gulp-sass browser-sync



6. Create a gulpfile.js 

const gulp = require('gulp');
const sass = require('gulp-sass');
const browserSync = require('browser-sync').create();
//compile scss into css
function style() {
    return gulp.src('stylesheets/scss/**/*.scss')
        .pipe(sass().on('error', sass.logError))
        .pipe(gulp.dest('stylesheets/css/'))
        .pipe(browserSync.stream());
}

function watch() {
    browserSync.init({
        server: {
            baseDir: './'
        }
    });
    gulp.watch('stylesheets/scss/**/*.scss', style)
    gulp.watch('./*.html').on('change', browserSync.reload);
    gulp.watch('./js/**/*./js').on('change', browserSync.reload);
}
exports.style = style;
exports.watch = watch;


7. create a stylesheets folder and in the same folder, create another sass/scss folder and create scss file like : main.scss

8. run command gulp watch



# parveen545@gmail.com