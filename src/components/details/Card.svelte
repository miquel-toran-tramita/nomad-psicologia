<script lang="ts">
    import Svg from "./Svg.svelte"

    export let photo: string
    export let more: string
</script>

<style lang="scss">
    .card-container {
        position: relative;
        padding: 20px;

        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 25px;
        text-align: center;

        border-radius: 8px;
        overflow: hidden;

        :global(.plus) {
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

        .back {
            position: absolute;
            height: 100%;
            width: 100%;
            background-color: rgba(43, 54, 41, 0.65);
            top: 0;
            backdrop-filter: blur(5px);

            display: flex;
            flex-direction: column;
            gap: 10px;

            padding: 15px;
            font-size: 11px;
            text-align: start;
            font-weight: lighter;
            color: white;

            opacity: 0;
            transition: 0.3s ease;
        }
        
        &:hover {
            .back {
                transition: 0.3s ease;
                opacity: 1;
            }
        }
    }
</style>

<div class="card-container">
    <Svg name="plus" height="18" width="18" className="plus"/>

    <div class="photo">
        <img src={photo} alt="">
    </div>

    <slot/>

    <div class="back">
        <Svg name="minus" height="18" width="18" fill="white"/>
        {more}
    </div>
</div>