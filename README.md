<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>ScanMark — Scan. Read. Get Inspired.</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    min-height: 100vh;
    font-family: Arial, Helvetica, sans-serif;
    background: linear-gradient(135deg, #dff4ff, #c8e8ff, #e8dcff);
    color: #24445c;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 25px;
}

/* MAIN CARD */
.container {
    width: 100%;
    max-width: 1050px;
    min-height: 650px;
    background: rgba(255, 255, 255, 0.88);
    border-radius: 35px;
    padding: 45px;
    box-shadow: 0 25px 70px rgba(65, 120, 160, 0.22);
    position: relative;
    overflow: hidden;
}

/* DECORATIONS */
.circle {
    position: absolute;
    border-radius: 50%;
    opacity: 0.5;
}

.circle-one {
    width: 250px;
    height: 250px;
    background: #bde5ff;
    top: -120px;
    right: -90px;
}

.circle-two {
    width: 180px;
    height: 180px;
    background: #d8c9ff;
    bottom: -90px;
    left: -70px;
}

.star {
    position: absolute;
    color: #8abfe3;
    font-size: 25px;
}

.star-one {
    top: 80px;
    right: 18%;
}

.star-two {
    bottom: 90px;
    right: 8%;
}

.star-three {
    top: 40%;
    left: 5%;
}

/* HEADER */
header {
    position: relative;
    z-index: 2;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 45px;
}

.logo {
    font-size: 32px;
    font-weight: 900;
    letter-spacing: -1px;
    color: #367eaf;
}

.logo span {
    color: #9a83d1;
}

.tagline {
    font-size: 11px;
    font-weight: bold;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: #6c91a8;
}

/* CONTENT */
.content {
    position: relative;
    z-index: 2;
    display: grid;
    grid-template-columns: 1fr 1.1fr;
    gap: 60px;
    align-items: center;
}

/* LEFT SIDE */
.left {
    padding: 20px;
}

.label {
    display: inline-block;
    background: #edf8ff;
    color: #5597c4;
    padding: 9px 15px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: bold;
    letter-spacing: 1px;
    margin-bottom: 25px;
}

.left h1 {
    font-size: clamp(45px, 6vw, 75px);
    line-height: 0.95;
    margin: 0 0 25px;
    letter-spacing: -4px;
    color: #234b66;
}

.left h1 span {
    font-family: Georgia, serif;
    font-weight: normal;
    color: #789dcc;
}

.description {
    color: #688497;
    line-height: 1.7;
    font-size: 15px;
    max-width: 430px;
}

/* QUOTE CARD */
.quote-area {
    position: relative;
}

.quote-card {
    background: linear-gradient(145deg, #ffffff, #f4faff);
    border: 1px solid #d7eafa;
    border-radius: 30px;
    padding: 45px;
    min-height: 390px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    box-shadow: 0 20px 50px rgba(64, 116, 150, 0.12);
    position: relative;
    overflow: hidden;
}

.quote-card::before {
    content: "“";
    position: absolute;
    top: -35px;
    right: 15px;
    font-family: Georgia, serif;
    font-size: 150px;
    color: #e5f3fc;
}

.small-label {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 2px;
    font-weight: bold;
    color: #70a7c9;
    position: relative;
    z-index: 1;
}

.quote {
    font-family: Georgia, serif;
    font-size: clamp(25px, 3vw, 35px);
    line-height: 1.35;
    color: #315770;
    margin: 25px 0;
    position: relative;
    z-index: 1;
}

.author {
    font-size: 13px;
    font-weight: bold;
    color: #8ba4b5;
    position: relative;
    z-index: 1;
}

/* BUTTONS */
.buttons {
    display: flex;
    gap: 12px;
    margin-top: 25px;
    flex-wrap: wrap;
    position: relative;
    z-index: 2;
}

button {
    border: none;
    padding: 14px 20px;
    border-radius: 15px;
    font-weight: bold;
    cursor: pointer;
    transition: 0.2s ease;
}

button:hover {
    transform: translateY(-2px);
}

.inspire {
    background: #66b5e8;
    color: white;
    box-shadow: 0 8px 20px rgba(102, 181, 232, 0.3);
}

.copy {
    background: white;
    color: #5284a5;
    border: 1px solid #d5e9f5;
}

/* REMINDER */
.reminder {
    margin-top: 25px;
    padding: 16px 20px;
    background: #f5f1ff;
    border-radius: 15px;
    color: #8070a8;
    font-size: 12px;
    line-height: 1.5;
}

/* FOOTER */
footer {
    margin-top: 35px;
    display: flex;
    justify-content: space-between;
    font-size: 10px;
    color: #9aafbd;
    position: relative;
    z-index: 2;
}

/* TOAST */
.toast {
    position: fixed;
    bottom: 25px;
    left: 50%;
    transform: translate(-50%, 20px);
    background: #24445c;
    color: white;
    padding: 12px 18px;
    border-radius: 12px;
    font-size: 13px;
    opacity: 0;
    pointer-events: none;
    transition: 0.25s;
}

.toast.show {
    opacity: 1;
    transform: translate(-50%, 0);
}

/* MOBILE */
@media (max-width: 800px) {

    body {
        padding: 12px;
    }

    .container {
        padding: 28px;
        border-radius: 28px;
    }

    header {
        flex-direction: column;
        align-items: flex-start;
        gap: 8px;
    }

    .content {
        grid-template-columns: 1fr;
        gap: 30px;
    }

    .left {
        padding: 0;
    }

    .left h1 {
        font-size: 55px;
    }

    .quote-card {
        padding: 30px;
        min-height: 330px;
    }

    footer {
        flex-direction: column;
        gap: 8px;
    }
}
</style>
</head>

<body>

<div class="container">

    <!-- Decorative elements -->
    <div class="circle circle-one"></div>
    <div class="circle circle-two"></div>

    <div class="star star-one">✦</div>
    <div class="star star-two">✧</div>
    <div class="star star-three">✦</div>

    <!-- HEADER -->
    <header>

        <div class="logo">
            Scan<span>Mark</span>
        </div>

        <div class="tagline">
            Scan. Read. Get Inspired.
        </div>

    </header>


    <!-- MAIN CONTENT -->
    <div class="content">

        <!-- LEFT -->
        <section class="left">

            <div class="label">
                ✦ A MESSAGE FOR YOU
            </div>

            <h1>
                Pause.<br>
                <span>Read this.</span>
            </h1>

            <p class="description">
                You scanned the code, so this little message
                is now yours. Take a moment, read it slowly,
                and carry the reminder with you.
            </p>

            <div class="reminder">
                ✦ You never know when a small message
                can make a big difference.
            </div>

        </section>


        <!-- RIGHT -->
        <section class="quote-area">

            <div class="quote-card">

                <div class="small-label">
                    Your ScanMark message
                </div>

                <div>

                    <div class="quote" id="quote">
                        “You do not have to have everything
                        figured out to keep moving forward.”
                    </div>

                    <div class="author" id="author">
                        — ScanMark
                    </div>

                </div>

                <div class="buttons">

                    <button class="inspire" id="newQuote">
                        ✦ Another message
                    </button>

                    <button class="copy" id="copyQuote">
                        Copy quote
                    </button>

                </div>

            </div>

        </section>

    </div>


    <!-- FOOTER -->
    <footer>

        <span>
            Created with <strong>ScanMark</strong>
        </span>

        <span>
            Scan → Read → Get Inspired
        </span>

    </footer>

</div>


<!-- COPY NOTIFICATION -->
<div class="toast" id="toast">
    Quote copied!
</div>


<script>

const quotes = [

    [
        "“You do not have to have everything figured out to keep moving forward.”",
        "— ScanMark"
    ],

    [
        "“Keep going. Small steps still move you forward.”",
        "— ScanMark"
    ],

    [
        "“Your pace is still progress.”",
        "— ScanMark"
    ],

    [
        "“Give yourself permission to begin again.”",
        "— ScanMark"
    ],

    [
        "“There is something good waiting for you beyond this moment.”",
        "— ScanMark"
    ],

    [
        "“You are allowed to be a work in progress.”",
        "— ScanMark"
    ],

    [
        "“A little progress today is still worth celebrating.”",
        "— ScanMark"
    ],

    [
        "“Take the next step. You do not need to see the whole path.”",
        "— ScanMark"
    ]

];


let current = 0;

const quoteElement = document.getElementById("quote");
const authorElement = document.getElementById("author");
const toast = document.getElementById("toast");


function showNextQuote() {

    current = (current + 1) % quotes.length;

    quoteElement.textContent = quotes[current][0];

    authorElement.textContent = quotes[current][1];

}


document
    .getElementById("newQuote")
    .addEventListener("click", showNextQuote);


document
    .getElementById("copyQuote")
    .addEventListener("click", async function() {

        try {

            await navigator.clipboard.writeText(
                quoteElement.textContent + " " + authorElement.textContent
            );

            toast.textContent = "Quote copied!";

        } catch (error) {

            toast.textContent = "Select and copy the quote";

        }

        toast.classList.add("show");

        setTimeout(function() {
            toast.classList.remove("show");
        }, 1600);

    });

</script>

</body>
</html>
