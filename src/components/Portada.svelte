<script lang="ts">
  import Svg from './details/Svg.svelte'
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .portada-content {
    position: relative;
    width: 100%;
    height: 75dvh;
    background-color: var(--colorBrand);
    overflow: hidden;

    .logo {
      position: absolute;
      top: 15%;
      left: 0;
      right: 0;
      margin: auto;
      height: 70%;
      opacity: 0.8;
      z-index: 2;
    }

    .linea {
      position: absolute;
      left: 0;
      right: 0;
      margin: auto;
      width: 95%;
      top: -20%;
      z-index: 0;

      @include notDesktop {
        width: 200%;
        top: 15px;
        left: -25%;
      }
    }

    .coneixens {
      position: absolute;
      bottom: 50px;
      right: 0;
      left: 0;
      margin: 0 auto;

      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 5px;

      span {
        color: white;
        font-weight: 100;
        font-size: 13px;
      }

      :global(svg) {
        transform: rotate(-90deg);
      }
    }
  }
</style>

<div class="portada-content">
  <img class="logo" src="/assets/cara_logo.svg" alt="logo" />
  <img class="linea" src="/assets/linea.svg" alt="linea" />
  <div class="coneixens">
    <span>Coneixe'ns</span>
    <Svg name="" fill="white" />
  </div>
</div>
