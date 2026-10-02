[index.html](https://github.com/user-attachments/files/32945311/index.html)
<!DOCTYPE html>
<html lang="my">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For You ❤️</title>

<!-- Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Myanmar:wght@400;600;700&display=swap" rel="stylesheet">

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    min-height: 100vh;
    font-family: "Noto Sans Myanmar", "Segoe UI", sans-serif;
    background:
        radial-gradient(circle at 50% 10%, rgba(255, 105, 180, .25), transparent 40%),
        radial-gradient(circle at 10% 60%, rgba(255, 50, 120, .18), transparent 35%),
        radial-gradient(circle at 90% 80%, rgba(255, 150, 200, .15), transparent 35%),
        linear-gradient(180deg, #2d0b22, #1a0615 55%, #0f030d);
    color: white;
    overflow-x: hidden;
}

/* FLOATING HEARTS BACKGROUND */
.hearts {
    position: fixed;
    inset: 0;
    pointer-events: none;
    overflow: hidden;
    z-index: 0;
}

.heart {
    position: absolute;
    bottom: -50px;
    color: rgba(255, 125, 180, .35);
    font-size: 20px;
    animation: floatHeart linear infinite;
}

.heart:nth-child(1) { left: 8%; animation-duration: 9s; animation-delay: 1s; }
.heart:nth-child(2) { left: 20%; font-size: 14px; animation-duration: 12s; }
.heart:nth-child(3) { left: 35%; animation-duration: 10s; animation-delay: 3s; }
.heart:nth-child(4) { left: 52%; font-size: 16px; animation-duration: 13s; }
.heart:nth-child(5) { left: 70%; animation-duration: 11s; animation-delay: 2s; }
.heart:nth-child(6) { left: 87%; font-size: 15px; animation-duration: 9s; animation-delay: 4s; }

@keyframes floatHeart {
    0% { transform: translateY(0) rotate(0deg); opacity: 0; }
    15% { opacity: .7; }
    80% { opacity: .5; }
    100% { transform: translateY(-110vh) rotate(35deg); opacity: 0; }
}

/* MAIN CONTAINER */
.container {
    position: relative;
    z-index: 2;
    width: 100%;
    max-width: 500px;
    margin: auto;
    padding: 25px 15px 60px;
    text-align: center;
}

/* STICKER CONTAINER */
.sticker-container {
    margin-bottom: 10px;
}

.sticker-gif {
    width: 150px;
    height: auto;
    display: inline-block;
    filter: drop-shadow(0 0 15px rgba(255, 130, 190, 0.4));
}

h1 {
    font-size: 24px;
    font-weight: 700;
    color: #ffd8e9;
    text-shadow: 0 0 12px rgba(255, 120, 180, .6);
    margin-bottom: 8px;
}

.subtitle {
    color: #f8b8d2;
    font-size: 14px;
    line-height: 1.6;
    margin-bottom: 20px;
}

.counter {
    margin: 0 auto 25px;
    width: fit-content;
    padding: 8px 20px;
    border-radius: 30px;
    background: rgba(255, 85, 150, .2);
    border: 1px solid rgba(255, 140, 190, .4);
    backdrop-filter: blur(5px);
    color: #ffd5e6;
    font-size: 14px;
}

.counter span {
    color: #ff8fba;
    font-weight: bold;
    font-size: 16px;
}

/* 2-COLUMN GRID SYSTEM */
.box-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px 15px;
    width: 100%;
    margin-bottom: 30px;
}

.card {
    position: relative;
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 182, 193, 0.2);
    border-radius: 16px;
    padding: 15px 10px;
    backdrop-filter: blur(8px);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
    cursor: pointer;
    transition: all 0.3s ease;
}

.card:hover {
    transform: translateY(-5px);
    border-color: rgba(255, 182, 193, 0.5);
    box-shadow: 0 12px 25px rgba(255, 105, 180, 0.25);
}

.card.locked {
    cursor: not-allowed;
    opacity: .35;
    filter: grayscale(.6);
    transform: none !important;
}

.number {
    margin-bottom: 10px;
    color: #ffc6dc;
    font-size: 12px;
    letter-spacing: 1.5px;
    font-weight: bold;
}

/* GIFT BOX DESIGN */
.gift {
    position: relative;
    width: 120px;
    height: 100px;
    margin: auto;
}

.box-body {
    position: absolute;
    left: 10px;
    right: 10px;
    bottom: 0;
    height: 65px;
    border-radius: 6px 6px 10px 10px;
    background: linear-gradient(135deg, #d93672, #a8174d);
    box-shadow: 0 6px 15px rgba(0, 0, 0, .4);
    z-index: 2;
}

.lid {
    position: absolute;
    left: 0;
    top: 20px;
    width: 120px;
    height: 22px;
    border-radius: 5px;
    background: linear-gradient(135deg, #ed4a82, #bd2158);
    transform-origin: left bottom;
    transition: transform .5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    z-index: 4;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
}

.ribbon-v {
    position: absolute;
    left: 50%;
    top: 0;
    bottom: 0;
    width: 16px;
    transform: translateX(-50%);
    background: #ffd0df;
    z-index: 3;
}

/* SECRET TEXT DISPLAY */
.secret {
    position: absolute;
    left: 50%;
    bottom: 15px;
    width: 140px;
    transform: translateX(-50%) translateY(0) scale(0.7);
    opacity: 0;
    padding: 10px 6px;
    border-radius: 10px;
    background: #ffffff;
    color: #d91b5c;
    font-size: 13px;
    font-weight: bold;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.5);
    border: 2px solid #ffb3d1;
    transition: all 0.5s ease;
    z-index: 10;
    pointer-events: none;
    word-wrap: break-word;
}

/* OPEN ANIMATION */
.gift.open .lid {
    transform: rotate(-75deg) translate(-8px, -15px);
}

.gift.open .secret {
    opacity: 1;
    transform: translateX(-50%) translateY(-50px) scale(1);
}

.lock {
    position: absolute;
    right: 8px;
    top: 8px;
    font-size: 14px;
    opacity: 0;
}

.card.locked .lock { opacity: 1; }

/* FINAL RESULT BOX */
.selected-items {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 8px;
    margin: 15px 0;
}

.badge {
    background: rgba(255, 180, 210, .25);
    border: 1px solid rgba(255, 140, 190, .5);
    color: #ffffff;
    padding: 6px 12px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: bold;
}

.final-message {
    margin-top: 25px;
    padding: 20px 15px;
    border-radius: 18px;
    background: rgba(255, 80, 150, .15);
    border: 1px solid rgba(255, 150, 190, .3);
    backdrop-filter: blur(10px);
    color: #ffd9e8;
    line-height: 1.8;
    display: none;
    animation: fadeIn 0.8s ease;
}

.final-message.show {
    display: block;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(15px); }
    to { opacity: 1; transform: translateY(0); }
}
</style>
</head>

<body>

<div class="hearts">
    <div class="heart">♥</div>
    <div class="heart">♡</div>
    <div class="heart">♥</div>
    <div class="heart">♡</div>
</div>

<div class="container">

    <!-- WORKING GIF STICKER FROM GIPHY -->
    <div class="sticker-container">
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHY5bGRia203NGR2ZmQxZnAzbTJpdGFpYnY4bGt2ZnZmbGZtb3RwOCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/MDJ9IbxxvDUQM/giphy.gif" alt="Cute Sticker" class="sticker-gif">
    </div>

    <h1>မင်းအတွက် လက်ဆောင်လေးတွေရှိတယ်</h1>

    <div class="subtitle">
        ဘယ် Box ထဲမှာ ဘာရှိလဲ မသိရဘူး 🤭<br>
        မင်းကြိုက်တဲ့ ၅ ခုကိုပဲ ရွေးကြည့်နော် ❤️
    </div>

    <div class="counter">
        ရွေးထားပြီး — <span id="count">0</span> / 5
    </div>

    <!-- 2-COLUMN GRID FOR 10 BOXES -->
    <div class="box-grid">

        <!-- BOX 1 -->
        <div class="card" data-message="အာဘွား 💋❤️">
            <div class="number">GIFT 01</div>
            <div class="gift">
                <div class="secret">အာဘွား 💋❤️</div>
                <div class="box-body"></div>
                <div class="ribbon-v"></div>
                <div class="lid"></div>
            </div>
            <div class="lock">🔒</div>
        </div>

        <!-- BOX 2 -->
        <div class="card" data-message="အချစ်တွေ 💖">
            <div class="number">GIFT 02</div>
            <div class="gift">
                <div class="secret">အချစ်တွေ 💖</div>
                <div class="box-body"></div>
                <div class="ribbon-v"></div>
                <div class="lid"></div>
            </div>
            <div class="lock">🔒</div>
        </div>

        <!-- BOX 3 -->
        <div class="card" data-message="အာဘွား 💋❤️">
            <div class="number">GIFT 03</div>
            <div class="gift">
                <div class="secret">အာဘွား 💋❤️</div>
                <div class="box-body"></div>
                <div class="ribbon-v"></div>
                <div class="lid"></div>
            </div>
            <div class="lock">🔒</div>
        </div>

        <!-- BOX 4 -->
        <div class="card" data-message="လူကိုအပိုင်ယူ 🫂❤️">
            <div class="number">GIFT 04</div>
            <div class="gift">
                <div class="secret">လူကိုအပိုင်ယူ 🫂❤️</div>
                <div class="box-body"></div>
                <div class="ribbon-v"></div>
                <div class="lid"></div>
            </div>
            <div class="lock">🔒</div>
        </div>

        <!-- BOX 5 -->
        <div class="card" data-message="အာဘွား 💋❤️">
            <div class="number">GIFT 05</div>
            <div class="gift">
                <div class="secret">အာဘွား 💋❤️</div>
                <div class="box-body"></div>
                <div class="ribbon-v"></div>
                <div class="lid"></div>
            </div>
            <div class="lock">🔒</div>
        </div>

        <!-- BOX 6 -->
        <div class="card" data-message="သီတင်းကျွတ်မုန့်ဖိုး ၁ သိန်း 💰❤️">
            <div class="number">GIFT 06</div>
            <div class="gift">
                <div class="secret">သီတင်းကျွတ်မုန့်ဖိုး ၁ သိန်း 💰❤️</div>
                <div class="box-body"></div>
                <div class="ribbon-v"></div>
                <div class="lid"></div>
            </div>
            <div class="lock">🔒</div>
        </div>

        <!-- BOX 7 -->
        <div class="card" data-message="အာဘွား 💋❤️">
            <div class="number">GIFT 07</div>
            <div class="gift">
                <div class="secret">အာဘွား 💋❤️</div>
                <div class="box-body"></div>
                <div class="ribbon-v"></div>
                <div class="lid"></div>
            </div>
            <div class="lock">🔒</div>
        </div>

        <!-- BOX 8 -->
        <div class="card" data-message="စားချင်တဲ့မုန့်များ 🍰🍓❤️">
            <div class="number">GIFT 08</div>
            <div class="gift">
                <div class="secret">စားချင်တဲ့မုန့်များ 🍰🍓❤️️</div>
                <div class="box-body"></div>
                <div class="ribbon-v"></div>
                <div class="lid"></div>
            </div>
            <div class="lock">🔒</div>
        </div>

        <!-- BOX 9 -->
        <div class="card" data-message="အာဘွား 💋❤️">
            <div class="number">GIFT 09</div>
            <div class="gift">
                <div class="secret">အာဘွား 💋❤️</div>
                <div class="box-body"></div>
                <div class="ribbon-v"></div>
                <div class="lid"></div>
            </div>
            <div class="lock">🔒</div>
        </div>

        <!-- BOX 10 -->
        <div class="card" data-message="လိုချင်တဲ့ဝမ်းဆက်တစ်စုံ 👗✨">
            <div class="number">GIFT 10</div>
            <div class="gift">
                <div class="secret">လိုချင်တဲ့ဝမ်းဆက်တစ်စုံ 👗✨</div>
                <div class="box-body"></div>
                <div class="ribbon-v"></div>
                <div class="lid"></div>
            </div>
            <div class="lock">🔒</div>
        </div>

    </div>

    <!-- FINAL RESULT (NO RESET BUTTON) -->
    <div class="final-message" id="finalMessage">
        💕 မင်းရွေးလိုက်တဲ့ လက်ဆောင်တွေက<br>
        <div class="selected-items" id="selectedItems"></div>
        ကိုယ်မင်းအတွက် တကူးတက သိမ်းထားပေးတဲ့<br>
        <strong>Surprise လေးတွေပါ ❤️</strong>
        <br><br>
        မင်းပျော်ရင် ကိုယ်လည်းပျော်တယ် 🥰
    </div>

</div>

<script>
const cards = document.querySelectorAll(".card");
const countText = document.getElementById("count");
const finalMessage = document.getElementById("finalMessage");
const selectedItemsContainer = document.getElementById("selectedItems");

const MAX_SELECTIONS = 5;
let selected = 0;
let chosenGifts = [];

cards.forEach(card => {
    card.addEventListener("click", () => {
        if (card.classList.contains("selected") || card.classList.contains("locked")) {
            return;
        }

        if (selected >= MAX_SELECTIONS) {
            return;
        }

        selected++;
        chosenGifts.push(card.getAttribute("data-message"));

        card.classList.add("selected");
        const gift = card.querySelector(".gift");
        gift.classList.add("open");

        countText.textContent = selected;

        if (selected === MAX_SELECTIONS) {
            // Lock all unselected boxes
            cards.forEach(otherCard => {
                if (!otherCard.classList.contains("selected")) {
                    otherCard.classList.add("locked");
                }
            });

            // Display results
            selectedItemsContainer.innerHTML = "";
            chosenGifts.forEach(msg => {
                const badge = document.createElement("span");
                badge.className = "badge";
                badge.textContent = msg;
                selectedItemsContainer.appendChild(badge);
            });

            setTimeout(() => {
                finalMessage.classList.add("show");
            }, 600);
        }
    });
});
</script>

</body>
</html>
