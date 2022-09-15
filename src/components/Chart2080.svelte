<script>

</script>

<main>

    <div class="pie20-80">
        <p>Team Wallet</p>
        <p>20%</p>
        <p>Buy/Burn</p>
        <p>80%</p>
    </div>

</main>

<style>

main {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 50px 0px;
}

.pie20-80 {
  width: 200px; height: 200px;
  border-radius: 50%;
  background-image: conic-gradient(#e3ff67 0deg, #e3ff67 72deg, #ff584d 72deg, #ff584d 360deg);
  border: 2px solid #cccccc
}

p  {
    font-size: 14px;
    font-weight: 700;
    color: white;
    /* text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd; */
    text-shadow: -1px -1px 0 #000000, 1px -1px 0 #000000, -1px 1px 0 #000000, 1px 1px 0 #000000;
}

p:nth-child(1){
    text-align: right;
    margin: 40px 20px 0px 0px;
}

p:nth-child(2){
    text-align: right;
    margin: 5px 40px 0px 0px;
}

p:nth-child(3){
    text-align: center;
    margin: 40px 25px 0px 0px;
}

p:nth-child(4){
    text-align: center;
    margin: 5px 40px 0px 0px;
}




</style>