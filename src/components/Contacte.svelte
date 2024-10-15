<script lang="ts">
  import Svg from '@/components/details/Svg.svelte'
  export let id
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .contact-container {
    padding-top: 50px;
    padding-bottom: 50px;

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
            min-height: 25px;
            border: 1px solid #bebebe;
            border-radius: 5px;
            padding: 10px;
            font-size: 16px;
            outline: none;
          }

          textarea {
            height: 100px;
            resize: vertical;
          }

          &.radio {
            padding-top: 20px;
            padding-bottom: 30px;
            flex-direction: row;

            a:hover {
              color: var(--colorBrandSoft);
            }

            input {
              width: 25px;
              height: 25px;
              min-height: 0;
              border-radius: 100%;
            }

            align-items: center;
            font-size: 13px;
          }
        }
      }

      .info {
        width: 500px;
        padding-top: 40px;

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

        .logo {
          width: 100%;
          display: flex;
          justify-content: flex-start;
        }
      }

      @include notDesktop {
        flex-direction: column;

        .form,
        .info {
          width: 100%;

          .logo {
            justify-content: center;
          }
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
      <input type="hidden" name="access_key" value="155c3305-6d49-4f5e-a22b-71d5891a8c96" />

      <!-- Form Inputs. Each input must have a name="" attribute -->
      <div class="input-group">
        <label for="">Nom</label>
        <input type="text" name="Nom" required />
      </div>

      <div class="input-group">
        <label for="">Email</label>
        <input type="text" name="Email" required />
      </div>

      <div class="input-group">
        <label for="">Telèfon</label>
        <input type="text" name="Telèfon" required />
      </div>

      <div class="input-group">
        <label for="">Deixa el teu comentario</label>
        <textarea name="Missatge"></textarea>
      </div>

      <div class="input-group radio">
        <input type="checkbox" required />
        <label for="">He llegit i acepto la <a href="/politica-de-privacitat">Política de privacitat</a></label>
      </div>

      <!-- Honeypot Spam Protection -->
      <input type="checkbox" name="botcheck" class="hidden" style="display: none;" />

      <input type="hidden" name="redirect" value="http://localhost:4000/" />

      <button type="submit" class="g-btn">ENVIAR</button>
    </form>

    <div class="info">
      <div class="logo">
        <Svg name="logo2" width="150" height="80" />
      </div>

      <div class="info-text"><span>Direcció:</span> Carrer de l'Átlantida, 21, planta 2 08930 Sant Adrià del Besòs.</div>

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
