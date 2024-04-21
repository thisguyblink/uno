<script>
    import Page from "$lib/backround.svelte";
    let search_term = "";
    let name = "";
</script>

<div class="back">
    <div class="searchBar">
        <p id="bio">Biography Search</p>
        <p id="autofill">Looking for {search_term || "something random"}!</p>
        <input id="searchIn" bind:value={search_term} placeholder="explore!!" />
        <button id="search">Search</button>
    </div>
    <div class="pics">
        <img id="person1" src="/assets/download-1.jpg" alt="" />
        <img id="person2" src="/assets/download-2.jpg" alt="" />
        <img id="person3" src="/assets/download-3.jpg" alt="" />
        <img id="person4" src="/assets/download-4.jpg" alt="" />
        <img id="person5" src="/assets/download-5.jpg" alt="" />
        <img id="person6" src="/assets/download-6.jpg" alt="" />
        <img id="person7" src="/assets/download-7.jpg" alt="" />
        <img id="person8" src="/assets/download-8.jpg" alt="" />
        <img id="person9" src="/assets/download-9.jpg" alt="" />
        <img id="person10" src="/assets/download-10.jpg" alt="" />
        <img id="person11" src="/assets/download-11.jpg" alt="" />
        <img id="person12" src="/assets/download-12.jpg" alt="" />
    </div>
</div>

<style>
    @import url("https://fonts.googleapis.com/css2?family=Jersey+25&display=swap");
    * {
        font-family: "Jersey 25";
    }
    .searchBar {
        margin-top: 100px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        z-index: 5;
    }
    #bio {
        margin-bottom: -10px;
        font-size: 45px;
        font-weight: bold;
    }
    #searchIn {
        width: 220px;
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 15px;
        outline: none;
        font-size: 26px;
        color: white;
        font-weight: bold;
        background-color: black;
    }
    #autofill {
        font-size: 25px;
        font-weight: bold;
    }
    #search {
        padding: 10px 20px;
        color: white;
        border-radius: 15px;
        cursor: pointer;
        font-size: 20px;
        text-align: center;
        margin-top: 15px;
        background-color: black;
        font-weight: bold;
    }

    /* Hover effect */
    #search:hover {
        color: black;
        background-color: white;
        box-shadow: inset 0 0 0 3px black;
    }

    .pics {
        z-index: -1;
        filter: saturate(0);
        display: flex;
        flex-wrap: wrap;
        position: absolute;
        left: -10%;
        top: -30%;
        flex-grow: 1;
        filter: blur(8px);
    }
    .pics img {
        flex-grow: 1;
        filter: blur(5px);
        margin: 10px;
        filter: saturate(0);
    }

    .pics img:hover {
        filter: saturate(100%);
    }
    .back {
        position: relative;
    }
</style>
