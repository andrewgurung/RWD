## Approaching a Responsive Web Design

- Get designs in the browser as soon as possible
  - http://styletil.es
  - Style Tiles are a design deliverable consisting of fonts, colors and interface elements that communicate the essence of a visual brand for the web.

- Letting the design dictate the breakpoints
  - Always start with the smalest screen sizes upward
  - Write the CSS for the smallest viewport first and then add any changes to different elements within media queries afterwards.
  ```CSS
  .rule {
    /* Smallest viewport size styles */
  }
  @media (min-width: 40rem) {
    .rule {
    /* Medium viewport size changes */
    }
  }

  @media (min-width: 50rem) {
    .rule {
    /* Larger viewport size changes */
    }
  }
  ```
- Use tools such as BrowserSync to synchronize your work
  - http://browsersync.io/

- Embracing progressive enhancement
  - Begin all front-end code with lowest common denominator
  - Then progressively enhance code for more capable devices and browsers
  - Concentrate on using elements such as main, header, footer, article, section and aside correctly

- Defining a browser support matrix
  - Functional parity, not aesthetic parity
  - Choosing the browsers to support
    - Use Google Analytics to look at visitor statistics

- Linking CSS breakpoints to JavaScript
- Avoiding CSS frameworks in production
- Developing pragmatic solutions
- Writing the simplest possible code
- Hiding, showing, and loading content across viewports
- Letting CSS do the (visual) heavy lifting
- Using validators and linting tools
- Analyzing and testing web page performance (webpagetest.org)
- Embracing faster and more effective techniques
- Keeping an eye out for the next 'big' things
