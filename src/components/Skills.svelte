<h3>Skills</h3>
<div class="skills">
    
    <h4 class="spacer">SOFT SKILLS:</h4>
    <p class="spacer"> Problem solving, Work under pressure, Team work </p>

    <h4>PROGRAMMING LANGUAGES:</h4>
    <p> Typescript, Python, C++, Java, Javascript, Kotlin </p>

    <h4>FRONTEND FRAMEWORKS:</h4>
    <p> Vue, Angular, Svelte, React </p>

    <h4>BACKEND FRAMEWORKS:</h4>
    <p> Express.js, Flask </p>

    <h4>DESKTOP & MOBILE:</h4>
    <p> Electron, Android Studio </p>

    <h4>DATABASES:</h4>
    <p> Postgtres, MariaDB, MongoDB, Redis </p>

    <h4>IT TOOLS:</h4>
    <p> Git, Docker, VSCode, Postman </p>

</div>


<script lang="ts">
</script>


<style lang="less">
    h4 {
        color: var(--theme);
        text-align: right;
    }
    p, h4 {
        font-size: 1.5em;
        margin: 0.5em 0;
    }

    .spacer {
        margin-bottom: 1.5em;
    }

    .skills {
        display: grid;
        grid-template-columns: 1fr auto;
        align-items: center;
        column-gap: 2em;
    }

    @media only screen and (max-width: 750px) {
        p, h4 {
            text-align: center;
        }
        h4 {
            margin-bottom: 0 !important;
        }
        .skills {
            grid-template-columns: auto;
        }

     }

</style>