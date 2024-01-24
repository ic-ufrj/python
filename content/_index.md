---
title: "Computação 1 em Python"
---

<style>
    .gradient-box {
        width: 100%;
        height: 400px;
        background: linear-gradient(to bottom right,#02087d,#2e66ff);
        position: absolute;
        margin: auto;
        top: 0;
        left: 0;
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

    .subtitulo {
        font-size: 15px;
        font-weight: 200;
        font-family: system-ui;
        margin-top: 20px;
    }

    .main-card {
        display: flex;
        margin: auto;
        max-width: 850px;
        margin-top: 240px;
        z-index: 8;
        position: relative;
    }

    @media only screen and (max-width: 600px) {
        .main-card {
           display: block;
           text-align: -webkit-center;
        }

        .titulo {
            font-size: 20px;
            width: 300px;
        }

        .subtitulo {
            font-size: 13px;
        }
    }

    .card {
        width: 300px;
        padding: 20px;
        background-color: #f7f7f7;
        border-radius: 8px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        text-align: center;
        margin: 10px;
        font-size: 14px;
        }

    .titulo-card {
        font-size: 25px;
        font-weight: 400;
        margin-top: 10px;
    }

    .link-lista {
        color: #fff;
        text-decoration: underline;
    }

    .link-lista:hover {
        color: #fff;
        font-weight: bold;
    }
</style>

<div class="gradient-box">
    <div class="cutout"></div>
</div>
<div class="titulo">
    Bem-vindo ao curso de Introdução à Programação com Python do IC/UFRJ
    <div class="subtitulo">
        Você pode acessar as aulas na
        <a class="link-lista" href="./aulas/index.html">lista de aulas</a>
        ou na barra barra lateral (em modo desktop), ou no menu hambúrguer (em dispositivos móveis).
    </div>
</div>
<div class="main-card">
    <div class="card">
        <i class="fas fa-code" style="font-size: 20px; margin: 10px;"></i>
        <div class="titulo-card">Importância da Programação</div>
        <p>A programação expande o pensamento lógico e estimula a resolução de problemas, habilidades essenciais em qualquer área profissional.</p>
    </div>
    <div class="card">
        <i class="fab fa-python" style="font-size: 20px; margin: 10px;"></i>
        <div class="titulo-card">Por que Python?</div>
        <p>Python é uma linguagem versátil e poderosa, facilitando a entrada no mundo da programação. É usada em diversas áreas, desde desenvolvimento web até inteligência artificial.</p>
    </div>
    <div class="card">
        <i class="fas fa-graduation-cap" style="font-size: 20px; margin: 10px;"></i>
        <div class="titulo-card">Aprenda Agora!</div>
        <p>Comece sua jornada de aprendizado em programação com Python. Aprender a programar abre portas para oportunidades incríveis de crescimento profissional.</p>
    </div>
</div>

# Python para Iniciantes
# Conheça o curso desenvolvido pelo IC‑UFRJ

Bem vindos ao material do curso de Computação I do
[Instituto de Computação](https://ic.ufrj.br)
da Universidade Federal do Rio de Janeiro.

Esse material, agora aberto ao público em geral,
foi desenvolvido com base em proposta pedagógica
[desenvolvida por docentes do IC-UFRJ](https://doi.org/10.5753/wei.2016.9683)
O formato apresentado aqui foi desenvolvido durante
o período de isolamento social devido à pandemia de COVID-19,
para o chamado "Ensino Remoto Emergencial".
Isso significa que foi concebido como material de apoio
a uma turma regular das disciplinas ICP114 e ICP121 (Computação I)
oferecidas pelo IC a alunos de diversos cursos da UFRJ,
para ser seguido com acompanhamento regular de um(a) professor(a).

Mas isso não significa que não possa também ser usado de maneira autônoma
por estudantes interessados em aprender noções básicas de programação através da linguagem Python.
Se é o seu caso, por que não experimentar?

Cada aula é dirigida por um roteiro,
com parte do conteúdo apresentado por escrito
e parte do conteúdo apresentado através de vídeos.
Disponibilizamos também alguns exercícios com correção automática
através de formulários online e algumas listas de exercícios (ou laboratórios)
com problemas para os quais pedimos que desenvolvam uma solução em Python.
