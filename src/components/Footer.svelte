<script>

    ////////////// Links /////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

    function link() {
        window.location.href = "";
      }

    ////////////// Links End /////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

    ////////////// Copy To Clipboard End ////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

    let wallet = "0x0BA88e510D7683EAB79cb023a55D8AE21D7593DA"

    /*function copy() {
    navigator.clipboard.writeText(wallet)
    alert("Address Copied")
    }*/

    function copy() {
        const elem = document.createElement('textarea')
        elem.value = wallet
        document.body.appendChild(elem)
        elem.select()
        document.execCommand('copy')
        document.body.removeChild(elem)
        alert("Address Copied")
    }

////////////// Copy To Clipboard End ////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

</script>

<main>

    <footer>
      <div class="links-section">
        <a href="https://t.me/OpenBuzz"><img src="telegram.png" alt="Telegram"></a>
        <a href="https://twitter.com/TheOpenBuzz?t=3S5nPSKapUvST64N99HVew&s=09"><img src="twitter.png" alt="Twitter"></a>
      </div>
      <div class="donation-section">
        <div>
          <p>Team Wallet for Donations: </p>
          <div>
            <span on:click="{copy}" class="HeaderInfo_addressText__2x_sD">{wallet}</span>
              <div on:click="{copy}" class="HeaderInfo_copyIcon__21b8W">
                <svg width="20px" height="20px" viewBox="0 0 20 20" style="cursor: pointer; color: var(--bg-default-color);">
                  <g id="copy" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
                    <circle id="Oval" fill="currentColor" cx="10" cy="10" r="10"></circle>
                    <g id="Group-13" transform="translate(5.794476, 5.790468)" stroke="#616B84">
                      <path d="M3.5978014,6.21230639e-14 L6.00483293,6.21230639e-14 C6.24961697,6.2522187e-14 6.48589921,0.0897832911 6.66891449,0.252339862 L7.72628545,1.19151064 C7.93994388,1.38128488 8.06220389,1.65340132 8.06220389,1.93917078 L8.06220389,5.79807571 C8.06220389,6.35036046 7.61448864,6.79807571 7.06220389,6.79807571 L3.5978014,6.79807571 C3.04551665,6.79807571 2.5978014,6.35036046 2.5978014,5.79807571 L2.5978014,1 C2.5978014,0.44771525 3.04551665,6.22245169e-14 3.5978014,6.21230639e-14 Z" id="Rectangle"></path><path d="M5.46440249,7.1136292 L5.46440249,7.1136292 L5.46440249,7.70730424 C5.46440249,8.31088547 4.97510322,8.80018474 4.37152199,8.80018474 L1.0928805,8.80018474 C0.489299265,8.80018474 0,8.31088547 0,7.70730424 L0,3.09498952 C0,2.49140829 0.489299265,2.00210903 1.0928805,2.00210903 L2.34654139,2.00210903 L2.34654139,2.00210903" id="Path">
                      </path>
                      <path d="M5.61108423,0 L5.61108423,1.84318671 C5.61108423,2.06410061 5.79017033,2.24318671 6.01108423,2.24318671 L8.06220389,2.24318671 L8.06220389,2.24318671" id="Path-2">
                      </path>
                    </g>
                  </g>
                </svg>
              </div>
          </div>
          <p class="wallet-info">ERC20 and all EVM compatible chains (Polygon, AVAX, BSC)</p>
        </div>
      </div>
      <div>
        <p style="color: white; font-size: 10px; font-weight: 500;">Copyright © 2022 – OpenBuzz</p>
      </div>
    </footer>

</main>

<style>


/*----------- Donation Area ------------------------------------------------------------------*/

span {
  color: rgb(192, 98, 255);
  font-weight: 700;
  font-size: 17px;
}

.donation-section > div {
  display: grid;
	align-items: center;
	margin-bottom: 10px;
	font-size: 15px;
	color: white;
  justify-items: center;
  text-shadow: -1px 0 #17314f, 1px -1px 0 #17314f, -1px 1px 0 #17314f, 1px 1px 0 #17314f;
}

.donation-section > div > p {
  color: white;
  text-shadow: -1px 0 #17314f, 1px -1px 0 #17314f, -1px 1px 0 #17314f, 1px 1px 0 #17314f;
}

.donation-section > div > div {
  display: flex;
  justify-content: center;
  align-items: center;
}

.HeaderInfo_addressText__2x_sD {
  font-size: 15px;
  margin: 0px 10px 0px 0px;
  color: hsl(0, 0%, 100%);
  text-shadow: -1px 0 #17314f, 1px -1px 0 #17314f, -1px 1px 0 #17314f, 1px 1px 0 #17314f;
}

.HeaderInfo_copyIcon__21b8W {
  margin: 2px 0px 0px 0px;
}

.HeaderInfo_copyIcon__21b8W:hover {
  transform: scale(1.05);
  color: hsl(195, 25%, 77%);
}

.wallet-info {
  align-items: center;
  font-size: 10px;
  font-weight: 400;
  color: lightblue;
  text-shadow: none !important;
}

@media (max-width: 355px) {

  .donation-section > div {
    text-align: center;
    padding: 10px;
    font-size: 12px;
  }

  .HeaderInfo_addressText__2x_sD {
    font-size: 12px;
    margin: 0px 10px 0px 0px;
  }

  .wallet-info {
    font-size: 8px;
  }
}

/*----------- Donation Area End ------------------------------------------------------------------*/

footer {
  display: grid;
  justify-content: center;
  background-color: #000000;
  text-align: center;
  padding: 25px;
}

.links-section > a > img:nth-child(1) {
  width: 35px;
  height: 35px;
  border-radius: 5px;
  margin: 25px 10px 25px 0px;
}

.links-section > a > img:nth-child(2) {
  width: 35px;
  height: 35px;
  border-radius: 5px;
  margin: 25px 0px 25px 10px;
}

.links-section > a > img:hover {
  cursor: pointer;
  transform: scale(1.2);
  transition: transform 0.1s linear;
}

@media (min-width: 100px) and (max-width: 299px) {

  footer {
    padding: 10px 0px;
  }

  .HeaderInfo_addressText__2x_sD {
      font-size: 9px;
  }
}

@media (min-width: 300px) and (max-width: 500px) {

    footer {
      text-align: center;
      padding: 11px;
    }

    .HeaderInfo_addressText__2x_sD {
      font-size: 10px;
    }

}

</style>