<script>
    import Footer from "../components/Footer.svelte"
    import Form from "../components/Form.svelte"
    import Infocards from "../components/Infocards.svelte"
    import Newest from "../components/Newest.svelte"
    import Ticket from "../components/Ticket.svelte"

</script>
  
  <main>
  
    <header>
  
      <div class="menu-container">
        <div>
          <a href="/#Contact"><p>Contact</p></a>
        </div>
        <div>
          <a href="/#BuzzBoards"><p>BuzzBoards</p></a>
        </div>
      </div>
  
      <div class="main-board">
        <a href="#/MainBuzzBoard">
          <button>Main BuzzBoard</button>
        </a>
      </div>
  
    </header>
  
    <section class="section-1">
  
      <div class="logo-container">
        <img src="OpenBuzz Logo.png" alt="OpenBuzz">
      </div>
  
      <div>
        <h1>
          A DECENTRALIZED MESSAGE BOARD FOR YOUR COMMUNITY
        </h1>
      </div>
  
    </section>
  
    <section class="section-2">
      <div class="info-card-container">
        <div class="info-card">
          <img src="/icons/chat.png" alt="Chat Board">
          <p>Post your message freely on the board</p>
          <p>
            OpenBuzz is fully decentralized and censorless. 
            Every BuzzBoard is dedicated to a community where you can engage and interact by posting, 
            liking or disliking messages from other users.
          </p>
        </div>
        <div class="info-card">
          <img src="/icons/metabolism.png" alt="Burn Tokens">
          <p>Burn tokens with each message</p>
          <p>
            Each message on OpenBuzz costs a fee which is used to buy and burn designated tokens.
            With this mechanism, projects can increase their liquidity and simultaneously decrease their supply.
          </p>
        </div>
        <div class="info-card">
          <img src="/icons/lottery.png" alt="Ticket">
          <p>Each message is also a prize pool ticket</p>
          <p>
            As an additional incentive for users to post messages, each message id on the board is added into a Chainlink VRF roll
            and can win the current pool prize, which gets distributed after every cycle. 
          </p>
        </div>
        <div class="info-card">
          <img src="/icons/winner.png" alt="Rating Pot">
          <p>One winner is selected on every cycle</p>
          <p>
            A cycle is over when 100 messages are posted. The board is then reset to accept new posts. Users can win
            a prize pool every cycle, the more messages they type, the more tickets they get.
          </p>
        </div>
      </div>
  
      <div class="second-info-container">
        <p>Help your project while having fun</p>
        <p>
          With each message you post on a token's BuzzBoard, OpenBuzz auto buys and burns that designated token, 
          therefore decreases the total supply while also increasing the liquidity backing of it.
        </p>
      </div>
      
      <Newest/>
  
    </section>
  
    <section class="section-3">

        
      <div class="third-info-container">
        <p>
          Simple Mechanisms
        </p>
        <p>
          OpenBuzz gives your community the opportunity to burn tokens and get rewarded when doing it.
        </p>
      </div>

      <Infocards/>
  
    </section>
  
    <section id="BuzzBoards" class="section-4">
  
      <div>
        <h1 style="font-size: 30px; margin: 25px 0px 25px 0px;">Check out our BuzzBoards</h1>
      </div>

      <p>
        BuzzBoards are message boards that are individually created for tokens with the lottery and burn mechanism. 
      </p>
      <p>
        Select your favorite BuzzBoard, post messages, burn tokens, and win price pools in the process.
      </p>
  
      <div class="buzzboard-container">
  
        <div>
          <h1>BuzzBoards</h1>
  
          <div>
            <a href="#/OpenBuzzDogira">
              <div class="buzzboard">
                <img src="tokens/dogira.png" alt="Dogira">
                <p>Dogira</p>
                <img src="/networks/polygon.png" alt="Polygon">
              </div>
            </a>
<!-- 
            <a href="#/OpenBuzzDogira">
              <div class="buzzboard">
                <img src="tokens/polydoge.png" alt="Polydoge">
                <p>Polydoge</p>
                <img src="/networks/polygon.png" alt="Polygon">
              </div>
            </a>

            <a href="#/OpenBuzzDogira">
              <div class="buzzboard">
                <img src="tokens/rubic.png" alt="Rubic">
                <p>Rubic</p>
                <img src="/networks/polygon.png" alt="Polygon">
              </div>
            </a> -->
  
        </div>
  
      </div>
  
    </section>
  
    <section id="Contact" class="section-5">
  
      <div>
        <h1 style="font-size: 30px;">
          Create a BuzzBoard for your token
        </h1>
        <br>
        <p>
          Reach out to us and let's make a BuzzBoard for your project! Each BuzzBoard is customizable and
          can reward different prizes, adjust prize-per-message, change Buzz-and-Burn rates, and more!
        </p>
        <Form/>
        <p>
          Once your application is approved, we will create a custom contract based on your input, deploy it and integrate it with our frontend.
        </p>
        <div>
          <p><span>E-Mail:</span> Your or your project's email address.</p>
          <p><span>Project Name:</span> The name of your project.</p>
          <p><span>Network:</span> The network your project is running on, you want us to deploy a BuzzBoard for it.</p>
          <p><span>Contract Address:</span> The contract address of your project.</p>
          <p><span>Swap Protocol:</span> The swap protocol you want us to use to buy and burn your project's tokens.</p>
        </div>
        <p>After reviewing your application, we'll contact you about a potential listing.</p>
      </div>
  
    </section>

    <Ticket/>
  
    <!-- <section class="section-6">
      <div>
        <h1>Section 6</h1>
      </div>
    </section>
  
    <section class="section-7">
      <div>
        <h1>Section 7</h1>
      </div>
    </section> -->
  
  
    <!-- <Main/> -->
  
    <Footer />
  
  </main>
  
  <style>

        a {
          text-decoration: none;
        } 
        
        a:visited {
          color:none;
        }
  
        p {
          text-align: center;
          font-size: 18px;
          font-weight: 700;
          color: white;
          /* text-shadow: -1px -1px 0 #e1eefd, 1px -1px 0 #e1eefd, -1px 1px 0 #e1eefd, 1px 1px 0 #e1eefd; */
          text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
          max-width: 500px;
        }
  
        header {
          display: flex;
          flex-direction: row;
          /* background-color: #0B1336; */
          /* padding: 25px; */
          background: linear-gradient(90deg, #0094FD 0%, #0094FD 20%, #00D2EA 40%, #00E7B9 60%, #93F489 80%, #F9F871 100%);
        }
  
        .menu-container {
          display: flex;
          justify-content: center;
          align-items: center;
          margin: 10px 15px;
        }
  
        .menu-container > div {
          margin: 0px 10px 0px 0px;
        }

        .menu-container > div > a > p {
          transition: all 0.2s;
        }

        .menu-container > div > a > p:hover {
          transition: all 0.1s;
          color: #F9F871;
        }
  
        .main-board {
          margin: 20px 20px 0px 0px;
        }
  
        .main-board > a > button {
          border-radius: 5px;
          border: 2px solid #22222a;
          background-color: #0094fd;
          font-size: 17px;
          font-weight: 700;
          color: white;
          text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
        }

        .main-board > a > button {
          text-decoration: none;
          color: white;
          text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
        } 
  
        .main-board > a > button:hover {
          cursor: pointer;
          background-color: #4fb6ff;
          transform: scale(1.01);
        }
  
        .main-board > a > button:active {
          cursor: pointer;
          background-color: #0094fd;
          transform: scale(0.99);
        }
  
        .logo-container {
          display: flex;
          justify-content: center;
          align-items: center;
          margin: 10px auto 10px auto;
        }
  
        .logo-container > img {
          width: auto;
          height: 120px;
        }
  
        .section-1 {
          display: grid;
          justify-items: center;
          align-items: center;
          padding: 30px 0px 170px 0px;
          background: linear-gradient(90deg, #0094FD 0%, #0094FD 20%, #00D2EA 40%, #00E7B9 60%, #93F489 80%, #F9F871 100%);
        }
  
        .section-1 > div > h1 {
          text-align: left;
          font-size: 20px;
          font-weight: 700;
          color: white;
          /* text-shadow: -1px -1px 0 #e1eefd, 1px -1px 0 #e1eefd, -1px 1px 0 #e1eefd, 1px 1px 0 #e1eefd; */
          text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
          max-width: 330px;
        }
  
        .section-2 {
          display: grid;
          justify-items: center;
          align-content: center;
          padding: 5px;
          /* background-color: #A4ABBD; */
          background-color: #ffffff;
        }
  
        .info-card-container {
          display: grid;
          justify-items: center;
          grid-template-columns: auto auto auto auto;
          grid-gap: 0px;
          margin-top: -130px;
          background-color: #ffffff;
          border-radius: 5px 5px 0px 0px;
          padding-bottom: 25px;
          border-bottom: 2px solid black;
        }
  
        .info-card {
          /* background-color: #E6F4F1;
          border: 2px solid #F4F9FF; */
          max-width: 200px;
          padding: 5px 10px;
          display: grid;
          justify-items: left;
          margin-top: 25px;
        }
  
        .info-card:nth-child(2) {
          margin-top: 20px;
        }
  
        .info-card:nth-child(4) {
          margin-top: 18px;
        }
  
        .info-card > img {
          width: auto;
          height: 38px;
        }
  
        .info-card:nth-child(2) > img {
          width: auto;
          height: 43px;
        }
  
        .info-card:nth-child(3) > img {
          width: auto;
          height: 35px;
        }
  
        .info-card:nth-child(4) > img {
          width: auto;
          height: 43px;
        }
  
        .info-card > p {
          text-shadow: none;
          text-align: left;
          font-size: 16px;
          font-weight: 700;
          max-width: 500px;
          margin: 10px 0px 0px 0px;
        }
  
        .info-card-container > div:nth-child(1) > p:nth-child(2) {
          color: #009dfa;
        }
  
        .info-card-container > div:nth-child(2) > p:nth-child(2) {
          color: #00d1ea;
        }
  
        .info-card-container > div:nth-child(3) > p:nth-child(2) {
          color: #00e5bd;
        }
  
        .info-card-container > div:nth-child(4) > p:nth-child(2) {
          color: #54ee9d;
        }
  
        .info-card > p:nth-child(3) {
          text-shadow: none;
          color: #8d8d8d ;
          text-align: left;
          font-size: 14px;
          font-weight: 500;
          max-width: 500px;
          margin: 30px 0px 0px 0px;
        }
  
        .second-info-container {
          margin: 50px 0px;
          display: inline-flex;
          flex-wrap: wrap;
          justify-content: left;
        }
  
        .second-info-container > p {
          text-shadow: none;
          color: #0094fd;
          text-align: left;
          font-size: 20px;
          font-weight: 700;
          max-width: 430px;
          margin: 5px 25px 5px 0px;
        }
  
        .second-info-container > p:nth-child(2) {
          text-shadow: none;
          color: #8d8d8d;
          text-align: left;
          font-size: 14px;
          font-weight: 500;
          margin: 5px 0px 5px 25px;
        }
  
        .third-info-container {
          margin: 10px 0px 100px 0px;
          display: grid;
          justify-items: center;
          align-content: center;
        }
  
        .third-info-container > p:nth-child(1) {
          text-shadow: none;
          color: white;
          text-align: left;
          font-size: 30px;
          font-weight: 700;
          max-width: 700px;
          margin: 25px 0px;
          text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
        }
  
        .third-info-container > p:nth-child(2) {
          text-shadow: none;
          color: white;
          text-align: left;
          font-size: 20px;
          font-weight: 700;
          max-width: 700px;
          margin: 5px 0px;
          text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
        }
  
        .section-3 {
          display: grid;
          justify-items: center;
          align-content: center;
          padding: 100px 0px;
          /* background-color: #A4ABBD; */
          background-color: #00B7FF;
        }
  
        .section-4 {
          display: grid;
          justify-items: center;
          align-content: center;
          /* background-color: #A4ABBD; */
          background-color: #00D2EA;
          padding: 100px 0px 100px 0px;
        }

        .section-4 > p {
          padding: 5px 25px;
        }
  
        .section-4 > div > h1 {
          color: white;
          /* text-shadow: -1px -1px 0 #e1eefd, 1px -1px 0 #e1eefd, -1px 1px 0 #e1eefd, 1px 1px 0 #e1eefd; */
          text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
          text-align: center;
          margin: 25px 0px 75px 0px;
        }
  
        .buzzboard-container {
          background-color: white;
          border: 1px solid black;
          border-radius: 15px 15px 0px 0px;
          /* width: 250px; */
          height: auto;
          margin-top: 50px;
        }
  
        .buzzboard-container > div > h1 {
          display: grid;
          justify-items: center;
          align-content: center;
          padding: 5px 10px;
          margin: -1px;
          color: white;
          border: 1px solid black;
          border-radius: 15px 15px 0px 0px;
          font-size: 45px;
          --start: -20%;
          height: 100px;
          background-image: repeating-radial-gradient(circle at var(--start), transparent 0%, transparent 10%, rgba(54, 89, 219, 0.33) 10%, rgba(54, 89, 219, 0.33) 17%), linear-gradient(to right, #5b7cfa, #3659db);
          color: #fff;
          position: relative;
          overflow: hidden;
        }
  
        .buzzboard-container > div > div {
          padding: 0px 5px;
          margin: 0px;
        }
  
        .buzzboard-container > div > div > a > div {
          justify-items: center;
          flex-wrap: wrap;
          margin: 10px 0px;
  
          display: grid;
          grid-template-columns: 1fr 3fr 1fr;
          align-items: center;
          padding: 10px 5px;
          overflow: hidden;
          border-radius: 10px;
          box-shadow: 0 5px 7px -1px rgb(51 51 51 / 20%);
          cursor: pointer;
          transition: transform 0.25s cubic-bezier(0.7, 0.98, 0.86, 0.98), box-shadow 0.25s cubic-bezier(0.7, 0.98, 0.86, 0.98);
          background-color: #fff;
        }
  
        .buzzboard-container > div > div > a > div:hover {
          transform: scale(1.02)
        }
  
        .buzzboard-container > div > div > a > div > p {
          padding: 5px 10px;
          margin: 0px;
        }
  
        .buzzboard-container > div > div > a > div > img {
          max-width: 100%;
          width: 75px;
          border-radius: 50%;
          box-shadow: 0 0 0 10px #ebeef3, 0 0 0 22px #f3f4f6;
        }
  
        .buzzboard-container > div > div > a > div > img:nth-child(3) {
          max-width: 100%;
          width: 55px;
          box-shadow: none;
        }
  
        .section-5 {
          display: grid;
          justify-items: center;
          align-content: center;
          padding: 100px 0px 100px 0px;
          /* background-color: #A4ABBD; */
          background-color: #00E7B9;
        }
  
        .section-5 > div > h1 {
          color: white;
          /* text-shadow: -1px -1px 0 #e1eefd, 1px -1px 0 #e1eefd, -1px 1px 0 #e1eefd, 1px 1px 0 #e1eefd; */
          text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
          text-align: center;
        }
  
        .section-5 > div {
          display: grid;
          justify-items: center;
          padding: 0px 10px;
        }

        .section-5 > div > p {
          padding: 0px 25px;
          text-align: center;
          text-shadow: 1px 1px 5px black;
        }

        .section-5 > div > div {
          display: grid;
          justify-items: left;
          padding: 5px 15px;
          margin: 50px 0px;
          /* background-color: #ffffffd5;
          border-radius: 5px;
          border: 2px solid white;
          padding: 5px 10px; */
        }
  
        .section-5 > div > div > p {
          font-size: 15px;
          max-width: 350px;
          /* color: #003458; */
          color: rgb(255, 255, 255);
          /* text-shadow: -1px -1px 0 #e1eefd, 1px -1px 0 #e1eefd, -1px 1px 0 #e1eefd, 1px 1px 0 #e1eefd; */
          /* text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;  */
          text-shadow: 1px 1px 5px black;
          text-align: left;
        }
  
        .section-5 > div > div > p > span {
          font-size: 15px;
          color: rgb(0, 0, 0);
          text-shadow: -1px -1px 0 #e1eefd, 1px -1px 0 #e1eefd, -1px 1px 0 #e1eefd, 1px 1px 0 #e1eefd;
          /* text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd; */
          text-align: left;
        }
  
        /* .section-6 {
          display: grid;
          justify-items: center;
          align-content: center;
          padding: 5px;
          background-color: #93F489;
        }
  
        .section-7 {
          display: grid;
          justify-items: center;
          align-content: center;
          padding: 5px;
          background-color: #F9F871;
        } */
  
        @media (min-width: 631px) and (max-width: 900px) {
          header {
            display: grid;
            justify-content: center;
          }
  
          .main-board {
            display: grid;
            justify-items: center;
            margin: 25px 0px;
          }
  
          .section-2 {
            height: 1100px;
          }
  
          .info-card-container {
            grid-template-columns: auto auto auto;
            margin-top: 0px;
          }
  
          .second-info-container {
            justify-content: center;
          }
          
          .third-info-container {
            padding: 5px 10px;
            text-align: center;
          }
  
          .third-info-container > p {
            text-align: center !important;
          }

        }
        
        @media (min-width: 451px) and (max-width: 630px) {
          header {
            display: grid;
            justify-content: center;
          }
  
          .main-board {
            display: grid;
            justify-items: center;
            margin: 25px 0px;
          }
  
          .section-2 {
            height: 1100px;
          }
  
          .info-card-container {
            grid-template-columns: auto auto;
            margin-top: 0px;
          }
  
          .second-info-container {
            justify-content: center;
          }
  
          .third-info-container {
            padding: 5px 10px;
            text-align: center;
          }
  
          .third-info-container > p {
            text-align: center !important;
          }
        }
  
        @media (min-width: 380px) and (max-width: 450px) {
          header {
            display: grid;
            justify-content: center;
          }
  
          .main-board {
            display: grid;
            justify-items: center;
            margin: 25px 0px;
          }
  
          .section-2 {
            height: 1700px;
          }
  
          .info-card-container {
            grid-template-columns: auto;
            margin-top: 0px;
          }
  
          .second-info-container {
            justify-content: center;
          }
  
          .third-info-container {
            padding: 5px 10px;
            text-align: center;
          }
  
          .third-info-container > p {
            text-align: center !important;
          }
        }
  
        @media (min-width: 10px) and (max-width: 379px) {
  
          header {
            display: grid;
            justify-content: center;
          }
  
          .main-board {
            display: grid;
            justify-items: center;
            margin: 25px 0px;
          }
  
          .section-1 > div > h1 {
            text-align: center;
          }
  
          .section-2 {
            height: 1750px;
          }
  
          .info-card-container {
            grid-template-columns: auto;
            margin-top: 0px;
          }
  
          .second-info-container {
            justify-content: center;
          }
  
          .second-info-container > p {
            margin: 0px;
            padding: 0px;
            text-align: center;
          }
  
          .third-info-container {
            padding: 5px 10px;
            text-align: center;
          }
  
          .third-info-container > p:nth-child(1) {
            text-align: center !important;
          }
  
          .third-info-container > p {
            text-align: center !important;
          }
  
          .buzzboard-container {
            width: 250px;
          }
  
          .buzzboard-container > div > h1 {
            font-size: 35px;
          }
  
        }
  
  </style>
  