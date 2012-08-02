# hoganyam
Yet another hogan.js(moustache templates) middleware. Can render templates with partials serverside or precompile them for use on the client. In debug mode the templates are recompiled every time, otherwise cached.

## Usage
``` js
    var hoganyam = require('hoganyam');
```

### As connect-style middleware

Makes the templates available individually.
``` js
    app.use(hoganyam.provide(templatesDir, options));
```

Makes the templates avaible packed into one js file.
``` js
    app.use(hoganyam.providePacked(templatesDir), options));
```

### Serverside rendering

``` js
    hoganyam.render(file, context, options, function(err, str) {
        // do something with the rendered template string
    });
```

**Use as broadway plugin for flatiron**
``` js
    app.use(hoganyam.plugin, {dir: templatesDir, ext: '.html'});
    // now you can render directly to the response
    app.render(res, 'templatename', { title: 'Hello Hogan'});
```

**For options see source**

## License
MIT License

## Install with npm
    npm install hoganyam

## Run tests
    npm test