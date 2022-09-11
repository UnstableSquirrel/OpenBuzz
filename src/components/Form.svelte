<script>

//import { prevent_default } from "svelte/internal";


</script>










<main>

  <div class="container">
    <h2>Your Project Informations</h2>
    <form action="" method="POST">
        <input type="email" name="E-Mail" id="email" placeholder="E-Mail" required>
        <input type="text" name="Name" id="name" placeholder="Project Name" required>
        <input type="text" name="Chain" id="chain" placeholder="Network" required>
        <input type="text" name="Contract" id="contract" placeholder="Contract Address" required>
        <input type="text" name="Swap" id="swap" placeholder="Swap Protocol" required>
        <textarea name="Project Info" id="message" cols="35" rows="10" placeholder="Project Information"></textarea>
        <input type="submit" value="Send">
    <!--<input type="hidden" name="_next" value="https://yourdomain.co/thanks.html">-->
    </form>
  </div>

</main>










<style>

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: "Poppins",sans-serif;
    }

    main {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        min-height: 70vh;
        width: 100%;
        /*background: radial-gradient(#777,#1C1D25);*/
        transform: scale(0.95);
    }

    h2 {
      font-size: 30px;
      padding: 20px;
      text-align: center;
    }

    .container {
        margin: 50px 0px;
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 500px;
        padding: 5px;
        border-radius: 15px;
        /* border: 3px solid #F9F871; */
        box-shadow: 0 0 15px rgb(122, 122, 122);
        background-color: white;
        /* background-color: gray; */
    }

    form {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 90%;
    }

    input {
        width: 100%;
        margin: 10px 0px;
        height: 35px;
        font-size: 17px;
        text-align: center;
        padding: 10px;
        outline: none;
        border-radius: 15px;
        border: none;
        background: rgb(235, 228, 228);
    }

    textarea {
        width: 100%;
        margin: 20px 0px;
        padding: 10px 20px;
        font-size: 17px;
        text-align: center;
        outline: none;
        border-radius: 15px;
        border: none;
        background: rgb(235, 228, 228);
    }

    input[type=submit] {
        margin: 12px;
        width: 120px;
        height: 50px;
        padding-bottom: 10px;
        background: #00D2EA;
        color: rgb(255, 255, 255);
        cursor: pointer;
    }

    @keyframes change {
      from {background: #00E7B9;}
      to {background: #00E7B9;}
    }

    input[type=submit]:hover {
        /*background: #d6b18c;*/
        background: #00E7B9;
        transform: rotate(2deg);
        transition: ease 0.4s;
        transform: change;
    }

    @media screen and (max-width:600px) {
        .container{
            width: 90%;
        }
    }

</style>