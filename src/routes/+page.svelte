<script>
    // You don't need to import the font here, you can import it directly in your CSS
    // import 'https://fonts.googleapis.com/css2?family=Jersey+25&display=swap';
</script>

<div class="circle">
    <p id="title">uno</p>
</div>

<style>
    @import url("https://fonts.googleapis.com/css2?family=Jersey+25&display=swap");
    * {
    }
    .circle {
        padding: 150px;
        position: relative;
        margin: auto;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: black;
        height: 300px;
        width: 300px;
        border-radius: 50%;
    }
    #title {
        position: absolute;
        top: 10%;
        left: 33%;
        color: white;
        font-family: "Jersey 25";
        font-weight: bold;
        font-size: 150px;
    }
</style>
