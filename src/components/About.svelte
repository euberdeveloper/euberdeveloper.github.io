<h3>ABOUT ME</h3>
<div class="my-info">
    <p><span class="info-name">Name:</span>Eugenio Berretta</p>
    <p><span class="info-name">From:</span>Italy</p>
    <p><span class="info-name">Age:</span>{ age }</p>
    <p><span class="info-name">Now in:</span>Munich</p>
</div>
<div class="about">
    <div class="picture"></div>
    <p>
        I'm a { age } years old Italian student, currently attending a Masters Degree in Computer Science at TUM.<br />
        I'm passionate about data science and web development.
    </p>
</div>
<div class="urls">
    <a href="https://www.github.com/euberdeveloper/" target="_blank"><Github color='#ed9074' size='48' /></a>
    <a href="https://www.linkedin.com/in/eugenio-berretta/" target="_blank"><Linkedin color='#ed9074' size='48' /></a>
    <a href="mailto:euberdeveloper+curriculum@gmail.com" target="_blank"><Email color='#ed9074' size='48' /></a>
    <a href="https://www.t.me/eugeniovb/" target="_blank"><Telegram color='#ed9074' size='48' /></a>
    
</div>


<script lang="ts">
    import Github from "svelte-material-icons/Github.svelte";
    import Linkedin from "svelte-material-icons/Linkedin.svelte";
    import Email from "svelte-material-icons/Email.svelte";
    import Telegram from "svelte-material-icons/Telegram.svelte";

    const age = Math.floor( (new Date().getTime() - new Date(1999, 3, 23).getTime()) / 3.15576e+10 );
</script>


<style lang="less">
    .my-info {
        width: fit-content;
        margin: auto;
        display: grid;
        column-gap: 3em;
        grid-template-columns: 1fr 1fr;
        padding: 1.5em .5em;
        @media only screen and (max-width: 750px) { grid-template-columns: 1fr; }
    }
    .about {
        display: grid;
        grid-template-columns: 1fr auto;
        align-items: center;
        justify-content: center;
        @media screen and (max-width: 800px) {
            grid-template-columns: auto;
            align-items: center;
            justify-items: center;
        }
        .picture {
            width: 120px;
            height: 120px;
            background-image: url(../images/pro.jpg);
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            border-radius: 50%;
            margin: 1em;
            border: 4px solid var(--theme-2);
        }
    }

    .urls {
        display: flex;
        flex-direction: row;
        justify-content: center;
        margin: 1em auto;
        padding: 0 3em;
        border-top: 1px solid var(--theme-2);
        width: fit-content;

        a {
            padding: .5em 1em;
        }
    }
    p {
        margin: 0.3em 1em;
        font-size: 1.3em;
        .info-name {
            width: 90px;
            display: inline-block;
            color: #ed9074;
        }
    }
</style>