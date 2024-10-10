<script lang="ts">
  import Card from "./details/Card.svelte"

interface IPeople {
    photo: string,
    name: string,
    title: string,
    num: number,
    role: string
}

let people: IPeople[] = [
    {photo: "",
    name: "Maria Rita Ragusa.",
    title: "Psicóloga General Sanitaria.",
    num: 18.177,
    role: "Cofundadora de Nomad."
    },

    {photo: "",
    name: "Maria Rita Ragusa.",
    title: "Psicóloga General Sanitaria.",
    num: 18.177,
    role: "Cofundadora de Nomad."
    },

    {photo: "",
    name: "Maria Rita Ragusa.",
    title: "Psicóloga General Sanitaria.",
    num: 18.177,
    role: "Cofundadora de Nomad."
    },

    {photo: "",
    name: "Maria Rita Ragusa.",
    title: "Psicóloga General Sanitaria.",
    num: 18.177,
    role: "Cofundadora de Nomad."
    },

    {photo: "",
    name: "Maria Rita Ragusa.",
    title: "Psicóloga General Sanitaria.",
    num: 18.177,
    role: "Cofundadora de Nomad."
    },
]
</script>

<style lang="scss">
    .equip-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 75px;
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
                width: 600px;
            }
        }

        .cards {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 75px;

            
        }
    }
</style>

<div class="equip-container">
    <div class="title">
        <h1>Transformem la psicologia perquè puguis transformar la teva vida.</h1>
        <p>La diversitat del nostre equip multidisciplinari és la nostra major fortalesa. Junts, treballem 
            en sinergia per oferir-te el suport que millor s’adapti a les teves necessitats, acompanyant-te 
            en el teu camí cap al benestar amb professionalitat, empatia i compromís.</p>
    </div>

    <div class="cards">
        {#each people as person}
            <Card photo={person.photo}>
                <div class="info">
                    <div class="name">{person.name}</div>
                    <div class="title">{person.title}</div>
                    <div class="num">Col·legiada {person.num}.</div>
                    <div class="role">{person.role}</div>
                </div>
            </Card>
        {/each}
    </div>
</div>