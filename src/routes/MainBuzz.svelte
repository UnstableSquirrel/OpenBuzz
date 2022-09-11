<script>
// @ts-nocheck


  import OpenBuzz from "../contracts/MainABI.json"
  import Footer from "../components/Footer.svelte"
  import Info from "../components/InformationMainPolygon.svelte"
  import { onMount } from 'svelte';

  const ABI = OpenBuzz
  const ADDRESS = "0x7C12aB4fd96C408E650aC71E537f7AcE126E5aCa"
  // const OWNER = "0x02fec424f3E37188Fb3757298Eca61C200D2A99b"
  



  // if (browser) {

  let hasMounted = false

  // @ts-ignore
  window.userAddress = null
  let wallet
 // @ts-ignore
   $: if (wallet != window.userAddress) {
        // @ts-ignore
        wallet = window.userAddress
     }





  let gas
  // $: gas

  $:  change = function changeGas() {
        gas = window.localStorage.setItem("gas", gas + "000000000")
        gas = window.localStorage.getItem("gas").substring(0, window.localStorage.getItem("gas").length - 9)
      }

  $:  if (window.localStorage.getItem("gas") === null || window.localStorage.getItem("gas") === undefined) {
        gas = window.localStorage.setItem("gas", "50000000000")
        gas = window.localStorage.getItem("gas").substring(0, window.localStorage.getItem("gas").length - 9)
      }
  
  $:  if (window.localStorage.getItem("gas") != null || window.localStorage.getItem("gas") != undefined) {
        gas = window.localStorage.getItem("gas").substring(0, window.localStorage.getItem("gas").length - 9)
      }

  let gasModal = "close"
  let chainId





  window.onload = async () => {
    // @ts-ignore
    if (window.ethereum) {
      // @ts-ignore
      window.web3 = new Web3(window.ethereum)
      // @ts-ignore
      chainId = await web3.eth.getChainId()
      // console.log(chainId)
    } else {
      alert("No ETH brower extension detected.")
    }
      // @ts-ignore
      window.userAddress = window.localStorage.getItem("userAddress")
      // @ts-ignore
      wallet = window.userAddress
  }
  hasMounted = true


  function truncateAddress(address) {
    if (!address) {
      return ""
    }
    return `${address.substr(0, 5)}...${address.substr(
      address.length - 5,
      address.length
    )}`
  }

  function logout() {
    // @ts-ignore
    window.userAddress = null
    // @ts-ignore
    wallet = window.userAddress
    window.localStorage.removeItem("userAddress")
  }

  async function loginWithEth() {
    // @ts-ignore
    if (window.web3) {
        try {
          // @ts-ignore
          const selectedAccount = await window.ethereum
            .request({
              method: "eth_requestAccounts",
            })
            .then((accounts) => accounts[0])
            .catch(() => {
              throw Error("No account selected!")
            })
          // @ts-ignore
          window.userAddress = selectedAccount
          // @ts-ignore
          wallet = window.userAddress
          window.localStorage.setItem("userAddress", selectedAccount)
        } catch (error) {
          console.error(error)
        }
      } else {
        alert("No ETH brower extension detected.")
      }
  }





  // $: if (wallet != null) {
  //       getWalletInfo()
  //     }




      
  let Modal = "close"

  let currentPriceMessages
  let currentPriceReactions





  let gasLimitForChar
  let Messages = []
  let newMessage = ""
  let charCount
  $: charCount = Array.from(newMessage).length

  $: if (charCount < 100) {
    gasLimitForChar = 300000
  }

  $: if (charCount >= 100 && charCount <= 500) {
    gasLimitForChar = 700000
  }

  $: if (charCount > 500 && charCount <= 1000) {
    gasLimitForChar = 1500000
  }

  $: if (charCount > 1000) {
    gasLimitForChar = 3000000
  }

  async function getMessages() {
      // @ts-ignore
      const web3 = new Web3(window.ethereum)
      const contract = new web3.eth.Contract(ABI, ADDRESS)
      currentPriceMessages = await contract.methods.priceReaction().call({ from: wallet })
      if(wallet == 0x02fec424f3E37188Fb3757298Eca61C200D2A99b) {
        currentPriceMessages = 0
      }
      currentPriceReactions = await contract.methods.priceReaction().call({ from: wallet })
      if(wallet == 0x02fec424f3E37188Fb3757298Eca61C200D2A99b) {
        currentPriceReactions = 0
      }
      // console.log(currentPriceMessages)
      for (let i = 1; i < 100; i++) {
        const info = await contract.methods.posts(i).call({ from: wallet })
        if (info.adr == "0x0000000000000000000000000000000000000000") {
          return
        }
        else {
          Messages.push({
            "Id": info.id,
            "Address": info.adr,
            "Likes": info.likes,
            "Dislikes": info.dislikes,
            "Message": info.message,
            "Ratio": parseInt(info.likes) - parseInt(info.dislikes),
          })
          // console.log(Messages)
        }
        Messages.sort(function(a, b) {
          return b.Ratio - a.Ratio
        })
        Messages = Messages
        // console.log(Messages)
      }
  }


  // getMessages()

  async function addMessage() {
    // @ts-ignore
    const web3 = new Web3(window.ethereum)
    const contract = new web3.eth.Contract(ABI, ADDRESS)
    const info = await contract.methods.addPost(newMessage).send({ from: wallet , value: (currentPriceMessages), gasPrice : parseInt(window.localStorage.getItem("gas")), gasLimit: gasLimitForChar })
    console.log(newMessage)
    console.log(info)
    newMessage = ""
  }

  // async function deleteAll() {
  //   const web3 = new Web3(window.ethereum)
  //   const contract = new web3.eth.Contract(ABI, ADDRESS)
  //   const info = await contract.methods.restart().send({ from: wallet , gasPrice : parseInt(window.localStorage.getItem("gas")), gasLimit: 3000000 })
  //   console.log(info)
  // }

  // async function whitelist() {
  //   const web3 = new Web3(window.ethereum)
  //   const contract = new web3.eth.Contract(ABI, ADDRESS)
  //   const info = await contract.methods.whitelistSender("0x527a819db1eb0e34426297b03bae11F2f8B3A19E").send({ from: wallet , gasPrice : parseInt(window.localStorage.getItem("gas")), gasLimit: 500000 })
  //   console.log(info)
  // }

  // async function checkWhitelist() {
  //   const web3 = new Web3(window.ethereum)
  //   const contract = new web3.eth.Contract(ABI, ADDRESS)
  //   const info = await contract.methods.whitelisted().call({ from: wallet , gasPrice : parseInt(window.localStorage.getItem("gas")), gasLimit: 500000 })
  //   console.log(info)
  // }




  
  let likeId
  let dislikeId
  async function like() {
    // @ts-ignore
    const web3 = new Web3(window.ethereum)
    const contract = new web3.eth.Contract(ABI, ADDRESS)
    const info = await contract.methods.addLike(likeId).send({ from: wallet , value: (currentPriceReactions), gasPrice : parseInt(window.localStorage.getItem("gas")), gasLimit: 210000 })
    console.log(info)
  }

  async function dislike() {
    // @ts-ignore
    const web3 = new Web3(window.ethereum)
    const contract = new web3.eth.Contract(ABI, ADDRESS)
    const info = await contract.methods.addDislike(dislikeId).send({ from: wallet , value: (currentPriceReactions), gasPrice : parseInt(window.localStorage.getItem("gas")), gasLimit: 210000 })
    console.log(info)
  }

  function getLikeId(i) {
    likeId = i
    // console.log(likeId)
    like()
  }

  function getDislikeId(i) {
    dislikeId = i
    // console.log(dislikeId)
    dislike()
  }

// }

</script>

<main>

  <header>

      <div class="logo-container">
        <div>
          <a href="/"><img src="OpenBuzz.png" alt="OpenBuzz"></a>
        </div>
      </div>

      {#if wallet != null }
      <div class="logout-container">
        <p id="userAddress">{truncateAddress(wallet)}</p>
        <button id="logoutButton" on:click="{logout}">
          Logout
        </button>
        <div class="gas-container">
          <!-- <p>Current Gas: </p> -->
          <p>{gas} Gwei</p>
          <button  on:click="{() => gasModal = "open"}">Set Gas</button>
        </div>
      </div> 
      {/if}
      {#if wallet == null }
      <div class="login-container">
        <button id="loginButton" on:click="{loginWithEth}">
          Login
        </button>
      </div>
      {/if}

  </header>

  <div class="add-message-container">
    <button on:click="{() => Modal = "open"}">Add Message +</button>
  </div>

  <div id="modal-container" class="{"modal " + gasModal}">
    <div class="modal-content">
        <span on:click="{() => gasModal = "close"}" class="close-button">×</span>

        <div class="gas-modal">
          <label for="Amount">New Gas: </label>
          <input style="width: 120px;" type="number" name="gas" on:change="{change}" bind:value="{gas}">
          <button on:click="{() => gasModal = "close"}">good</button>
        </div>

    </div>
  </div>

  <div class="messages-container">

      {#if chainId != 137}
        <h1 style="text-align: center; color: white; font-size: 35px; font-weight: 700; text-shadow: -1px -1px 0 #17314f, 1px -1px 0 #17314f, -1px 1px 0 #17314f, 1px 1px 0 #17314f;">Please connect to the Polygon Network!</h1>
      {/if}

      {#if chainId == 137}
        {#await getMessages()}
          <h1 style="text-align: center; color: white; font-size: 35px; font-weight: 700; text-shadow: -1px -1px 0 #17314f, 1px -1px 0 #17314f, -1px 1px 0 #17314f, 1px 1px 0 #17314f;">Loading ...</h1>
        {:then}

          {#if Messages.length > 0}
          <h1 style="text-align: center; color: white; font-size: 35px; font-weight: 700; text-shadow: -1px -1px 0 #17314f, 1px -1px 0 #17314f, -1px 1px 0 #17314f, 1px 1px 0 #17314f;">{Messages.length}</h1>
          <div style="background-color: white; height: 2px; width: 100%; margin-bottom: 50px; box-shadow: -1px -1px 0 #17314f, 1px -1px 0 #17314f, -1px 1px 0 #17314f, 1px 1px 0 #17314f"></div>
            {#each Messages as message}
            <div class="message">
              <div class="author-address">
                <p>{`${message.Address.substr(0, 5)}...${message.Address.substr(message.Address.length - 5, message.Address.length)}`}</p>
              </div>
              <div class="message-content">
                <p>{message.Message}</p>
              </div>
              <div class="thumbs-container">
                <div class="likes">
                  <label on:click="{() => getLikeId(message.Id)}" for="likes">👍</label>
                  <p>{message.Likes}</p>
                </div>
                <div class="dislikes">
                  <label on:click="{() => getDislikeId(message.Id)}" for="likes">👎</label>
                  <p>{message.Dislikes}</p>
                </div>
              </div>
            </div>
            {/each}
          {/if}
    
          {#if Messages.length == 0}
            <h1 style="text-align: center; color: white; font-size: 35px; font-weight: 700; text-shadow: -1px -1px 0 #17314f, 1px -1px 0 #17314f, -1px 1px 0 #17314f, 1px 1px 0 #17314f;">Share your message with the world!</h1>
          {/if}

        {:catch error}
          <h1 style="
            text-align: center;
            color: white;
            font-size: 35px;
            font-weight: 700;
            text-shadow: rgb(23 49 79) -1px -1px 0px, rgb(23 49 79) 1px -1px 0px, rgb(23 49 79) -1px 1px 0px, rgb(23 49 79) 1px 1px 0px;">Loading Error!
          </h1>
        {/await}
      {/if}

  </div>

  <div id="modal-container" class="{"modal " + Modal}">
    <div class="modal-content">
        <span on:click="{() => Modal = "close"}" class="close-button">×</span>

        <div class="message-modal">
          <label for="Amount">New Message: </label>
          <!-- <input style="width: 100px; height: 100px; border: 1px solid; border-radius: 10px; overflow: hidden;" type="text" name="message" bind:value="{newMessage}"> -->
          <textarea cols="50" rows="5" maxlength='1480' bind:value="{newMessage}" on:change="{newMessage = newMessage}"></textarea>
          <button on:click="{() => Modal = "close"}" on:mousedown="{addMessage}">Submit</button>
          <p style="text-align: center; color: black; font-size: 15px; font-weight: 700; text-shadow: -1px -1px 0 #ffffff, 1px -1px 0 #ffffff, -1px 1px 0 #ffffff, 1px 1px 0 #ffffff;">
            {charCount}/1480
          </p>
        </div>

    </div>
  </div>

    <Info />
    <Footer />

</main>

<style>

      .close {
        display: none;
      }

      .open {
        display: block !important;
      }

      button {
        height:40px;
        width:max-content;
        background:#0094FF;
        text-transform:uppercase;
        color:rgb(245, 245, 245);
        font-weight:700;
        letter-spacing: 1px;
        border: 2.5px solid #D3FBD8;
        font-size: 15px;
        outline:none;
        cursor: pointer;
        border-radius: 10px;
        padding: 0px 10px;
      }

      button {
        transition:all .2s ease-in-out;
      }

      button:hover {
        background:#68c0ff;
        text-shadow:
          (0 0 10px rgba(255,255,255, 1),
          0 0 50px rgba(255, 255, 255, .8),
          0 0 75px rgba(255, 255, 255, .6),
          0 0 76px rgba(255, 255, 255, .4),
          0 0 77px rgba(255, 255, 255, .5),
          0 0 78px rgba(255, 255, 255, .4),);
      }

      .logo-container {
        display: flex;
        justify-content: center;
        margin: 50px 15px;
      }

      .logo-container > div > a > img {
        width: auto;
        height: 50px;
      }

      .login-container {
        display: grid;
        justify-items: center;
        padding-right: 30px;
      }

      .login-container > button {
        margin: 65px 0px 20px 0px;
      }

      .logout-container {
        display: grid;
        justify-items: center;
        padding-right: 30px;
      }

      .logout-container > p {
        margin: 50px 0px 5px 0px;
        color: white;
        font-size: 15px;
        font-weight: 700;
        text-shadow: -1px -1px 0 #17314f, 1px -1px 0 #17314f, -1px 1px 0 #17314f, 1px 1px 0 #17314f;
      }

      .logout-container > button {
        margin: 0px 0px 20px 0px;
      }





      .messages-container {
        display: grid;
        justify-items: center;
        align-items: center;
        background-color: #0095ff;
        border: 5px solid #303A4E;
        padding: 25px;
      }

      .message {
        display: grid;
        justify-items: center;
        align-items: center;
        border: 2.5px solid #303A4E;
        border-radius: 10px;
        background-color: #D3FBD8;
        padding: 5px 10px;
        margin: 10px 0px;
        max-width: 500px;
        /* box-shadow: 2px 2px 15px ghostwhite; */
      }

      .author-address {
        display: flex;
        justify-items: left;
        width: auto;
      }

      .author-address > p {
        font-size: 12px;
        color: rgb(0, 0, 0);
        text-shadow: -1px -1px 0 #e1eefd, 1px -1px 0 #e1eefd, -1px 1px 0 #e1eefd, 1px 1px 0 #e1eefd;
        font-weight: 700;
        text-align: left;
      }

      .message-content {
        overflow: auto;
        background-color: white;
        padding: 0px 15px;
        border-radius: 5px;
        max-width: 90%;
      }

      .message-content > p {
        overflow: auto;
        font-size: 15px;
        color: rgb(0, 0, 0);
        /* text-shadow: -1px -1px 0 #000000, 1px -1px 0 #000000, -1px 1px 0 #000000, 1px 1px 0 #000000; */
        font-weight: 700;
        max-width: 100%;
      }

      .thumbs-container {
        display: flex;
        justify-content: center;
      }

      .likes {
        margin: 0px 15px;
      }

      .dislikes {
        margin: 0px 15px;
      }

      .thumbs-container > .likes > label {
        padding: 5px 5px;
      }

      .thumbs-container > .dislikes > label {
        padding: 5px 5px;
      }

      .thumbs-container > .likes > label:hover {
        cursor: pointer;
        transform: scale(1.4);
        transition: transform 0.1s linear;
      }

      .thumbs-container > .dislikes > label:hover {
        cursor: pointer;
        transform: scale(1.4);
        transition: transform 0.1s linear;
      }

      .likes > p {
        margin: 0px;
        text-align: center;
        font-size: 12px;
        color: rgb(0, 0, 0);
        text-shadow: -1px -1px 0 #ffffff, 1px -1px 0 #ffffff, -1px 1px 0 #ffffff, 1px 1px 0 #ffffff;
        font-weight: 700;
      }

      .dislikes > p {
        margin: 0px;
        text-align: center;
        font-size: 12px;
        color: rgb(0, 0, 0);
        text-shadow: -1px -1px 0 #ffffff, 1px -1px 0 #ffffff, -1px 1px 0 #ffffff, 1px 1px 0 #ffffff;
        font-weight: 700;
      }





      .add-message-container {
        display: flex;
        justify-content: center;
        margin: 50px 0px 50px 0px;
      }

      .add-message-container > button {
        background-color: #6bff6b;
        color: black;
      }

      .add-message-container > button:hover {
        background-color: #bbffbb;
        color: black;
      }

/************** Modal ********************************************************************/

      /* The Modal (background) */
      .modal {
        display: none; /* Hidden by default */
        position: fixed; /* Stay in place */
        z-index: 1; /* Sit on top */
        padding-top: 50px; /* Location of the box */
        left: 0;
        top: 0;
        width: 100%; /* Full width */
        height: 100%; /* Full height */
        overflow: auto; /* Enable scroll if needed */
        background-color: rgb(0,0,0); /* Fallback color */
        background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
      }

      /* Modal Content */
      .modal-content {
        background-color: #75f8dc;
        margin: auto;
        padding: 10px 15px;
        border: 1px solid #888;
        width: 80%;
        height: 80%;
        border-radius: 20px;
      }

      /* The Close Button */
      .close-button {
        color: #000000;
        float: right;
        font-size: 30px;
        font-weight: 700;
        width: 35px;
        height: 33px;
        text-align: center;
        border: 2px solid black;
        background-color: red;
      }

      .close-button:hover,
      .close-button:focus {
        background-color: rgb(223, 0, 0);
        cursor: pointer;
      }

      .message-modal {
        display: grid;
        justify-items: center;
      }

      .message-modal > label {
        display:flex; 
        justify-content: center; 
        text-align:center; 
        font-size:25px; 
        z-index: 5;
        color: black;
        font-weight: 700; 
        text-shadow: -1px -1px 0 #ffffff, 1px -1px 0 #ffffff, -1px 1px 0 #ffffff, 1px 1px 0 #ffffff;
        margin: 120px 0px 0px 0px !important;
      }

      .message-modal > textarea {
        width: 50vw;
        height: 40vh;
        margin: 25px 0px 10px 0px;
      }

/************** Modal ********************************************************************/

      @media (min-width: 150px) and (max-width: 500px) {

        header {
          display: grid;
          justify-content: center;
        }

        .funds-container {
          display: grid !important;
          justify-items: center !important;
          align-items: center !important;
          grid-template-columns: auto auto !important;
          padding: 0px !important;
        }
        .funds-container > div {
          display: grid !important;
          justify-content: center !important;
          align-items: center !important;
          margin: 0px !important;
          /* grid-template-columns: auto auto; */
        }

        .login-container {
          padding: 0px;
        }

        .logout-container {
          padding: 0px;
        }
      }

      .gas-container {
        display: grid;
        justify-items: center;
        margin: 0px;
        padding: 0px;
      }

      .gas-container > p {
        margin: 5px 0px;
        padding: 0px;
        color: white;
        font-size: 15px;
        font-weight: 700;
        text-shadow: -1px -1px 0 #17314f, 1px -1px 0 #17314f, -1px 1px 0 #17314f, 1px 1px 0 #17314f;
      }

      /************** Modal ********************************************************************/

      /* The Modal (background) */
      .modal {
        display: none; /* Hidden by default */
        position: fixed; /* Stay in place */
        z-index: 1; /* Sit on top */
        padding-top: 50px; /* Location of the box */
        left: 0;
        top: 0;
        width: 100%; /* Full width */
        height: 100%; /* Full height */
        overflow: auto; /* Enable scroll if needed */
        background-color: rgb(0,0,0); /* Fallback color */
        background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
      }

      /* Modal Content */
      .modal-content {
        background-color: #75f8dc;
        margin: auto;
        padding: 10px 15px;
        border: 1px solid #888;
        width: 80%;
        border-radius: 20px;
      }

      /* The Close Button */
      .close-button {
        color: #000000;
        float: right;
        font-size: 30px;
        font-weight: 700;
        width: 35px;
        height: 33px;
        text-align: center;
        border: 2px solid black;
        background-color: red;
      }

      .close-button:hover,
      .close-button:focus {
        background-color: rgb(223, 0, 0);
        cursor: pointer;
      }

      .gas-modal {
        display: grid;
        justify-items: center;
      }

      .gas-modal > label {
        margin: 200px 0px 0px 0px !important;
        display:flex; 
        justify-content: center; 
        text-align:center; 
        padding:0px !important; 
        font-size:25px;
      }

      .gas-modal > input {
        margin-top: 10px;
      }

/************** Modal ********************************************************************/

</style>
