# gulp-htmlhint [![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency Status][depstat-image]][depstat-url]

> [htmlhint](https://github.com/yaniswang/HTMLHint) wrapper for [gulp](https://github.com/wearefractal/gulp) to validate your HTML


## Usage

First, install `gulp-htmlhint` as a development dependency:

```shell
npm install --save-dev gulp-htmlhint
```

Then, add it to your `gulpfile.js`:

```javascript
var htmlhint = require("gulp-htmlhint");

gulp.src("./src/*.ext")
	.pipe(htmlhint())
```

## API

### htmlhint(options)

See all rules here: [https://github.com/yaniswang/HTMLHint/wiki/Rules](https://github.com/yaniswang/HTMLHint/wiki/Rules)

If options is empty, task will scan nothing.

#### options.htmlhintrc
Type: `String`
Default value: `null`

If this filename is specified, options and globals defined therein will be used. Task and target options override the options within the `htmlhintrc` file. The `htmlhintrc` file must be valid JSON and looks something like this:

```json
{
  "tag-pair": true,
}
```

#### options.reporter
Type: `Function`
Default value: `default reporter`

Specify a custom reporter for error messages

```json
{
  "reporter": function(message){
    gutil.log(message.line,message.col,message.message,message.evidence);
  },
}
```

#### options.force
Type: `Boolean`
Default value: `false`

Report HTMLHint errors but dont fail the task


## License

[MIT License](bezoerb.mit-license.org)

[npm-url]: https://npmjs.org/package/gulp-htmlhint
[npm-image]: https://badge.fury.io/js/gulp-htmlhint.png

[travis-url]: http://travis-ci.org/bezoerb/gulp-htmlhint
[travis-image]: https://secure.travis-ci.org/bezoerb/gulp-htmlhint.png?branch=master

[depstat-url]: https://david-dm.org/bezoerb/gulp-htmlhint
[depstat-image]: https://david-dm.org/bezoerb/gulp-htmlhint.png