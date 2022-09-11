<script>

</script>

<main>

    <div class="fourth-info-container">
        <p>
          The main focus of OpenBuzz is the communities and for them to have fun writing and reading messages.
        </p>
        <div>
          <img src="/ui-1.png" alt="UI">
        </div>
        <p> 
          Whether it's copypasta, advice or just shitposting, users can decide for themselves what they like and what they don't 
          using the reaction functions that determine the rank of a post.
        </p>
        <div>
          <img src="/buzzin.gif" alt="Buzzin">
        </div>
        <p>
          To make posting on OpenBuzz even more accessible and attractive to users, every wallet that makes a post is thrown into a 
          lottery drawing and has the opportunity to win the prize pot that is awarded every 100 messages. 
        </p>
        <div>
          <img src="/icons/bingo.png" alt="bingo">
        </div>
        <p>
          All random rolls are made using Chainlink's verifable random number generator for the blockchain.
        </p>
        <div>
          <img src="/chainlink-vrf.png" alt="Chainlink VRF">
        </div>
        <p>
          After reaching 100 messages, the BuzzBoard will be locked to new messages and cleared to make room for the next cycle.
        </p>
    </div>

</main>

<style>

        .fourth-info-container {
          margin: 50px 0px 100px 0px;
          display: grid;
          justify-items: center;
          align-content: center;
        }
  
        .fourth-info-container > p {
          color: white;
          text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
          text-align: center;
          font-size: 20px;
          font-weight: 700;
          max-width: 400px;
          margin: 5px 25px 5px 0px;
        }
  
        .fourth-info-container > div {
          display: flex;
          justify-content: center;
          align-items: center;
          margin: 25px 0px;
          padding: 0px;
        }
  
        .fourth-info-container > div > img {
          width: 80%;
          height: auto;
          border-radius: 5px;
          margin-bottom: 50px;
        }
  
        .fourth-info-container > div:nth-child(2) > img {
          width: 80%;
          height: auto;
          border-radius: 5px;
        }
  
        .fourth-info-container > div:nth-child(6) > img {
          width: 60%;
          height: auto;
          border-radius: 5px;
        }
  
        .fourth-info-container > div:nth-child(8) > img {
          width: 30%;
          height: auto;
          border-radius: 5px;
        }

        @media (min-width: 901px) and (max-width: 1500px) {
            .fourth-info-container > div:nth-child(8) > img {
            width: 40%;
            }
        }

        @media (min-width: 631px) and (max-width: 900px) {
            .fourth-info-container > div:nth-child(8) > img {
                width: 60%;
            }

            .fourth-info-container > p {
                display: grid;
                text-align: center;
                margin: 10px 0px;
            }

        }

        @media (min-width: 451px) and (max-width: 630px) {
            .fourth-info-container > div:nth-child(8) > img {
                width: 80%;
            }

            .fourth-info-container > p {
                display: grid;
                text-align: center;
                margin: 10px 0px;
            }
        }

        @media (min-width: 380px) and (max-width: 450px) {
            .fourth-info-container > div:nth-child(8) > img {
                width: 80%;
            }

            .fourth-info-container > p {
                display: grid;
                text-align: center;
                padding: 0px;
                margin: 10px 0px;
            }

        }

        @media (min-width: 10px) and (max-width: 379px) {
            .fourth-info-container > div:nth-child(8) > img {
                width: 80%;
            }

            .fourth-info-container > p {
                display: grid;
                text-align: center;
                padding: 5px 10px;
                margin: 10px 0px;
            }

        }

</style>