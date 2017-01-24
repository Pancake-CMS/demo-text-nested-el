# demo-text-nested-el

A demo user component for the Pancake project. What it does is, it provides a demo component definition for nested user components. Where a user can drag and drop more user components.

## Installation

```shell
bower install --save pancake-cms-demo-text-nested-el
```

## Note

#### Inline Components

If you are planning to add support for nested components, which can be dragged and dropped into your user components by other users, then you will need to add this behavior to your element.

```javascript
behaviors: [
    NestedIncluderBehavior
]
```

#### Translated Content

If you are planning to add support for translated content, you can add it by adding these two things in your element

1. Add this behavior

```javascript
behaviors: [
    ContentEditorBehavior
]
```

This is responsible for showing the editors for your element.

2. Adding the `usercontent` properties

```javascript
    usercontent: {
        type: Object,
        notify: true,
        reflectToAttribute: false
    }
```

This is responsible for sending data from parent element to `ContentEditorBehavior` behavior.

3. Adding the content nodes to your element

If a div is supposed to be a content div, i.e. if it is supposed to contain translated text, it need to have an `is-content` attribute whose value can be `inline`, `inline-more` or `wsywig`. All these values correspont to different types of editors. It will also need a `content-id` attribute. Its value can be any String as long as it is not repeated twice.

```html
<h4 is-content="inline" content-id="heading">Some Random Demo Heading</h4>
```

#### Template Properties

A user component can have different types of attributes added to it in a template. Say for example, one template might need alignment of text to be center, while the other might need it to me left aligned. This is where a user creating the template gets to choose the attribute value in `property-editor` dialog box.

The `properties.json` file has an example of a dropdown property that can be editted and then used in templates and pages. If you would like to read more about the types of properties supported, you can reffer [this link](https://github.com/Pancake-CMS/property-editor).