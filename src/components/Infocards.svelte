<script>

</script>

<main>

    <div class="container">

        <div class="item">
            <div class="image-container">
                <img src="/icons/community.png" alt="UI">
            </div>
            <div class="description">
                <div>
                    <h1>Community Centered</h1>
                    <p>
                      Our main focus is on serving communities, the cornerstone of a all great projects. We want to give your community 
                      a place to chat and shill while burning tokens.
                    </p>
                </div>
            </div>
        </div>

        <div class="item">
            <div class="image-container">
                <img src="/icons/duck.png" alt="Buzzin">
            </div>
            <div class="description">
                <div>
                    <h1>Post For Fun</h1>
                    <p>
                       Whether it's pasta, not financial advice or plain old shitposting, OpenBuzz is here for you. Users can decide what they like and what they don't 
                       using the reaction functions that determine the rank of a post.
                    </p>
                </div>
            </div>
        </div>

        <div class="item">
            <div class="image-container">
                <img src="/icons/bingo.png" alt="bingo">
            </div>
            <div class="description">
                <div>
                    <h1>Win With Each Message</h1>
                    <p>
                       To make posting on OpenBuzz even more attractive, every post is entered into a 
                       drawing, then has the opportunity to win the prize pool, awarded after the 100th message is posted. 
                    </p>
                </div>
            </div>
        </div>

        <div class="item">
            <div class="image-container">
                <img src="/icons/link.png" alt="Chainlink VRF">
            </div>
            <div class="description">
                <div>
                    <h1>Fair And Provable Randomness</h1>
                    <p>
                       To ensure everything is fair and decentralized, all random rolls are made using Chainlink's verifable random number generator.
                       At the start of a new cycle the previous prize pool winner's wallet address will be displayed on the top of the board so the transaction can be seen by everyone.  
                    </p>
                </div>
            </div>
        </div>

    </div>

    <div class="info-sentence"> 
        <p>
            After reaching 100 messages, the BuzzBoard will be locked to new messages and cleared to make room for the next cycle.
        </p>
    </div>

</main>

<style>

/* .section-1 {
    display: grid;
    justify-items: center;
    align-items: center;
    padding: 30px 0px 170px 0px;
    background: linear-gradient(90deg, #0094FD 0%, #0094FD 20%, #00D2EA 40%, #00E7B9 60%, #93F489 80%, #F9F871 100%);
} */

.container {
    /* background: #f4f4f581; */
    display: grid;
    justify-items: center;
    padding: 0px;
    margin: 0px 10px;
    grid-template-columns: auto auto;
}

.item {
    display: grid;
    padding: 0px;
    grid-template-columns: auto auto;
    margin: 10px;
    border: 5px solid black;
    border-radius: 15px;
    width: 700px;
    background-color: #fefefe;
}

.item > .image-container > img {
    padding: 50px;
} 

.item > .description {
    padding: 0px 15px;
    justify-items: left;
} 

h1 {
    color: #F9F871;
    text-shadow: -1px -1px 0 #000000, 1px -1px 0 #000000, -1px 1px 0 #000000, 1px 1px 0 #000000;
    font-weight: 700;
}

p {
    font-weight: 700;
}

img {
    width: 100px;
    height: 95px;
    border-radius: 8px 0px 0px 8px;
}

.info-sentence {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 25px;
}

.info-sentence > p {
    text-align: center;
    font-size: 20px;
    font-weight: 700;
    color: white;
    text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
}

@media (min-width: 751px) and (max-width: 1500px) {
    .container {
        grid-template-columns: auto;
    }
}

@media (min-width: 251px) and (max-width: 750px) {
    .container {
        grid-template-columns: auto;
    }

    .item {
        grid-template-columns: auto;
        margin: 10px;
        width: auto;
    }

    .item > .image-container {
        text-align: center;
    }

    h1 {
        text-align: center;
    }

    p {
        text-align: center;
    }
}

</style>