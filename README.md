# gaming-links

My gaming profiles across different platforms.

## References

> [The Net Ninja](https://www.youtube.com/c/TheNetNinja) (Shaun Pelling)

- [Svelte Tutorial for Beginners #1 - Introduction](https://youtu.be/zojEMeQGGHs).
- [Svelte Tutorial for Beginners #2 - Setting up a Svelte App](https://youtu.be/lnpdn2rE2N8).
- [Svelte Tutorial for Beginners #3 - Svelte Basics](https://youtu.be/TanFofZBvNI).
- [Svelte Tutorial for Beginners #4 - User Input & Data Binding](https://youtu.be/n8Kk7uvsx9A).
- [Svelte Tutorial for Beginners #5 - Reactive Values](https://youtu.be/QJJjXRIg7kI).
- [Svelte Tutorial for Beginners #6 - Loops](https://youtu.be/sGmSSULKJwE).
- [Svelte Tutorial for Beginners #7 - Inline Event Handlers](https://youtu.be/VWOpVxIkZJs).
- [Svelte Tutorial for Beginners #8 - Conditionals](https://youtu.be/9PfCZFqYsYA).
- [Svelte Tutorial for Beginners #9 - Components](https://youtu.be/rkwKpULfWZA).
- [Svelte Tutorial for Beginners #10 - CSS & Conditional Styles](https://youtu.be/AAPu__4qSlY).
- [Svelte Tutorial for Beginners #11 - Props](https://youtu.be/Y1McRGLkxQc).
- [Svelte Tutorial for Beginners #12 - Event Forwarding](https://youtu.be/SaMils0yx7s).
- [Svelte Tutorial for Beginners #13 - Event Modifiers](https://youtu.be/RrNC2hizXXI).
- [Svelte Tutorial for Beginners #14 - Slots](https://youtu.be/WUXalRPfP1A).
- [Svelte Tutorial for Beginners #15 - Forms (part 1)](https://youtu.be/FB_am3ZPY7I).
- [Svelte Tutorial for Beginners #16 - forms (part 2)](https://youtu.be/tkBgoKpU6Tk).
- [Svelte Tutorial for Beginners #17 - Dispatching Custom Events](https://youtu.be/yCkYm4zze8I).

## Notes

> Svelte

- Svelte = compiler (not a framework) + reactivity + components.
- Svelte compiles the code for production at build time into a (single) JavaScript bundle. So, no extra scripts/libraries are shipped to production. The Svelte library is not deployed as in React and Vue.
- `App.svelte`: root component.
- Handler functions can take the `event` object.
- Data binding:
  - The [`bind:property` directive](https://svelte.dev/docs#bind_element_property) is a two-way data binding under the hood. So, `<input type="text" bind:value={colorVariable}>` is similar to `<input type="text" on:input={handleInputFunction} value={colorVariable}>`. In practice, the input element changes the variable and the changes will be reflected on the page. If the variable is changed elsewhere (via a button, for example), the value will also be updated in the input element.
- `$: console.log(colorVariable);` is an example of a reactive statement. Use `$: {...}` for a code block.
- `{#each array as arrayElement (arrayElement.key)}...{/each}` (`key` is important if you need to manipulate the data). This block can also have an `{:else}` clause, which is rendered if `array` is empty.
- `<button on:click={() => handleClick(object.id)}>Delete</button>` or `<button on:click={(event) => handleClick(event, object.id)}>Delete</button>` (inline event handler). This is useful for deleting an element from an array by its identifier within an each block (assuming there is a button for each element), for example. In other words, this is useful if the handler function needs to take arguments in addition to `event`.
- Event forwarding:
  - If the `on:` directive (e.g., `on:click`) is used without a value, the component will _forward_ the event. In this way, a consumer (parent component) of the component (child component) can listen for it. In other words, you can define a handler function in `App.svelte`, assuming the component is used here, as there is another element, such as a button, that is used to show/hide this component. Example:
    - `App.svelte` file: `<Modal ... on:click={toggleModal} />` and `<button on:click={toggleModal}>...</button>`.
    - `Modal.svelte` file: `<div ... on:click>...</div>`.
  - The `self` event modifier (e.g., `on:click|self`) is useful for a modal since the handler is only triggered if `event.target` is the element itself. In practice, this allows the modal to be closed only if there is a click outside the message container (a child `<div>`), on the part that is faded, for example.
- In Svelte, when we bind to a number input (e.g., `<input type="number" bind:value={numVariable}>`), the [input value is coerced](https://svelte.dev/docs#bind_element_property). In this way, the associated variable is a number, not a string.
- `let arrayVariable = [];` + `bind:group={arrayVariable}` for radio and checkbox inputs ([example](https://svelte.dev/docs#bind_group)).
- Dispatching custom events:
  - Event forwarding is for events, not data (use [`createEventDispatcher`](https://svelte.dev/docs#createEventDispatcher) instead).
  - Events dispatched (custom event + data) from child components can be listened to in their parent (e.g., `<ChildComponent on:name={handlerFunction} />`). The data is available on the `detail` property of the event object.

> CSS

- `crimson` instead of `red` ([color keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value)).

> Misc

- [Craft](https://www.craft.do/):
  - Document/Markdown editor.
  - [How to set (and delete) custom icon on Mac](https://www.craft.do/s/dhXngIMJLQu96b).
