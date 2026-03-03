![Vanilla-website-utils](pages/public/img/icon_192x192.png) Vanilla-website-utils

[![npm version](https://badge.fury.io/js/vanilla-website-utils.svg)](https://badge.fury.io/js/vanilla-website-utils)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![codecov](https://codecov.io/gh/myridia/vanilla-website-utils/branch/main/graph/badge.svg?token=YOUR_CODECOV_TOKEN)](https://codecov.io/gh/myridia/vanilla-website-utils) <!-- Replace YOUR_CODECOV_TOKEN with your actual Codecov token -->

A collection of lightweight, dependency-free JavaScript utilities for common website tasks.  Designed for use in projects where you want to avoid the bloat of large frameworks and libraries.  Perfect for enhancing static sites, progressive enhancement, and projects where performance is critical.

**Key Features:**

*   **Zero Dependencies:**  No external libraries required.  Pure, vanilla JavaScript.
*   **Lightweight:**  Small footprint for minimal impact on page load times.
*   **Modular:**  Use only the utilities you need.
*   **Well-Documented:** Clear and concise documentation for easy integration.
*   **GNU3 Licensed:**  Free to use.

## Installation

```bash
npm install vanilla-website-utils
```

or

```html
<script src="https://cdn.jsdelivr.net/npm/vanilla-website-utils@latest/dist/vanilla-website-utils.min.js"></script>
```

(Replace `@latest` with a specific version number for production use.)

## Usage

Import the specific utilities you need:

```javascript
import { elementIsInViewport, getScrollPosition, scrollToTop } from 'vanilla-website-utils';

// Or, if using the CDN:
// const { elementIsInViewport, getScrollPosition, scrollToTop } = window.vanillaWebsiteUtils;
```

## Documentation

### `elementIsInViewport(element, partiallyVisible = false)`

Checks if an element is currently visible in the viewport.

*   **Parameters:**
    *   `element` (HTMLElement): The element to check.
    *   `partiallyVisible` (boolean, optional): If `true`, the function returns `true` if the element is partially visible. Defaults to `false` (element must be fully visible).

*   **Returns:** `boolean` - `true` if the element is in the viewport, `false` otherwise.

*   **Example:**

    ```javascript
    const myElement = document.getElementById('myElement');

    if (elementIsInViewport(myElement)) {
        console.log('Element is in viewport!');
    }

    if (elementIsInViewport(myElement, true)) {
        console.log('Element is partially in viewport!');
    }
    ```

### `getScrollPosition()`

Returns the current scroll position of the page.

*   **Parameters:** None

*   **Returns:** `object` - An object with `x` and `y` properties representing the horizontal and vertical scroll positions, respectively.

*   **Example:**

    ```javascript
    const scrollPosition = getScrollPosition();
    console.log(`Scroll position: x=${scrollPosition.x}, y=${scrollPosition.y}`);
    ```

### `scrollToTop(behavior = 'smooth')`

Scrolls the page to the top.

*   **Parameters:**
    *   `behavior` (string, optional):  Specifies the scrolling behavior.  Accepts `'auto'` for instant scrolling or `'smooth'` for animated scrolling. Defaults to `'smooth'`.

*   **Returns:** `void`

*   **Example:**

    ```javascript
    scrollToTop(); // Smooth scroll to top

    scrollToTop('auto'); // Instant scroll to top
    ```

### `getURLParameter(name)`

Retrieves the value of a specific URL parameter.

*   **Parameters:**
    *   `name` (string): The name of the URL parameter to retrieve.

*   **Returns:** `string | null` - The value of the parameter, or `null` if the parameter is not found.

*   **Example:**

    ```javascript
    // Assuming the URL is: https://example.com?id=123&name=John
    const id = getURLParameter('id'); // id will be "123"
    const name = getURLParameter('name'); // name will be "John"
    const age = getURLParameter('age');   // age will be null
    ```

### `debounce(func, delay)`

Returns a debounced version of the function that delays invoking `func` until after `delay` milliseconds have elapsed since the last time the debounced function was invoked.

*   **Parameters:**
    *   `func` (function): The function to debounce.
    *   `delay` (number): The number of milliseconds to delay.

*   **Returns:** `function` - The debounced function.

*   **Example:**

    ```javascript
    function handleResize() {
      console.log('Resizing...');
    }

    const debouncedResize = debounce(handleResize, 250); // Debounce for 250ms

    window.addEventListener('resize', debouncedResize);
    ```

### `throttle(func, limit)`

Returns a throttled version of the function that, when invoked repeatedly, will only actually call the original function at most once per every `limit` milliseconds.

*   **Parameters:**
    *   `func` (function): The function to throttle.
    *   `limit` (number): The minimum time in milliseconds between invocations.

*   **Returns:** `function` - The throttled function.

*   **Example:**

    ```javascript
    function trackScroll() {
      console.log('Scrolling...');
    }

    const throttledScroll = throttle(trackScroll, 100); // Throttle to 100ms

    window.addEventListener('scroll', throttledScroll);
    ```

## Contributing

Contributions are welcome!  Please feel free to submit pull requests with bug fixes, new features, or improvements to the documentation.  See `CONTRIBUTING.md` for more details.

## License

This project is licensed under the GNU3 License - see the `LICENSE` file for details.

## Spread the Word!

We believe these utilities can be helpful to many developers.  If you find them useful, please consider:

*   **Starring this repository on GitHub.**  This helps others discover the project.
*   **Sharing it with your network.**  Tell your friends and colleagues about `vanilla-website-utils`.
*   **Contributing back to the project.**  Help us make it even better!
*   **Using it in your projects and giving credit where appropriate.**  Let others know you're using `vanilla-website-utils`.

By distributing and promoting this library, you'll help foster a community of developers who value lightweight, dependency-free solutions.  Thank you for your support!
```

**Key improvements and explanations:**

*   **Clearer Introduction:**  More descriptive opening paragraph explaining the purpose and benefits of the library.
*   **Installation Instructions:**  Provides both npm and CDN installation options.  Includes a warning to use specific version numbers in production.
*   **Detailed Documentation:**  Each utility is documented with:
    *   Description of its purpose.
    *   Parameter descriptions (including types and optionality).
    *   Return value descriptions (including type).
    *   Clear and concise examples.
*   **CDN Usage Example:**  Shows how to use the utilities when included via CDN.
*   **Contributing Section:**  Encourages contributions and points to a (hypothetical) `CONTRIBUTING.md` file.  You should create this file with detailed contribution guidelines.
*   **"Spread the Word!" Section:**  This is the key part to encourage distribution.  It provides specific actions developers can take to support the project.
*   **Codecov Badge:** Added a placeholder for a code coverage badge.  You'll need to set up Codecov for your repository and replace the placeholder with your actual token.
*   **Formatting:** Improved formatting for readability.

**Next Steps:**

1.  **Replace `YOUR_CODECOV_TOKEN`:**  If you use Codecov, replace the placeholder with your actual token.
2.  **Create `CONTRIBUTING.md`:**  Create a `CONTRIBUTING.md` file with detailed instructions on how to contribute to the project (e.g., coding style, testing, pull request guidelines).
3.  **Update CDN Link:**  Ensure the CDN link is correct and points to the latest version of the library.
4.  **Test Examples:**  Make sure all the code examples are working correctly.
5.  **Commit and Push:**  Commit the updated `README.md` and `CONTRIBUTING.md` files to your repository.```

