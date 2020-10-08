# Generate page component

The React SPA generator is used by the [Labs CLI](https://docs.labs.lambdaschool.com/guides/labs-cli/labs-cli-basics) to generate greenfield SPA applications or add components.

## Overview

We will use the Labs CLI to generate a new [Page Component](https://www.npmjs.com/package/@lambdalabs/generator-spa#page) in our Labs SPA app. The generator will create a new folder in the `components/pages` directory and the following files:

* Container.js
* RenderPage.js
* index.js

## Run the generator

We will use the following information as arguments and options to the generator:

* `Pets` will be the page name
* `useOkta` - we want this to be a secured page \(and route\)

```text
> labs @lambdalabs/spa:page pets --useOkta
```

You can now find the new page folder:

```text
src
  ├ components
  │  ├ pages
  │  │  ├ Pets
  │  │  │  ├ PetsContainer.js
  │  │  │  ├ RenderPetsPage.js
  │  │  │  ├ index.js
```

Adding the following route to the main index.js will make the page available.

```javascript
<SecureRoute path="/example-list" component={ExampleListPage} />
```

