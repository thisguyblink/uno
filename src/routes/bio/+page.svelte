<script>
    import Page from "$lib/backround.svelte";
    import { search_term } from "$lib/store";
    import people from "./people.json"; // Import your JSON file
    // import { ChatSession } from "@google/generative-ai";
    // import {GoogleGenerativeAI} from '@google/generative-ai';
    // const api_key = "AIzaSyApg5WAot5CSD02dv5GXxgBRpxkxYJO2NI";
    // const model_name = "gemini-pro";
    // async function getPerson(input) {
    //     const genAI = GoogleGenerativeAI(api_key);
    //     genAI.getGenerativeModel({model:model_name});
    //     const result = await ChatSession.sendMessage(input);
    //     const response = result.response.text();
    //     return response;
    // }
    let name = "John Smith";
    let job = "Student";
    let picture = "/assets/download-1.jpg";
    let biography =
        "I'm Michael, a 24-year-old senior at XYZ University, majoring in Computer Science. I'm of European descent and would describe myself as reserved. In my free time, I enjoy coding.";
    let link = "Link Here";
    // Get the value of search_term
    let value;
    search_term.subscribe((val) => {
        value = val;
    });
    let commonTags = [];
    let commonTagsCount = 0;

    function getCommonTags() {
        const allTags = people.reduce((acc, item) => acc.concat(item.tags), []);

        const tagCount = {};
        allTags.forEach((tag) => {
            tagCount[tag] = (tagCount[tag] || 0) + 1;
            commonTagsCount += 1;
        });

        commonTags = Object.keys(tagCount).filter((tag) => tagCount[tag] > 1);
        if (commonTags.length > 1) {
            name = people[2].name; // Change the name to the name from the first object in the JSON data
            job = people[2].title; // Change the job to the title from the first object in the JSON data
            biography = people[2].bio;
        }
    }
    getCommonTags();
</script>

<Page></Page>
<div class="back">
    <p>{value}</p>
    <div class="box">
        <div>
            <img id="book" src="/assets/photobook.jpg" alt="" />
            <p id="name">{name}</p>
            <p id="title">{job}</p>
            <img id="portrait" src={picture} alt="" />
            <p id="speech">
                {biography}
            </p>
            <button id="video">Learn More</button>
        </div>
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
    .box {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 50px;
        z-index: 10;
    }
    #book {
        position: relative;
        width: 110%;
        /* margin: 0 auto; */
    }
    #name {
        position: absolute;
        top: 9%;
        left: 32%;
        font-size: 40px;
    }
    #title {
        position: absolute;
        top: 24%;
        left: 35%;
        font-size: 30px;
    }
    #portrait {
        position: absolute;
        top: 40%;
        left: 27%;
    }
    #speech {
        position: absolute;
        top: 14%;
        right: 23%;
        font-size: 23px;
        font-weight: bold;
        width: 200px;
        height: 220px;
        white-space: wrap; /* Prevents the text from wrapping */
        overflow: hidden; /* Hide overflowing text */
        text-overflow: ellipsis; /* Add ellipsis (...) if text overflows */
    }
    #video {
        position: absolute;
        top: 70%;
        right: 25%;
        font-size: 22px;
        font-weight: bold;
        padding: 10px 20px;
        background-color: #333458;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
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
        filter: blur(2px);
    }
    .pics img {
        flex-grow: 1;
        filter: blur(5px);
        margin: 10px;
        filter: saturate(0);
    }
</style>
