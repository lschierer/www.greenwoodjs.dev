---
title: Lit
layout: guides
order: 1
tocHeading: 2
---

# Lit

[**Lit**](https://lit.dev/) builds on top of the Web Components standards, adding additional developer experience ergonomics like reactivity, declarative templates and reducing boilerplate. Lit also has support for SSR (server-side rendering), which Greenwood supports through a plugin.

> You can see a complete hybrid project example in this [demonstration repo](https://github.com/thescientist13/greenwood-lit-ssr) as well as [demos](https://github.com/thescientist13/greenwood-lit-ssr/pulls?q=is%3Apr+is%3Aopen+label%3Ademo) of using Lit based component libraries like [**Shoelace**](https://shoelace.style/) and [**Spectrum Web Components**](https://opensource.adobe.com/spectrum-web-components/) with Greenwood.

## Installation

As with most libraries, just install **lit** with your favorite package manager as a dependency.

<!-- prettier-ignore-start -->
<app-ctc-block variant="runners">

  ```shell
  npm i lit
  ```

  ```shell
  yarn add lit
  ```

  ```shell
  pnpm add lit
  ```

</app-ctc-block>

<!-- prettier-ignore-end -->

Now you can start writing Lit based Web Components!

<!-- prettier-ignore-start -->
<app-ctc-block variant="snippet" heading="src/components/greeting.js">

  ```js
  import { html, css, LitElement } from "lit";

  export class SimpleGreeting extends LitElement {
    static styles = css`
      p {
        color: blue;
      }
    `;

    static properties = {
      name: { type: String },
    };

    constructor() {
      super();
      this.name = "Somebody";
    }

    render() {
      return html`<p>Hello, ${this.name}!</p>`;
    }
  }
  ```

</app-ctc-block>

<!-- prettier-ignore-end -->

That's it!

## SSR

To enable [Lit and SSR](https://lit.dev/docs/ssr/overview/) you can install our Greenwood [plugin](https://github.com/ProjectEvergreen/greenwood/tree/master/packages/plugin-renderer-lit) and add it to your _greenwood.config.js_.

```js
import { greenwoodPluginRendererLit } from "@greenwood/plugin-renderer-lit";

export default {
  plugins: [greenwoodPluginRendererLit()],
};
```

> Please see the [README](https://github.com/ProjectEvergreen/greenwood/blob/master/packages/plugin-renderer-lit/README.md) to learn more about full usage details and caveats.
