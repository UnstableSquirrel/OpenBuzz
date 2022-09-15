<script>

</script>

<main>

    <div class="ticket-container">
        <div class="ticket">
            <h1>Ticket</h1>
            <h2>#77</h2>
        </div>
    </div>

</main>

<style>

    main {
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 50px 0px;
    }

    .ticket-container {
        background-image: linear-gradient(45deg, transparent 75%, #0094FD 75%), linear-gradient(135deg, transparent 75%, #00D2EA 75%), linear-gradient(-45deg, transparent 75%, #00E7B9 75%), linear-gradient(-135deg, transparent 75%, #93F489 75%);
        background-color: #F9F871 ;
        /* border: 1px solid white; */
        width: 150px;
        height: 60px;
        padding: 5px;
    }

    .ticket {
        border: 2px dashed #c903ae;
        margin: -45px 5px 0px 5px;
        padding: 5px;
    }

    .ticket > h1 {
        text-align: center;
        font-size: 18px;
        font-weight: 700;
        color: white;
        text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
        margin: 0px 0px 0px 0px;
        padding: 5px 0px 0px 0px;
    }

    .ticket > h2 {
        text-align: center;
        font-size: 15px;
        font-weight: 700;
        color: white;
        text-shadow: -1px -1px 0 #0094fd, 1px -1px 0 #0094fd, -1px 1px 0 #0094fd, 1px 1px 0 #0094fd;
        margin: 0px;
        padding: 0px;
    }

    .ticket-container::before {
        content: '';
        padding: 5px 55px 19px 137px;
        margin: 0px 0px 0px -21px;
        background-size: 15px 10px;
        background-repeat: repeat-y;
        background-position: 0 0, 0 0, 100% 0, 100% 0;
        background-image: linear-gradient(45deg, transparent 75%, #0094FD 75%), linear-gradient(135deg, transparent 75%, #00D2EA 75%), linear-gradient(-45deg, transparent 75%, #00E7B9 75%), linear-gradient(-135deg, transparent 75%, #93F489 75%);
        font-size: 41px;
        text-align: center;
    }

</style>