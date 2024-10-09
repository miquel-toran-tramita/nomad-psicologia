<script lang="ts">
  export let disabled: boolean = false
  export let type: 'main' | 'secondary' | 'subButton' = 'main'
  export let width: string = ''
  export let customClass: string = ''
  export let click = () => {}
</script>

<style lang="scss">
  .btn-main,
  .btn-secondary {
    height: fit-content;
    width: fit-content;
    padding: 10px 15px;
    border-radius: 5px;
    transition: 0.3s ease;
  }

  .btn-main {
    background-color: var(--colorBrand);
    border: 1px solid var(--colorBrand);

    :global(span) {
      color: var(--colorBase);
    }

    &:not([disabled]):hover {
      transition: 0.3s ease;
      background-color: var(--colorBase);

      :global(span) {
        color: var(--colorBrand);
      }
    }

    &[disabled] {
      opacity: 0.3;
      border: 1px solid var(--colorText2);
      background-color: var(--colorBase);

      cursor: default;

      :global(span) {
        color: var(--colorText2);
      }
    }
  }

  .btn-secondary {
    border: 2px solid var(--colorBrand);

    :global(span) {
      color: var(--colorBrand);
      font-weight: bold;
      transition: 0.3s ease;
    }

    &:not([disabled]):hover {
      transition: 0.3s ease;
      background-color: var(--colorBrand);

      :global(span) {
        color: white;
        transition: 0.3s ease;
      }
    }

    &[disabled] {
      opacity: 0.3;
      border: 1px solid var(--colorText2);
      cursor: default;

      :global(span) {
        color: var(--colorText2);
      }
    }
  }
</style>

<button class="btn-{type} {customClass}" style={width ? `width: ${width}` : ''} on:click={click} {disabled}>
  <slot />
</button>
