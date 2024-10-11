<script lang="ts">
  import Svg from './details/Svg.svelte'
  export let id

  let openIndex: number = 0

  let especialitats = [
    {
      title: 'Psicoteràpia individual per nens, adolescents i adults.',
      description:
        'La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.',
    },
    {
      title: 'Psicoteràpia individual per nens, adolescents i adults.',
      description:
        'La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.',
    },
    {
      title: 'Psicoteràpia individual per nens, adolescents i adults.',
      description:
        'La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.',
    },
    {
      title: 'Psicoteràpia individual per nens, adolescents i adults.',
      description:
        'La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.',
    },
    {
      title: 'Psicoteràpia individual per nens, adolescents i adults.',
      description:
        'La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.',
    },
    {
      title: 'Psicoteràpia individual per nens, adolescents i adults.',
      description:
        'La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.',
    },
    {
      title: 'Psicoteràpia individual per nens, adolescents i adults.',
      description:
        'La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.',
    },
    {
      title: 'Psicoteràpia individual per nens, adolescents i adults.',
      description:
        'La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.',
    },
    {
      title: 'Psicoteràpia individual per nens, adolescents i adults.',
      description:
        'La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.',
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
          }
        }

        &.open {
          height: auto;
          transition: 0.3s ease;

          p {
            display: block;
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
