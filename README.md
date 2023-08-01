# BeelineJS

BeelineJS is a bootstrap, mini framework to get you started on developing single page application.
The app is compiled by webpack and a prebuild node script generating components, templates and layouts.

## Centrelized events
Events are created at the document level and auto dispatched to all the components.
You can write a complete application without the need to `addEventListener`.

## Key bindings
The binding is done by a string model key, the core will find and notify all the linked view/components if a changed was made to their model.

## Pre-compiled templates, components and layouts
### Templates
Templates are html files that are compiled into `html.js`.
You can use one or more templates in a component using `require`

### Components
Components contains 3 main functions:
- `create`: returns the template to be loaded as element to the page
- `init`: called after the element was added to the page.
can be used to set user, document or/and window events.

### Layouts
Layouts are static html templates used to position elements on the page

### Great stucture
The stucture is flexible and well formated.
- build: run before the app is built.
- app: contains the core and the first load
- components: factory generated components.
- layouts: factory generated layouts.
- style: style generated from layouts and components into a single file.

## data load
All pages and page refresh are loaded via the `OnLoad` function.
A load action can contain one or all of the following:
- Models
- Layouts
- Views
- ViewData
- Events

Once a `model` is loaded all the `mKey` bounded views will be updated.
Once a `viewData` is loaded all the `dKey` bounded views will be updated.
Layouts will be added followed by views.
Events will be dispatched to the views linked by `mKey`.

After each load the core will clear and the `views`, `models` and `layouts` not in use.
