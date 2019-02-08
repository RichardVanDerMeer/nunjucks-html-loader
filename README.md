Nunjucks (Webpack) HTML Loader
==============================
The original 'nunjucks-loader' takes nunjucks templates and turns them into javascript. I wanted to take nunjucks templates and turn them into pre-compiled static html files.
This fork also adds an option to make adjustments to the environment.

[![NPM version][npm-image]][npm-url]
[![Github license][github-license-image]][github-url]
[![Github stars][github-image]][github-url]

Usage
-----

This is a very simple webpack loader for nunjucks files. It performs the following opteration:

    some-template.nunj -> html string

When you mix it with the file-loader you can take it one step further!

    some-template.nunj -> html string -> some-file.html

Add your personal variation to the below loader configuration to your webpack config and you should be good to go.

	{
		test: /njk|nunjucks/,
		use: [
			{
				loader: 'nunjucks-html-loader',
				query: {
					environment: function(env) {
						env.addGlobal('base', '/path/to/base')
						return env
					},
					context: 'src',
					name: '[path][name].html'
				}

			},

		]

	}


[npm-url]: https://www.npmjs.com/package/nunjucks-html-loader
[npm-image]: https://img.shields.io/npm/v/nunjucks-html-loader.svg
[github-url]: https://github.com/ryanhornberger/nunjucks-html-loader
[github-image]: https://img.shields.io/github/stars/ryanhornberger/nunjucks-html-loader.svg?style=social&label=Star
[github-license-image]: https://img.shields.io/github/license/ryanhornberger/nunjucks-html-loader.svg
