<h3>{ titles[type] }</h3>
<div class="boxes">
    {#each boxes as b}
    <div class="{b.flipped ? 'box flipped' : 'box'}">
        <div class="box-img">
            { #if b.img }
            <img src="{ b.img }" alt="">
            { /if }
        </div>
        <div class="box-title">
            <h4>
                { b.title }
            </h4>
            { #if b.subtitles }{#each b.subtitles as s}
                <div class="subtitle">
                    { #if s.flag } <img src="./images/flags/{s.flag.toLowerCase()}.svg" alt="flag" class="flag" /> { /if }
                    <h5>{ s.text }</h5>
                </div>
            { /each }{ /if }
        </div>
        <div class="box-description">
            <p>{@html b.description }</p>
            { #if b.more }
                { #if b.showMore } <p class="more">{@html b.more }</p> { /if }
                <p class="show-more" on:click={ () => { b.showMore = !b.showMore} }>{b.showMore ? 'Show less' : 'Show more'}</p>
            { /if }
            <span class="fi fi-gr"></span> <span class="fi fi-gr fis"></span>

        </div>
    </div>
    {/each}
</div>

<script lang="ts">
    import { text } from 'stream/consumers';
    import { It, Se, De, Es} from "svelte-flag-icons";
    export let type: string;

    const flagsComp = { It, Se, De, Es }

    type Box = {
        img?: string,
        title: string,
        subtitles?: {flag?: string, text: string}[],
        description: string,
        more?: string,
        showMore?: boolean,
        flipped?: boolean
    };

    const titles = {
        Education: 'Education',
        Experience: 'Work Experiences',
        Projects: 'Other Experiences'
    };

    const infos: { [id: string]: Box[] } = {
        Education: [
            {
                img: "./images/kth.jpg",
                title: "Attending Master's in Computer Science",
                subtitles: [
                    {flag: "De", text: "TUM, Munich, Germany | October 2021 - Current"},
                ],
                description: "\
                I am currently attending a Master degree in Computer Science at TUM",
                showMore: false,
                more: null
            },
            {
                img: "./images/trento.jpg",
                title: "Bachelor's in Computer Science",
                subtitles: [
                    { flag: 'It', text: "Università di Trento, Trento, Italy | September 2018 - July 2022" }
                ],
                description: "\
                I have taken courses in Software Engineering, Data Structures, Algorithms, and Programming and Mathematics.\
                I graduated with the highest grade of 110 cum laude in July 2022",
                showMore: false,
                more: "The complete list of courses I have taken:\
                <ul>\
                <li>Algorithms and Data Structures</li>\
                <li>Computer Programming 1</li>\
                <li>Programming Languages</li>\
                <li>Software Engineering 1 & 2</li>\
                <li>Geometry and Linear Algebra</li>\
                <li>Calculus 1</li>\
                <li>Probability and Statistics</li>\
                <li>Mathematical Foundations of Computer Science</li>\
                <li>Logic</li>\
                <li>Operating Systems</li>\
                <li>Databases</li>\
                <li>Networks</li>\
                <li>Physics</li>\
                <li>Computer Architectures</li>\
                <li>Human-Computer Interaction</li>\
                <li>Formal Languages and Compilers</li>\
                <li>Introduction to Machine Learning</li>\
                <li>Introduction to Web Programming</li>\
                <li>Introduction to Computer and Network Security</li>\
                </ui>\
                "
            },
        ],
        Experience: [
            {
                flipped: true,
                img: "./images/lifeware.jpg",
                title: "Lifeware SA",
                subtitles: [
                    { flag: 'Lu', text: "Lifeware, Luxembourg | February 2022 - Current" }
                ],
                description: "Working remotely as software engineer for Lifeware, a company that develops software for insurance companies"
            },
            {
                flipped: true,
                img: "./images/euberlogo.jpg",
                title: "Free Lance Developer",
                subtitles: [
                    { flag: 'It', text: "Valdagno, Italy" }
                ],
                description: "Worked as Full Stack developer to make websited for small businesses, including both static websites and web applications developed with Node.js"
            },
            {
                flipped: true,
                img: "./images/wiki.jpg",
                title: "Computer Science Internship",
                subtitles: [
                    { flag: 'Es', text: "Eurecat, Barcelona, Spain | January - June 2021" }
                ],
                description: "Analyzing important patterns in Wikipedia contributors' retention over time using Python."
            },
            {
                flipped: true,
                img: "./images/operatn.jpg",
                title: "OperaTN",
                subtitles: [
                    { flag: 'It', text: "Trento, Italy" }
                ],
                description: "Worked for the \"150 ore\" program of the Università di Trento, in which I developed the new internal management system for the \"Opera Universitaria\", organization that handles the student accomodations.\
                <br>\
                <a href=\"https://github.com/operatn\">Github organization</a>\
                <br>\
                <a href=\"https://operatn.operauni.tn.it\">Website</a>"
            }
        ],
        Projects: [
            {
                img: "./images/eagle.jpg",
                title: "Eletric Racing Car Telemetry",
                subtitles: [
                    { flag: 'It', text: "Eagle TRT, Trento, Italy | October 2019 - October 2021" }
                ],
                description: "PM of the telemetry team at EagleTRT, the Formula SAE group of Trento"
            },
            {
                img: "./images/soi.jpg",
                title: "School of innovation",
                subtitles: [
                    { flag: 'It', text: "Trento, Italy | September 2020 - April 2021" }
                ],
                description: "Extracurricolar program at Università di Trento focused on innovation and entrepreneurship"
            }
        ],
    };

    const boxes = infos?.[type] ?? [];

</script>


<style lang="less">
    h4 {
        font-size: 1.2em;
        margin: 3px 0;
    }
    .subtitle {
        display: flex;
        align-items: center;
        h5 {
            font-size: 1em;
            margin: 3px 0;
        }
        .flag {
            height: 1.3em;
            margin-top: 3px;
            margin-bottom: 3px;
            margin-right: 0.5em;
        }
    }
    .box {
        display: grid;
        grid-template-columns: auto 1fr;
        grid-template-rows: auto auto;
        padding: 1em 3em;
        column-gap: 3em;
        border-bottom: 1px solid var(--theme);

        @media screen and (max-width: 800px) {
            grid-template-columns: auto;
            grid-template-rows: auto auto;
            column-gap: 0;
            padding: 1em;

            .box-img {
                grid-row: auto !important;
                grid-column: auto !important;
                img {
                    margin-bottom: 1em;
                }
            }
        }

        &:last-child {
            border-bottom: none;
        }
        
        .box-img {
            align-self: flex-start;
            justify-self: center;
            grid-row: 1 / 3;
            img {
                border-radius: 25%;
                width: 120px;
                height: 120px;
            }
        }
        
        &.flipped {
            .box-img {
                grid-column: 2 / 3;
            }
        }

    }
</style>