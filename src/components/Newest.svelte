<script>

    // let back = "<"
    // let forward = ">"
    // let width1 = "1500px"
    // let width2 = "0px"
    // let current = 1

    // function increment() {
    //     if (current == 1) {
    //         current++
    //     }
    // }

    // function decrement() {
    //     if (current == 2) {
    //         current--
    //     }
    // }

    // $: if (current == 1) {
    //     width1 = "1500px"
    //     width2 = "0px"
    // }

    // $: if (current == 2) {
    //     width1 = "0px"
    //     width2 = "1500px"
    // }

</script>

<main>

    <div class="container">
        <div class="content-container">
            <h1>Newest BuzzBoard</h1>
            <a href="#/OpenBuzzDogira">
                <div class="Item">
                    <div class="title">
                        <img src="/tokens/dogira.png" alt="Dogira">
                        <h2>Dogira</h2>
                    </div>
                    <div class="token-summary">
                        <p>
                          Dogira has been developed to allow holders exposure to a fledgling Blockchain Development
                          Studio & DeFi Platform, led by industry professionals.
                        </p>
                        <a href="https://www.dogira.net/">dogira.net</a>
                    </div>
                </div>
            </a>
        </div>
    </div>

</main>

<style>

    main {
        margin: 100px 0px 250px 0px;
        padding: 0px;
    }

    .container {
        display: grid;
        justify-items: center;
        align-items: center;
        grid-template-columns: auto;
    }

    .content-container {
        display: grid;
        grid-template-columns: auto;
        justify-items: center;
    }

    .content-container > a {
        text-decoration: none;
        
    }

    .Item {
        display: grid;
        grid-template-columns: auto;
        padding: 5px 10px 20px 10px;
        text-align: center;
        font-size: 15px;
        color: black;
        background-color:white;
        box-shadow: rgb(88 102 126 / 8%) 0px 4px 24px, rgb(88 102 126 / 12%) 0px 1px 2px;
        border-radius: 8px;
        border: 5px solid #0094fd;
        width: 500px;
        transition: 0.1s;
    }

    .Item:hover {
        cursor: pointer;
        transform: scale(1.02);
        box-shadow: rgb(88 102 126 / 8%) 0px 4px 24px, rgb(88 102 126 / 12%) 0px 1px 2px;
        background-color:#F9F871 ;
    }

    h1 {
        text-align: left;
        font-size: 30px;
        font-weight: 700;
        max-width: 700px;
        margin: 25px 0px;
        color: #0094fd;
        text-shadow: -1px -1px 0 #ffffff, 1px -1px 0 #ffffff, -1px 1px 0 #ffffff, 1px 1px 0 #ffffff;
    }

    .title {
        display: flex;
        grid-template-columns: auto auto;
        font-size: 15px;
        justify-items: center;
        align-items: center;
    }

    .title > img {
        width: 35px;
        height: 35px;
        border-radius: 15px 0px 0px 0px;
        margin: 0px 10px 0px 0px;
    }

    .title > h2 {
        font-size: 20px;
    }

    .token-summary {
        font-size: 15px;
        font-weight: 700;
    }

    @media (min-width: 401px) and (max-width: 555px) {

        .Item {
            width: 350px;
        }
    }

    @media (min-width: 280px) and (max-width: 400px) {

        h1 {
            text-align: center;
        }

        .Item {
            width: 200px;
        }
    }

    @media (min-width: 10px) and (max-width: 379px) {
    }

</style>