<script lang="ts">
  import Card from './details/Card.svelte'

  interface IMember {
    photo: string
    name: string
    title: string
    num: number
    role: string
    description: string
  }

  const team: IMember[] = [
    {
      photo: 'Maria-Rita',
      name: 'Maria Rita Ragusa.',
      title: 'Psicóloga General Sanitaria.',
      num: 18.177,
      role: 'Cofundadora de Nomad.',
      description:
        "La meva professió sempre ha sigut una font d'aprenentatge personal, així mateix, veig la psicoteràpia com la co-creació d'un espai transicional on la persona pugui desenvolupar la seva personalitat. La meva formació ha estat focalitzada en la psicoanàlisis, amb especial atenció en els Trastorns de la Personalitat, tant en adults com en adolescents. Paral·lelament he participat en projectes d'investigació relacionats amb la Teoria de l'aferrament, en grups de supervisió clínica i en seminaris d'estudi dels autors fonamentals de la psicoanàlisi.",
    },

    {
      photo: 'Diego',
      name: 'Maria Rita Ragusa.',
      title: 'Psicóloga General Sanitaria.',
      num: 18.177,
      role: 'Cofundadora de Nomad.',
      description: '',
    },

    {
      photo: 'Adria',
      name: 'Maria Rita Ragusa.',
      title: 'Psicóloga General Sanitaria.',
      num: 18.177,
      role: 'Cofundadora de Nomad.',
      description: '',
    },

    {
      photo: 'Loida',
      name: 'Maria Rita Ragusa.',
      title: 'Psicóloga General Sanitaria.',
      num: 18.177,
      role: 'Cofundadora de Nomad.',
      description: '',
    },

    {
      photo: 'Marta',
      name: 'Maria Rita Ragusa.',
      title: 'Psicóloga General Sanitaria.',
      num: 18.177,
      role: 'Cofundadora de Nomad.',
      description: '',
    },
    {
      photo: 'Irene',
      name: 'Maria Rita Ragusa.',
      title: 'Psicóloga General Sanitaria.',
      num: 18.177,
      role: 'Cofundadora de Nomad.',
      description: '',
    },
    {
      photo: 'Lorena',
      name: 'Maria Rita Ragusa.',
      title: 'Psicóloga General Sanitaria.',
      num: 18.177,
      role: 'Cofundadora de Nomad.',
      description: '',
    },
    {
      photo: 'Alex',
      name: 'Maria Rita Ragusa.',
      title: 'Psicóloga General Sanitaria.',
      num: 18.177,
      role: 'Cofundadora de Nomad.',
      description: '',
    },
  ]
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .equip-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 50px 0;
    gap: 75px;

    .title {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      gap: 25px;
      max-width: 875px;
      width: 100%;

      h1 {
        max-width: 600px;
        width: 100%;
      }
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 75px;

      .info {
        display: flex;
        flex-direction: column;
        font-size: 13px;

        .name {
          font-weight: bolder;
        }
      }

      @include notDesktop {
        grid-template-columns: repeat(1, 1fr);
      }
    }
  }
</style>

<div class="equip-container">
  <div class="title g-wrapper">
    <h1>Transformem la psicologia perquè puguis transformar la teva vida.</h1>
    <p>
      La diversitat del nostre equip multidisciplinari és la nostra major fortalesa. Junts, treballem en sinergia per oferir-te el suport
      que millor s’adapti a les teves necessitats, acompanyant-te en el teu camí cap al benestar amb professionalitat, empatia i compromís.
    </p>
  </div>

  <div class="cards g-wrapper">
    {#each team as member}
      <Card photo={member.photo} more={member.description}>
        <div class="info">
          <span class="name">{member.name}</span>
          <span>{member.title}</span>
          <span>Col·legiada {member.num}.</span>
          <span>{member.role}</span>
        </div>
      </Card>
    {/each}
  </div>
</div>
