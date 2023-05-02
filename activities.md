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
        .tiles, .tile, .view, .details, p{
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .tiles{
            height: 350px;
            width: 350px;
            flex-wrap: wrap;
            justify-content: space-between;
        }
        .tiles .tile{
            cursor: pointer;
            position: relative;
            perspective: 1000px;
            transform-style: preserve-3d;
            height: calc(100% / 4 - 10px);
            width: calc(100% / 4 - 10px);
        }
        .tile.shake{
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
        .tiles .tile .view{
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
        .tile .front img{
            max-width: 17px;
        }
        .tile .back{
            transform: rotateY(-180deg);
        }
        .tile .back img{
            max-width: 40px;
        }
        .tile.flipped .front{
            transform: rotateY(180deg);
        }
        .tile.flipped .back{
            transform: rotateY(0);
        }
        .tile.badColor .back{ 
            background: #ffcbd1;
        }
        .tile.goodColor .back{
            background: #cdffd1;
        }
        .ui{
            width: 100%;
            margin-top: 15px;
            padding: 0 20px;
            border-radius: 7px;
            background: #fff;
            height: calc(100% / 4 - 30px);
            justify-content: space-between;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }
        .ui p{
            font-size: 18px;
            height: 17px;
            padding-right: 18px;
            border-right: 1px solid #ccc;
            color: #000;
        }
        .ui p span{
            margin-left: 8px;
        }
        .ui p b{
            font-weight: 500;
        }
        .ui button{
            cursor: pointer;
            font-size: 14px;
            color: #6563ff;
            border-radius: 4px;
            padding: 4px 11px;
            background: #fff;
            border: 2px solid #6563ff;
            transition: 0.3s ease;
        }
        .ui button:hover{
            color: #fff;
            background: #6563ff;
        }
        @media screen and (max-width: 700px) {
            .tiles{
                height: 350px;
                width: 350px;
            }
            .tile .front-view img{
                max-width: 16px;
            }
            .tile .back-view img{
                max-width: 40px;
            }
        }
        @media screen and (max-width: 530px) {
            .tile{
                height: 300px;
                width: 300px;
            }
            .tile .back-view img{
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
                padding-right: 5px;
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
        <ul class="tiles">
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <li class="tile">
            <div class="view front">
            <img src="images/que_icon.svg" alt="icon">
            </div>
            <div class="view back">
            <img src="images/img-kiwi.png" alt="tile-img">
            </div>
        </li>
        <div class="ui">
            <p class="time">Time: <span><b>0.00</b>s</span></p>
            <button>Retry</button>
        </div>
        </ul>
    </div>
</body>

<script>
    const tileList = document.querySelectorAll(".tile");
    const timeLabel = document.querySelector(".time b");
    const retryButton = document.querySelector(".details button");

    let time = 0;
    let counter = 0;
    let paused = false;
    let started = false;
    let tile1, tile2, timer;
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
        if(clicked != tile1 && !paused){
            clicked.classList.add("flipped");
            if(tile1 == "") {
                tile1 = clicked;
            } else {
                tile2 = clicked;
                paused = true;
                let img1 = tile1.querySelector(".back-view img").src;
                let img2 = tile2.querySelector(".back-view img").src;
                check(img1, img2);
            }
        }
    }

    function endGame(){
        clearInterval(timer);
        for (let i=0;i<tileList.length;i++){
            let tile = tileList[i];
            if (!(tile.classList.contains("flipped"))){
                tile.classList.add("flipped");
                setTimeout(() => {
                    tile.classList.add("badColor");
                }, 200);
            }
        }
    }

    function check(imgA, imgB) {
        if(imgA == imgB){
            isBad=false;
            for (let i=0;i<bad.length;i++){
                if (bad[i]==imgA.slice(42,-4)){
                    isBad=true;
                }
            }
            if (isBad){
                setTimeout(() => {
                    tile1.classList.add("badColor");
                    tile2.classList.add("badColor");
                }, 200);
                time+=5;
            } else {
                setTimeout(() => {
                    tile1.classList.add("goodColor");
                    tile2.classList.add("goodColor");
                }, 200);
                counter++;
                if(counter == 4){
                    endGame();
                    return;
                }
            }
            tile1.removeEventListener("click", flip);
            tile2.removeEventListener("click", flip);
            setTimeout(() => {
                tile1 = tile2 = "";
                paused = false;
            }, 200);
            return;
        }
        tile1.classList.add("shake");
        tile2.classList.add("shake");
        setTimeout(() => {
            tile1.classList.remove("shake", "flipped");
            tile2.classList.remove("shake");
            tile1 = tile2;
            tile2 = "";
            paused = false;
        }, 200);
    }

    function setup(){
        for (let i=0;i<tileList.length;i++){
            let tile = tileList[i];
            tile.style.display="inline";
        }
        time = 0;
        counter = 0;
        tile1 = tile2 = "";
        clearInterval(timer);
        timeLabel.innerText = time.toFixed(2);
        paused = false;
        started = false;

        good.sort((a, b) => 0.5 - Math.random());
        bad.sort((a, b) => 0.5 - Math.random());
        let tileSet = good.slice(0,4).concat(bad.slice(0,2));
        tileSet = tileSet.concat(tileSet);
        tileSet.sort((a, b) => 0.5 - Math.random());
        for (let i=0;i<tileSet.length;i++){
            tileList[i].classList.remove("flipped");
            tileList[i].classList.remove("goodColor");
            tileList[i].classList.remove("badColor");
            setTimeout(() => {
                tileList[i].querySelector(".back-view img").src = `images/img-${tileSet[i]}.png`;
            }, 500);
            tileList[i].addEventListener("click", flip);
        }
    }

    setup();

    retryButton.addEventListener("click", setup);
</script>