<head>
    <meta charset="utf-8">
    <title>Food Memory Game</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap');
        *{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        p{
            font-size: 20px;
        }
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            background: #6563ff;
        }
        ::selection{
            color: #fff;
            background: #6563ff;
        }
        .wrapper{
            padding: 25px;
            background: #f8f8f8;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        .cards, .card, .view, .details, p{
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .cards{
            height: 350px;
            width: 350px;
            flex-wrap: wrap;
            justify-content: space-between;
        }
        .cards .card{
            cursor: pointer;
            position: relative;
            perspective: 1000px;
            transform-style: preserve-3d;
            height: calc(100% / 4 - 10px);
            width: calc(100% / 4 - 10px);
        }
        .card.shake{
            animation: shake 0.35s ease-in-out;
        }
            @keyframes shake {
                0%, 100%{
                    transform: translateX(0);
                }
                20%{
                    transform: translateX(-13px);
                }
                40%{
                    transform: translateX(13px);
                }
                60%{
                    transform: translateX(-8px);
                }
                80%{
                    transform: translateX(8px);
                }
            }
        .cards .card .view{
            width: 100%;
            height: 100%;
            user-select: none;
            pointer-events: none;
            position: absolute;
            background: #fff;
            border-radius: 7px;
            backface-visibility: hidden;
            transition: transform 0.25s linear;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }
        .card .front-view img{
            max-width: 17px;
        }
        .card .back-view{
            transform: rotateY(-180deg);
        }
        .card .back-view img{
            max-width: 40px;
        }
        .card.flipped .front-view{
            transform: rotateY(180deg);
        }
        .card.flipped .back-view{
            transform: rotateY(0);
        }
        .card.badColor .back-view{ 
            background: #ffcbd1;
        }
        .card.goodColor .back-view{
            background: #cdffd1;
        }
        .details{
            width: 100%;
            margin-top: 15px;
            padding: 0 20px;
            border-radius: 7px;
            background: #fff;
            height: calc(100% / 4 - 30px);
            justify-content: space-between;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }
        .details p{
            font-size: 18px;
            height: 17px;
            padding-right: 18px;
            border-right: 1px solid #ccc;
            color: #000;
        }
        .details p span{
            margin-left: 8px;
        }
        .details p b{
            font-weight: 500;
        }
        .details button{
            cursor: pointer;
            font-size: 14px;
            color: #6563ff;
            border-radius: 4px;
            padding: 4px 11px;
            background: #fff;
            border: 2px solid #6563ff;
            transition: 0.3s ease;
        }
        .details button:hover{
            color: #fff;
            background: #6563ff;
        }
        @media screen and (max-width: 700px) {
            .cards{
                height: 350px;
                width: 350px;
            }
            .card .front-view img{
                max-width: 16px;
            }
            .card .back-view img{
                max-width: 40px;
            }
        }
        @media screen and (max-width: 530px) {
            .cards{
                height: 300px;
                width: 300px;
            }
            .card .back-view img{
                max-width: 35px;
            }
            .details{
                margin-top: 10px;
                padding: 0 15px;
                height: calc(100% / 4 - 20px);
            }
            .details p{
                height: 15px;
                font-size: 17px;
                padding-right: 13px;
            }
            .details button{
                font-size: 13px;
                padding: 5px 10px;
                border: none;
                color: #fff;
                background: #6563ff;
            }
        }
    </style>
</head>
<body>
    <div class="wrapper">
        <ul class="cards">
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-1.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-2.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-3.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-4.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-5.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-6.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-5.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-6.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-1.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-2.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-3.png" alt="card-img">
            </div>
        </li>
        <li class="card">
            <div class="view front-view">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back-view">
            <img src="images/img-4.png" alt="card-img">
            </div>
        </li>
        <div class="details">
            <p class="time">Time: <span><b>0.00</b>s</span></p>
            <button>Retry</button>
        </div>
        </ul>
    </div>
</body>

<script>
    const cardList = document.querySelectorAll(".card");
    const timeLabel = document.querySelector(".time b");
    const retryButton = document.querySelector(".details button");

    let time = 0;
    let counter = 0;
    let paused = false;
    let started = false;
    let card1, card2, timer;
    let good = [
        "almond", "apple", "avocado", "banana", "beans", "blueberry",
        "broccoli", "brusprouts", "carrot", "celery", "chickbreast", "cucumber",
        "eggs", "kiwi", "lettuce", "mushroom", "orange", "salmon",
        "spinach", "strawberry", "thethingyourdadlefttoget", "tomato", "walnut", "wholegrainbread"
    ];
    let bad = [
        "bacon","burger", "chicknug", "chips", "donut", "fries",
        "hotdog", "icecream", "pizza", "popcorn", "soda", "whitebread"
    ];

    function timing(){
        time+=0.01;
        timeLabel.innerText = time.toFixed(2);
    }

    function flip({target:clicked}){
        if(!started){
            started = true;
            timer=setInterval(timing, 10);
        }
        if(clicked != card1 && !paused){
            clicked.classList.add("flipped");
            if(card1 == "") {
                card1 = clicked;
            } else {
                card2 = clicked;
                paused = true;
                check(card1, card2);
            }
        }
    }

    function end(){
        clearInterval(timer);
        for (let i=0;i<cardList.length;i++){
            let card = cardList[i];
            if (!(card.classList.contains("flipped"))){
                card.classList.add("flipped");
                setTimeout(() => {
                    card.classList.add("badColor");
                }, 200);
            }
        }
    }

    function check(cardA, cardB) {
        let img1 = card1.querySelector(".back-view img").src;
        let img2 = card2.querySelector(".back-view img").src;
        if(img1 == img2){
            isBad=false;
            for (let i=0;i<bad.length;i++){
                if (bad[i]==img1.slice(42,-4)){
                    isBad=true;
                }
            }
            if (isBad){
                setTimeout(() => {
                    cardA.classList.add("badColor");
                    cardB.classList.add("badColor");
                }, 200);
                time+=5;
            } else {
                setTimeout(() => {
                    cardA.classList.add("goodColor");
                    cardB.classList.add("goodColor");
                }, 200);
                counter++;
                if(counter == 4){
                    end();
                    return;
                }
            }
            card1.removeEventListener("click", flip);
            card2.removeEventListener("click", flip);
            card1 = card2 = "";
            paused = false;
            return;
        }
        setTimeout(() => {
            card1.classList.add("shake");
            card2.classList.add("shake");
        }, 0);
        setTimeout(() => {
            card1.classList.remove("shake", "flipped");
            card2.classList.remove("shake");
            card1 = card2;
            card2 = "";
            paused = false;
        }, 200);
    }

    function setup(){
        for (let i=0;i<cardList.length;i++){
            let card = cardList[i];
            card.style.display="inline";
        }
        time = 0;
        counter = 0;
        card1 = card2 = "";
        clearInterval(timer);
        timeLabel.innerText = time.toFixed(2);
        paused = false;
        started = false;

        good.sort((a, b) => 0.5 - Math.random());
        bad.sort((a, b) => 0.5 - Math.random());
        let cardSet = good.slice(0,4).concat(bad.slice(0,2));
        cardSet = cardSet.concat(cardSet);
        cardSet.sort((a, b) => 0.5 - Math.random());
        for (let i=0;i<cardSet.length;i++){
            cardList[i].classList.remove("flipped");
            cardList[i].classList.remove("goodColor");
            cardList[i].classList.remove("badColor");
            setTimeout(() => {
                cardList[i].querySelector(".back-view img").src = `images/img-${cardSet[i]}.png`;
            }, 500);
            cardList[i].addEventListener("click", flip);
        }
    }

    setup();

    retryButton.addEventListener("click", setup);
</script>