<script lang="ts">
  import Svg from '@/components/details/Svg.svelte'
  export let id
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .contact-container {
    padding: 50px 0;

    .content {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 80px;

      .form {
        .input-group {
          padding-top: 30px;
          display: flex;
          flex-direction: column;
          gap: 10px;

          input,
          textarea {
            min-height: 50px;
            border: 1px solid lightgray;
            border-radius: 5px;
          }
          &.radio {
            padding-top: 0;
            flex-direction: row;
            input {
              width: 25px;
              height: 25px;
              border: 1px solid lightgray !important;
            }

            align-items: center;
          }
        }
      }

      .info {
        width: 500px;
        padding-top: 50px;

        display: flex;
        flex-direction: column;
        gap: 25px;

        :global(path) {
          fill: #191919;
        }

        .info-text {
          max-width: 325px;
          font-size: 15px;

          span {
            font-weight: bolder;
          }
        }
      }

      @include notDesktop {
        flex-direction: column;

        .form,
        .info {
          width: 100%;
        }
      }
    }
  }
</style>

<section class="contact-container g-wrapper" {id}>
  <h2 class="g-title">Contacte</h2>
  <div class="content">
    <form class="form" action="https://api.web3forms.com/submit" method="POST">
      <!-- Replace with your Access Key -->
      <input type="hidden" name="access_key" value="8ea05408-206c-4f8d-aeca-059327af5113" />

      <!-- Form Inputs. Each input must have a name="" attribute -->
      <div class="input-group">
        <label for="">Nom</label>
        <input type="text" name="Nom" required />
      </div>

      <div class="input-group">
        <label for="">Email</label>
        <input type="text" name="Telèfon" required />
      </div>

      <div class="input-group">
        <label for="">Telèfon</label>
        <input type="email" name="Email" required />
      </div>

      <div class="input-group">
        <label for="">Deixa el teu comentario</label>
        <textarea name="Missatge" required></textarea>
      </div>

      <div class="input-group radio">
        <input type="radio" />
        <label for="">He llegit i acepto la <a href="/politica-de-privacitat">Política de privacitat</a></label>
      </div>

      <!-- Honeypot Spam Protection -->
      <input type="checkbox" name="botcheck" class="hidden" style="display: none;" />

      <!-- Custom Confirmation / Success Page -->
      <input type="hidden" name="redirect" value="/gracies" />

      <button type="submit" class="g-btn">ENVIAR</button>
    </form>

    <div class="info">
      <Svg name="logo2" width="150" height="80" />

      <div class="info-text"><span>Direcció:</span> Carrer de l'Átlantida, 21, planta 2 08230 Sant Adrià del Besòs.</div>

      <div class="socials">
        <div class="info-text"><span>Teléfon:</span> 931 418 524</div>
        <div class="info-text"><span>WhatsApp:</span> 640 293 991</div>
        <div class="info-text"><span>E-mail:</span> nomad@nomadpsicologia.com</div>
      </div>

      <div class="info-text">
        <span>Com arribar:</span>
        <p>Metro: L2 Artigues - Sant Adrià</p>
        <p>Bus: H10 B20 B21 B23 B25 M26 M30 N2 N6</p>
        <p>Tramvia: Encants - Sant Adrià</p>
        <p>Renfe: Sant Adrià del Besòs</p>
      </div>
    </div>
  </div>
</section>
