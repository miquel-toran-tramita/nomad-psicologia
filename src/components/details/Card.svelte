<script lang="ts">
    import Svg from "./Svg.svelte"

    export let photo: string
</script>

<style lang="scss">
    .card-container {
        position: relative;
        padding: 15px;
                
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 25px;
        text-align: center;

        border: 1px solid;
        border-radius: 8px;

        :global(svg) {
            position: absolute;
            top: 15px;
            left: 15px;
        }

        .photo {
            height: 200px;
            width: 200px;
            border-radius: 100%;
            background-color: var(--colorBrandSofter);
        }
    }
</style>

<div class="card-container">
    <Svg name="plus" height="20" width="20"/>

    <div class="photo">
        <img src={photo} alt="">
    </div>

    <slot/>
</div>