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
    padding: 75px 50px;
    gap: 50px;
    background-color: var(--colorBrandSofter);

    .content {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      text-align: center;
      width: 100%;

      .text {
        position: absolute;
        top: 0;
        bottom: 0;
        right: 0;
        left: 0;
        margin: auto;

        display: flex;
        flex-direction: column;
        justify-content: center;
        gap: 25px;

        max-width: 775px;
        width: 100%;

        .title {
          padding: 0;
        }

        @include notDesktop {
          p {
            font-size: 15px;
          }
        }
      }

      .circle {
        height: 350px;
        width: 350px;
        border-radius: 100%;

        background-color: #ffbb00;
      }
    }

    .arrow {
      position: absolute;
      height: 40px;
      bottom: -20px;
    }
  }
</style>

<section class="cercle-content" {id}>
  <div class="content">
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

  <a href="#Demana Cita">
    <Button type="secondary">
      <span>DEMANA CITA</span>
    </Button>
  </a>
  <img class="arrow" src="/assets/arrow.svg" alt="arrrow" />
</section>
