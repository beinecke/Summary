## 新建Slide

Seminar/slides文件夹中新建{name}.html,按照格式书写内容，修改Seminar/app/main.js,

```javascript
function (require, Model, View, Controller, compose, fetch, markdown, highlight, split) {
		var source, model, view, controller, splitSlides;

		splitSlides = /\s*\<hr\s*\/?\>\s*/i;
		source = compose(fetch(require), split(splitSlides));

		model = new Model(source('slides/{name}.html'));
		view = new View(document.getElementById('slide-container'), model);
		controller = new Controller(view);

		controller.start().then(function () {
			document.body.className = '';
		});
	}
````
