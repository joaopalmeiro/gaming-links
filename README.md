# gaming-links

My gaming profiles across different platforms.

## References

- [Svelte Tutorial for Beginners #1 - Introduction](https://youtu.be/zojEMeQGGHs).
- [Svelte Tutorial for Beginners #2 - Setting up a Svelte App](https://youtu.be/lnpdn2rE2N8).
- [Svelte Tutorial for Beginners #3 - Svelte Basics](https://youtu.be/TanFofZBvNI).
- [Svelte Tutorial for Beginners #4 - User Input & Data Binding](https://youtu.be/n8Kk7uvsx9A).

## Notes

- Svelte = compiler (not a framework) + reactivity.
- Svelte compiles the code for production at build time into a (single) JavaScript bundle. So, no extra scripts/libraries are shipped to production. The Svelte library is not deployed as in React and Vue.
- `App.svelte`: root component.
- Data binding:
  - The `bind:property` directive is a two-way data binding under the hood. So, `<input type="text" bind:value={colorVariable}>` is similar to `<input type="text" on:input={handleInputFunction} value={colorVariable}>`. In practice, the input element changes the variable and the changes will be reflected on the page. If the variable is changed elsewhere (via a button, for example), the value will also be updated in the input element.
