<script lang="ts">
  import Button from './details/Button.svelte'
  import Svg from './details/Svg.svelte'
  export let id
</script>

<style lang="scss">
  @import '/src/sass/mixins.scss';

  .cercle-content {
    position: relative;
    display: flex;
    align-items: center;
    flex-direction: column;
    gap: 50px;
    background-color: var(--colorBrandSofter);
    padding: 50px 0;

    .content {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      text-align: center;
      width: 100%;
      max-width: 700px;

      padding-top: 50px;
      padding-bottom: 50px;

      @include notDesktop {
        padding-top: 0;
        padding-bottom: 0;
      }

      .text {
        top: 0;
        bottom: 0;
        right: 0;
        left: 0;
        margin: auto;

        display: flex;
        flex-direction: column;
        justify-content: center;
        gap: 25px;
        z-index: 1;

        max-width: 775px;
        width: 100%;

        .title {
          padding: 0;
        }

        p {
          font-size: 17px;

          @include notDesktop {
            font-size: 15px;
          }
        }
      }

      .circle {
        position: absolute;
        height: 100%;
        max-height: 350px;
        aspect-ratio: 1 / 1;
        border-radius: 100%;
        top: 0;
        bottom: 0;
        margin: auto;
        z-index: 0;

        background-color: #ffbb00;
      }
    }

    a {
      z-index: 2;
    }

    .arrow {
      position: absolute;
      height: 40px;
      bottom: -20px;
      z-index: 2;
    }
  }
</style>

<section class="cercle-content" {id}>
  <div class="content g-wrapper">
    <div class="text">
      <h2 class="g-title title">A NOMAD PSICOLOGIA creiem en una psicologia més enllà dels límits tradicionals.</h2>
      <p>
        Som un equip de professionals apassionat, amb més de 15 anys d’experiència i un profund arrelament al nostre territori, compromesos
        a oferir un servei de màxima competència, adaptat a les realitats canviants de les persones.
      </p>
      <p>
        <span style="font-weight: bolder;">Ens mou la visió d’una psicologia oberta, propera i lluminosa,</span> on la confidencialitat i la
        seguretat del pacient conviuen amb la possibilitat de connectar amb el món exterior.
      </p>
    </div>
    <div class="circle" />
  </div>

  <a href="#DemanaCita">
    <Button type="secondary">
      <span>DEMANA CITA</span>
    </Button>
  </a>
  <img class="arrow" src="/assets/arrow.svg" alt="arrrow" />
</section>
