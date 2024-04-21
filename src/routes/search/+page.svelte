<script>
    import Page from "$lib/backround.svelte";
    let search_term = "";
    let name = "";
</script>

<div>
    <div class="searchBar">
        <p id="bio">Biography Search</p>
        <p id="autofill">Looking for {search_term || "something random"}!</p>
        <input id="searchIn" bind:value={search_term} placeholder="explore!!" />
        <button id="search">Search</button>
    </div>
    <div class="pics"></div>
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
        z-index: 1;
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
        border-radius: 5px;
        outline: none;
        font-size: 26px;
        color: white;
        font-weight: bold;
        background-color: black;
    }
    #autofill {
        font-size: 25px;
    }

    #search {
        margin-top: 15px;
    }
</style>
