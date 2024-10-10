<script lang="ts">
    import Input from "./details/Input.svelte";
    import Checkbox from "./details/Checkbox.svelte";
    import Button from "./details/Button.svelte"
</script>

<style lang="scss">
    .contact-container {
        padding: 75px;

        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 50px;

        .content {
            display: flex;
            justify-content: space-between;
            gap: 75px;

            .form {
                width: 500px;
                
                .checkbox {
                    display: flex;
                    align-items: center;
                    gap: 10px;
                    padding-bottom: 20px;
                    
                    span {
                        font-size: 13px;
                        
                        a:hover {
                                color: var(--colorBrandSoft);
                        }
                    }
                }
            }

            .info {
                width: 500px;

                display: flex;
                flex-direction: column;
                gap: 25px;

                .logo {
                    height: 75px;
                    width: 200px;
                    border: 1px solid;
                    margin-bottom: 15px;
                }

                .info-text {
                    max-width: 325px;
                    font-size: 15px;

                    span {
                        font-weight: bolder;
                    }
                }
            }
        }
    }
    </style>
    
<div class="contact-container">
    <h1>Contacte</h1>
    <div class="content">
        <div class="form">
            <Input id="1" label="Nom"/>
            <Input id="2" label="Mail" type="email"/>
            <Input id="3" label="Teléfon" type="tel"/>
            <Input id="4" label="Deixa el teu comentari." type="textarea"/>

            <div class="checkbox">
                <Checkbox/>
                <span>He llegit i acepto la <a href="/">Politica de Privacitat</a></span>
            </div>

            <Button><span>ENVIAR</span></Button>
        </div>

        <div class="info">
            <div class="logo"></div>

            <div class="info-text"><span>Direcció:</span> Carrer de l'Átlantida, 21, planta 2 08230 Sant Adrià del Besòs.</div>

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
</div>