<script>

  import {clean, clsx ,forwardEventsBuilder} from './utils';
  import {current_component} from 'svelte/internal';
  const forwardEvents = forwardEventsBuilder(current_component);
let className = '';
  export {className as class};
  export let next = false;
  export let previous = false;
  export let first = false;
  export let last = false;
  export let ariaLabel = '';
  export let href = '';

  const props = clean($$props);

  $: classes = clsx(className, 'page-link');

  let defaultAriaLabel;

  $: if (previous) {
    defaultAriaLabel = 'Previous';
  } else if (next) {
    defaultAriaLabel = 'Next';
  } else if (first) {
    defaultAriaLabel = 'First';
  } else if (last) {
    defaultAriaLabel = 'Last';
  }

  $: realLabel = ariaLabel || defaultAriaLabel;

  let defaultCaret;
  $: if (previous) {
    defaultCaret = '\u2039';
  } else if (next) {
    defaultCaret = '\u203A';
  } else if (first) {
    defaultCaret = '\u00ab';
  } else if (last) {
    defaultCaret = '\u00bb';
  }
</script>

<a use:forwardEvents {...props} class={classes} {href}>
  {#if previous || next || first || last}
    <span aria-hidden="true">
      <slot> {defaultCaret} </slot>
    </span>
    <span class="sr-only"> {realLabel} </span>
  {:else}
    <slot/>
  {/if}
</a>
