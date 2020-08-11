# :zap: Backbone Employee Project

* Tutorial project using the [Backbone.js library](https://backbonejs.org/#) together with [jQuery](https://code.jquery.com/).

*** Note: to open web links in a new window use: _ctrl+click on link_**

## :page_facing_up: Table of contents

* [:zap: Backbone Employee Project](#zap-backbone-employee-project)
	* [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
	* [:books: General info](#books-general-info)
	* [:camera: Screenshots](#camera-screenshots)
	* [:signal_strength: Technologies](#signal_strength-technologies)
	* [:floppy_disk: Setup](#floppy_disk-setup)
	* [:computer: Code Examples](#computer-code-examples)
	* [:cool: Features](#cool-features)
	* [:clipboard: Status & To-Do List](#clipboard-status--to-do-list)
	* [:clap: Inspiration](#clap-inspiration)
	* [:envelope: Contact](#envelope-contact)

## :books: General info

* Backbone.js gives structure to web applications by providing models with key-value binding and custom events, collections with a rich API of enumerable functions, views with declarative event handling, and connects it all to your existing API over a RESTful JSON interface.
* BackboneJS architecture contains the following modules −

1. HTTP Request
2. Router
3. View
4. Events
5. Model
6. Collection
7. Data Source

* Some apps are too small to need building with an SPA framework such as Angular. The simplicity and interactivity of a jQuery-based application can be combined with the well-structured building blocks from Backbone.js to create interactive pages with code organization and structure.

## :camera: Screenshots

![Example screenshot](./img/employeeList.png)
![Example screenshot](./img/employeeCreate.png)

## :signal_strength: Technologies

* [Backbone.js library v1.4.0 from CDN](https://backbonejs.org/#)
* [Bootstrap v3.4.0 from CDN](https://getbootstrap.com/)
* [jQuery v3.4.1 from CDN](https://code.jquery.com/)

## :floppy_disk: Setup

* runs from index.html in browser.

## :computer: Code Examples

```javascript
EmployeeManager.Views.Employee = Backbone.View.extend(
	{
		tagName: 'li',
		className: 'media col-md-6 col-lg-4',
		template: _.template($('#tpl-contact').html()),

		events: {
			'click .delete-employee': 'onClickDelete'
		},

		initialize: function() {
			this.listenTo(this.model, 'remove', this.remove);
		},

		render: function() {
			var html = this.template(this.model.toJSON());
			this.$el.append(html);
			return this;
		},

		onClickDelete: function(e) {
			e.preventDefault();
			this.model.collection.remove(this.model);
		}
	}
);

```

## :cool: Features

* employees can be added and deleted. Code exists to add svg-13 avatars but I couldn't find a free source.

## :clipboard: Status & To-Do List

* Status: simple working backbone.js app.
* To-Do: add functionality. Find free source of avatars.

## :clap: Inspiration

* [BackboneJS - Quick Guide](https://www.tutorialspoint.com/backbonejs/backbonejs_quick_guide.htm)
* [Auth0: BackboneJS: Getting Started](https://auth0.com/blog/backbonejs-getting-started/#Understanding-Key-Concepts-in-BackboneJS)

## :envelope: Contact

* Repo created by [ABateman](https://www.andrewbateman.org) - you are welcome to [send me a message](https://andrewbateman.org/contact)
