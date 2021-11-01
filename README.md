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

## Notes

- Svelte = compiler (not a framework) + reactivity + components.
- Svelte compiles the code for production at build time into a (single) JavaScript bundle. So, no extra scripts/libraries are shipped to production. The Svelte library is not deployed as in React and Vue.
- `App.svelte`: root component.
- Handler functions can take the `event` object.
- Data binding:
  - The [`bind:property` directive](https://svelte.dev/docs#bind_element_property) is a two-way data binding under the hood. So, `<input type="text" bind:value={colorVariable}>` is similar to `<input type="text" on:input={handleInputFunction} value={colorVariable}>`. In practice, the input element changes the variable and the changes will be reflected on the page. If the variable is changed elsewhere (via a button, for example), the value will also be updated in the input element.
- `$: console.log(colorVariable);` is an example of a reactive statement. Use `$: {...}` for a code block.
- `{#each array as arrayElement (arrayElement.key)}...{/each}` (`key` is important if you need to manipulate the data). This block can also have an `{:else}` clause, which is rendered if `array` is empty.
- `<button on:click={() => handleClick(object.id)}>Delete</button>` or `<button on:click={(event) => handleClick(event, object.id)}>Delete</button>` (inline event handler). This is useful for deleting an element from an array by its identifier within an each block (assuming there is a button for each element), for example. In other words, this is useful if the handler function needs to take arguments in addition to `event`.
