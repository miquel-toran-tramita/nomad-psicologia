<script lang="ts">
    import Svg from "./details/Svg.svelte";
</script>

<style lang="scss">
    .portada-content {
        position: relative;
        width: 100%;
        height: 55dvh;
        background-color: var(--colorBrand);

        .coneixens {
            position: absolute;
            bottom: 20px;
            right: 0;
            left: 0;
            margin: 0 auto;

            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 5px;

            span {
                color: white;
                font-weight: 100;
                font-size: 13px;
            }
                
            :global(svg) {
                transform: rotate(-90deg);
            }
        }
    }
</style>

<div class="portada-content">
    <div class="logo"></div>
    <div class="coneixens">
        <span>Coneixe'ns</span>
        <Svg name="arrow2" fill="white"/>
    </div>
</div>