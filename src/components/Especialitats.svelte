<script lang="ts">
    import Svg from "./details/Svg.svelte";

    let open = false

    let especialitats = [
        {
            title: "Psicoteràpia individual per nens, adolescents i adults.",
            description: "La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.",
        },
        {
            title: "Psicoteràpia individual per nens, adolescents i adults.",
            description: "La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.",
        },
        {
            title: "Psicoteràpia individual per nens, adolescents i adults.",
            description: "La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.",
        },
        {
            title: "Psicoteràpia individual per nens, adolescents i adults.",
            description: "La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.",
        },
        {
            title: "Psicoteràpia individual per nens, adolescents i adults.",
            description: "La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.",
        },
        {
            title: "Psicoteràpia individual per nens, adolescents i adults.",
            description: "La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.",
        },
        {
            title: "Psicoteràpia individual per nens, adolescents i adults.",
            description: "La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.",
        },
        {
            title: "Psicoteràpia individual per nens, adolescents i adults.",
            description: "La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.",
        },
        {
            title: "Psicoteràpia individual per nens, adolescents i adults.",
            description: "La psicoteràpia individual de nens, adolescents i adults s’inicia amb un procés diagnòstic previ on identificarem l’origen del conflicte i farem una proposta de tractament personalitzada amb la finalitat de proporcionar a la persona tant orientació com recursos per solucionar-ho.",
        },
        
    ]
</script>

<style lang="scss">
    .especialitats-container {
        padding: 75px;
        background-color: var(--colorBrandSofter);
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 60px;

        -webkit-interpolate-size: allow-keywords;

        .especialitats {
            display: flex;
            flex-direction: column;
            width: 75%;

            .especialitat {
                border-bottom: 1px solid;
                border-top: 1px solid;

                display: flex;
                justify-content: space-between;
                padding: 35px 0;
                height: 90px;
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
                }
                
                &.open {
                    height: calc-size(fit-content);
                    transition: 0.3s ease;
                }
            }
        }
    }
</style>

<div class="especialitats-container">
    <h1>Especialitats</h1>

    <div class="especialitats">
        {#each especialitats as especialitat}
            <button class="especialitat" on:click={() => open = !open} class:open>
                <div class="details">
                    <span>{especialitat.title}</span>
                    <p>{especialitat.description}</p>
                </div>
                
                <Svg name="plus"/>
            </button>
        {/each}
    </div>
</div>