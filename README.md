## `use-element-dimensions`

React Hook to figure out DOM Element dimensions with updates

### Usage

```jsx
import useDimensions from "use-element-dimensions";

const Example = () => {
  const [{ width, height }, ref] = useDimensions();
  return (
    <div ref={ref}>
      The width of this div is: {width} and the height is: {height}
    </div>
  );
};
```

### Use case

There are already some hook libraries that provide dimensions on first render or even update them on `window` resize event, however in many cases this may not be sufficient. HTML DOM Elements can resize in response to a lot of things we don't expect, only one of which is screen size, for example:

- When animating any of the size properties.
- Setting a size properties on an encapsulating DOM Node.
- Orientation change (`resize` triggers in this case - or it should).

This package uses [`@juggle/resize-observer`](https://juggle.studio/resize-observer/) to [Ponyfill](https://github.com/sindresorhus/ponyfill) `ResizeObserver` API. This means that you can expect the same behaviour out of every browser, regardless of them having implemented the actual API or not.

### Development

Everything in this package is in `src/index.ts`. If you want to run an example to develop against, install [`parcel`](https://parceljs.org/) globally and then run `parcel example/simple/index.html` from the root directory of the project.

### Building


