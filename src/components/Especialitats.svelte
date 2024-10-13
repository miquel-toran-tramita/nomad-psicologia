<script lang="ts">
  import Svg from './details/Svg.svelte'
  export let id

  let openIndex: number = 0

  let especialitats = [
    {
      title: 'Psicoteràpia individual per nens, adolescents i adults',
      description:
        'La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.',
    },
    {
      title: 'Psicoteràpia de família i de parella',
      description:
        'Quants més siguem a terapia més recursos tindrem a disposició de la resolució dels problemes. En la majoria de les situacions la conflictivitat no només afecta a la persona amb el diagnòstic (‘pacient identificat’), sinó a tot el sistema relacional.',
    },
    {
      title: 'Psicoteràpia grupal',
      description:
        'El treball terapèutic dins d’un grup ens permet dur a terme el tractament en un espai segur on poder-nos sentir escoltats i acompanyats, des de l’empatia i el respecte mutu. Un espai en què qualsevol company és algú amb qui recolzar-nos i que ens pot aportar una visió nova que possibiliti el canvi i la millora individual.',
    },
    {
      title: 'Espais de pares',
      description:
        "Oferim un espai d’orientació per a mares i pares on poder reflexionar conjuntament sobre la paternitat, compartir emocions, trobar respostes i aportar pautes educacionals concretes, per tal d'obtenir més confiança i seguretat en les seves tasques parentals.",
    },
    {
      title: 'Espais de reflexió (Tallers i xerrades)',
      description:
        'Organitzem tallers i xerrades amb l’objectiu de generar espais de reflexió dinàmics i vivencials, a partir de les necessitats i demandes que ens arriben des de les escoles i els instituts.',
    },
    {
      title: 'Logopèdia',
      description:
        'A partir del disseny d’activitats per la prevenció, avaluació i tractament dels trastorns de la comunicació, el llenguatge, la parla, l’audició i les funcions orals no verbals, intentem millorar les capacitats comunicatives de cada persona.',
    },
    {
      title: 'Reeducació',
      description:
        "Concebem la reeducació pedagògica com un tractament psicològic dinàmic basat en una relació terapèutica en què el nen és part activa, amb l'objectiu de treballar les dificultats en els processos d’aprenentatge que afecten el rendiment acadèmic.",
    },
    {
      title: 'Assessorament a professionals',
      description:
        'El servei de formació i assessorament a professionals té la finalitat d’orientar i proporcionar recursos a professionals de diferents àmbits assistencials, a través de la creació d’espais de trobada multidisciplinaris.',
    },
    {
      title: 'Supervisions Clíniques',
      description:
        'La supervisió clínica és un dels eixos fonamentals de NOMAD, on oferim espais de supervisió grupal o individual per a professionals de la salut, amb l’objectiu de treballar casos clínics i promoure el creixement personal i professional.',
    },
  ]

  const openClick = (i: number) => {
    if (openIndex === i) {
      openIndex = -1
      return
    }

    openIndex = i
  }
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .especialitats-container {
    padding: 75px 0;
    background-color: var(--colorBrandSofter);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 60px;

    .especialitats {
      display: flex;
      flex-direction: column;
      width: 100%;

      @include notDesktop {
        :global(svg) {
          display: none;
        }
      }

      .especialitat {
        border-bottom: 1px solid;

        display: flex;
        justify-content: space-between;
        padding: 35px 0;
        overflow: hidden;
        transition: 0.3s ease;

        .details {
          max-width: 750px;
          text-align: start;
          display: flex;
          flex-direction: column;
          gap: 30px;

          span {
            font-size: 20px;
            font-weight: bold;
          }

          p {
            display: none;
            opacity: 0;
            translate: 0 -25px;
            transition-property: display opacity;
            transition-duration: 0.3s;
            transition-behavior: allow-discrete;
          }
        }

        &.open {
          height: auto;
          transition: 0.3s ease;

          p {
            display: block;
            opacity: 1;
            translate: 0 0;

            @starting-style {
              opacity: 0;
              translate: 0 -25px;
            }
          }
        }

        &.top {
          border-top: 1px solid;
        }
      }
    }
  }
</style>

<section class="especialitats-container" {id}>
  <h1>Especialitats</h1>

  <div class="especialitats g-wrapper">
    {#each especialitats as especialitat, i}
      <button class="especialitat" on:click={() => openClick(i)} class:open={openIndex === i} class:top={i === 0}>
        <div class="details">
          <span>{especialitat.title}</span>
          <p>{especialitat.description}</p>
        </div>

        <Svg name="plus" />
      </button>
    {/each}
  </div>
</section>
