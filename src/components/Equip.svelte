<script lang="ts">
  import Card from './details/Card.svelte'
  export let id

  interface IMember {
    photo: string
    name: string
    title: string
    num: string
    role: string
    description: string
  }

  const team: IMember[] = [
    {
      photo: 'Murillo',
      name: 'Murillo Motta.',
      title: 'Psicòleg General Sanitari.',
      num: '25.073',
      role: 'Cofundador de Nomad.',
      description:
        'La meva formació ha estat focalitzada en la psicoanálisis de nens, adolescents i adults. Paral·lelament he participat en projectes de investigació relacionats amb la Teoria de l’Aferrament, en grups de supervisió clínica i en seminaris d’estudi dels autors fonamentals de la psicoanàlisi. <br/><br/>He treballat com a psicoterapeuta en centres públics i privats d’atenció a la salut mental, tant individual com grupal, amb infants, adolescents i adults que presentaven diferents tipus de trastorns. Així mateix vaig impartir tallers i xerrades formatives.',
    },

    {
      photo: 'Maria-Rita',
      name: 'Maria Rita Ragusa.',
      title: 'Psicóloga General Sanitaria.',
      num: '18.177',
      role: 'Cofundadora de Nomad.',
      description:
        'La meva experiència i formació professional, d’orientació psicoanalítica, s’ha focalitzat a l’àrea de la psicologia clínica tant d’adults com infanto-juvenil. He complementat la meva formació realitzant un Post-grau teòric-clínic en Psicopatologia del nen, de l’adolescent i la família i una formació en Trastorn de l’Espectre Autista. <br/><br/>He treballat i col·laborat amb diversos centres de salut mental tant d’adults, com infanto-juvenils, i Hospital de dia (Trastorns de la Conducta Alimentaria). <br/><br/>Actualment, treballo i sóc co-fundadora en Nomad Psicología.',
    },

    {
      photo: 'Diego',
      name: 'Diego Piñero Leciñena.',
      title: 'Psicòleg General Sanitari.',
      num: '20.005',
      role: 'Cofundador de Nomad.',
      description:
        'La trobada amb diferents professionals ha constituït l’eix fonamental en la meva construcció com a professional, realitzant diverses formacions en psicoteràpia psicoanalítica amb nens, adolescents i adults especialitzant-me en psicodiagnòstic amb tècniques projectives gràfiques i assetjament escolar. <br/><br/>La meva experiència professional com a psicòleg s’ha centrat en l’àmbit clínic amb nens, adolescents i adults i en l’àmbit educatiu en diferents escoles i he coordinat diferents equips professionals. Realitzo supervisions a professionals de diferents àmbits i soc co-fundador de Nomad Psicologia.',
    },

    {
      photo: 'Adria',
      name: 'Adrià Puente Sabater.',
      title: 'Psicòleg i terapeuta familiar i de parella.',
      num: '22.571',
      role: 'Cofundador de Nomad.',
      description:
        'La meva formació com a psicoterapeuta engloba el constructivisme i la teràpia familiar sistèmica (Escola de Teràpia Familiar de Sant Pau). Des d’aquests models he desenvolupat una mirada capacitadora cap a les persones i treballo per potenciar-la. Penso que construint i enfortint els vincles més significatius de la vida podem trobar els recursos necessaris pel canvi. <br/><br/>Des de fa anys treballo en diferents camps, com les addiccions i les dependències, i famílies que pateixen situacions de vulnerabilitat.',
    },

    {
      photo: 'Loida',
      name: 'Loida Silvestre Celada.',
      title: 'Logopeda.',
      num: '08-3329',
      role: '',
      description:
        'Diplomada en logopèdia al 2005 per La universitat Ramón Llull, centrant la meva formació en la logopèdia escolar per atendre les demandes infanto-juvenils. Especialitzada en la feminització de la veu per a persones trans. <br/><br/>La meva trajectòria professional s’ha basat principalment en centres privats multidisciplinars encara que des de fa uns anys combino aquesta feina amb la intervenció directa a escoles de Badalona i Sant Adrià del Besòs i col·laborant dins del projecte de Proinfància de la Fundació la Caixa.',
    },

    {
      photo: 'Marta',
      name: 'Marta Febrer Vilaseca.',
      title: 'Psicóloga General Sanitaria.',
      num: '23.347',
      role: '',
      description:
        'La meva formació s’ha basat principalment en la psicologia clínica amb infants i adolescents realitzant un màster i un postgrau a l’Escola de Clínica Psicoanalítica amb Nens i Adolescents (ECPNA), en la intervenció familiar sistèmica realitzant un postgrau al Centre Kine i m’he format en intervenció psicosocial en violència masclista i familiar a l’Associació Conexus. <br/><br/>Professionalment he treballat en  infància i l’ adolescència i l’acompanyament dels adults de referència.',
    },
    {
      photo: 'Irene',
      name: 'Irene Garcia Bergé.',
      title: 'Psicóloga General Sanitaria.',
      num: '11.403',
      role: '',
      description:
        'La meva formació l’he cursada d’acord amb el meu recorregut professional dins de diferents àmbits en del camp de la psicologia. Específicament en l’àmbit clínic i terapèutic, m’he especialitzat en una vessant psicoanalítica i, actualment, estic immersa en profunditzar en l’etapa de la infància i l’adolescència formant-me en diferents escoles com ara a l’Escola de Clínica Psicoanalítica amb Nens i Adolescents (ECPNA). També he participat en sessions clíniques i sessions de supervisió psicològica.',
    },
    {
      photo: 'Lorena',
      name: 'Lorena Santana Rodríguez.',
      title: 'Psicóloga General Sanitaria.',
      num: '27.572',
      role: '',
      description:
        'Graduada en Psicologia, amb menció en Psicologia de la Salut, per la Universitat Oberta de Catalunya, ampliant els meus coneixements amb l’especialització en Teràpia Sistèmica Breu i amb la formació específica en trauma, vincle i dependència emocional. <br/><br/>Desenvolupo la meva activitat com a terapeuta i formadora en l’Àrea de Feminismes i LGTBIQ+ de l’Ajuntament de Barcelona, on acompanyo a dones CIS i trans, víctimes de l’explotació sexual i formes de violència de gènere dintre del col·lectiu LGTBIQ+.',
    },
    {
      photo: 'Alex',
      name: 'Alex Puig Folcrà.',
      title: 'Psicòleg i educador social.',
      num: ' 26.401',
      role: '',
      description:
        'M’he format dins el camp de la psicologia relacional i constructivista realitzant el Màster en Teràpia Cognitivo-social de la Universitat de Barcelona i  en  el camp de la psicoteràpia sistèmica, ja que considero que  aquestes orientacions em proporcionen eines per poder intervenir de forma integral tant a nivell individual com familiar i grupal.',
    },
  ]
</script>

<style lang="scss">
  @import 'src/sass/mixins.scss';

  .equip-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 75px 0;
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

<section class="equip-container" {id}>
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
</section>
