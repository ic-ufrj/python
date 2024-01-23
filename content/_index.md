<style>
    .gradient-box {
        width: 100%;
        height: 350px;
        background: linear-gradient(to bottom right, #02087d, #2e66ff);
        position: relative;
    }
    .cutout {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 100px;
        background: #fff; /* Cor da "corte" na diagonal */
        clip-path: polygon(0 100%, 100% 100%, 100% 0);
    }

    .titulo {
        position: absolute;
        top: 40px;
        color: #fff;
        font-size: 32px;
        font-weight: bold;
        width: 600px;
        left: 60px;
        font-family: system-ui;
    }
</style>

<div class="gradient-box">
    <div class="cutout"></div>
</div>
<div class="titulo">
    Bem-vindo ao curso de Introdução à Programação com Python do IC/UFRJ
</div>