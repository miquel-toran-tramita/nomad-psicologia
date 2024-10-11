<script lang="ts">
  import Button from './details/Button.svelte'
  import Svg from './details/Svg.svelte'
</script>

<style lang="scss">
  @import '/src/sass/mixins.scss';

  .cercle-content {
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

        @include notDesktop {
          h1 {
            font-size: 25px;
          }

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
  }
</style>

<div class="cercle-content">
  <div class="content">
    <div class="text">
      <h1>A NOMAD PSICOLOGIA creiem en una psicologia més enllà dels límits tradicionals.</h1>
      <p>
        Som un equip de professionals apassionat, amb més de 15 anys d’experiència i un profund arrelament al nostre territori, compromesos
        a oferir un servei de màxima competència, adaptat a les realitats canviants de les persones.
      </p>
      <p>
        Ens mou la visió d’una psicologia oberta, propera i lluminosa, on la confidencialitat i la seguretat del pacient conviuen amb la
        possibilitat de connectar amb el món exterior.
      </p>
    </div>
    <div class="circle" />
  </div>
  <Button type="secondary">
    <span>DEMANA CITA</span>
  </Button>
  <!--<Svg name="arrow2"/>-->
</div>
