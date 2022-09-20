<script lang="ts">
    import Github from "svelte-material-icons/Github.svelte";

    export let darkTheme: boolean;

    type Project = { name: string; description: string; link: string };
    const projects: { name: string; projects: Project[] }[] = [
        {
            name: "Web",
            projects: [
                {
                    name: "CV",
                    link: "https://github.com/euberdeveloper/euberdeveloper.github.io",
                    description: "This website",
                },
                {
                    name: "Unitn Tronchet",
                    link: "https://github.com/euberdeveloper/unitn-tronchet",
                    description:
                        'About Site where there are simulations of the theoric part of unitn exam "linguaggi di programmazione - mod 1"',
                },
                {
                    name: "GIF Analyzer",
                    link: "https://github.com/euberdeveloper/gif-analyzer-webapp",
                    description: "A PWA to analyze the parts of a GIF file.",
                },
            ],
        },
        {
            name: "NPM libraries",
            projects: [
                {
                    name: "Dree",
                    link: "https://github.com/euberdeveloper/dree",
                    description:
                        "A nodejs module wich helps you handle a directory tree",
                },
                {
                    name: "Mongoback",
                    link: "https://github.com/euberdeveloper/mongodb",
                    description:
                        "The most powerful npm module to export and make backups of your MongoDB",
                },
                {
                    name: "Video Scraper Core",
                    link: "https://github.com/euberdeveloper/video-scraper-core",
                    description:
                        "An npm module to retrieve the databases and the collections of a mongodb.",
                },
                {
                    name: "Mongo Scanner",
                    link: "https://github.com/euberdeveloper/mongo-scanner",
                    description:
                        "Get the latest daily grade of a course at the University of Trento",
                },
                {
                    name: "Euberlog",
                    link: "https://github.com/euberdeveloper/euberlog",
                    description: "A beautiful nodejs logger",
                },
            ],
        },
    ];
</script>

<h3>Personal Projects</h3>
<div class="somethings">
    {#each projects as prjs}
        <div class="something">
            <h4>{prjs.name}</h4>
            <div class="list">
                {#each prjs.projects as p}
                    <a href={p.link} target="”_blank”">
                        <p class="name">{p.name}</p>
                        <p class="description">{p.description}</p>
                    </a>
                {/each}
            </div>
        </div>
    {/each}
</div>
<div class="more-github">
    <a
        href="https://github.com/euberdeveloper"
        target="_blank"
        class={darkTheme ? "dark" : "#000"}
    >
        <p>And many more on my Github</p>
        <Github color="#FFF" size="32" />
    </a>
</div>

<style lang="less">
    a {
        color: inherit;
    }
    .something {
        max-width: 780px;
        margin: auto;
        border-bottom: 1px solid var(--theme);
        padding: 1.5em;

        .list {
            a {
                display: grid;
                grid-template-columns: 1fr 3fr;
                grid-gap: 2em;
                border-radius: 5px;
                padding: 0.3em;

                &:hover {
                    background-color: var(--theme-3);
                    color: white;
                }

                p {
                    margin: 0;
                }
                p.name {
                    color: var(--theme);
                    text-align: right;
                }
            }
        }

        &:last-child {
            border-bottom: none;
        }

        h4 {
            margin-top: 0;
            text-align: center;
            font-weight: bolder;
            color: var(--theme);
            font-size: 1.2em;
        }
    }

    .more-github {
        display: flex;
        justify-content: center;
        a {
            display: inline-block;
            text-transform: uppercase;
            font-size: 1.2em;
            margin-top: 2em;
            padding: 1em;
            border-radius: 5px;
            display: flex;
            align-items: center;
            background-color: var(--theme);
            &.dark {
                background-color: var(--theme-3);
            }

            p {
                margin: 0;
                margin-right: 1em;
                color: white;
            }
            &:hover {
                text-decoration: none;
            }
        }
    }
</style>
