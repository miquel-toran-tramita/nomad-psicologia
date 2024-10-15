<script lang="ts">
  import Svg from './Svg.svelte'

  export let photo: string
  export let more: string

  let flipped: boolean = false
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .card {
    position: relative;
    padding: 20px;
    width: 100%;

    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 25px;
    text-align: center;

    border-radius: 8px;
    overflow: hidden;

    :global(.plus) {
      position: absolute;
      top: 15px;
      left: 15px;
    }

    .photo {
      height: 200px;
      width: 200px;
      border-radius: 100%;
      object-fit: cover;
      background-color: var(--colorBrandSofter);
    }

    .back {
      position: absolute;
      height: 100%;
      width: 100%;
      background-color: rgba(43, 54, 41, 0.8);
      top: 0;
      backdrop-filter: blur(5px);

      display: flex;
      flex-direction: column;
      gap: 10px;

      padding: 15px;
      font-size: 13px;
      text-align: start;
      font-weight: lighter;
      color: white;

      opacity: 0;
      transition: 0.3s ease;
    }

    @include desktop {
      &:hover {
        .back {
          transition: 0.3s ease;
          opacity: 1;
        }
      }
    }

    @include notDesktop {
      .flipped {
        opacity: 1;
      }
    }
  }
</style>

<button class="card" on:click={() => (flipped = !flipped)}>
  <Svg name="plus" height="18" width="18" className="plus" />

  <img class="photo" src="/assets/equip/{photo}.JPG" alt="foto" />

  <slot />

  <div class="back" class:flipped>
    <Svg name="minus" height="18" width="18" fill="white" />
    {@html more}
  </div>
</button>
