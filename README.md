# Sunlight-childrens
???
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>SUNLIGHT CHILDREN</title>

<style>

/* =========================
   기본
========================= */

* {
    box-sizing: border-box;
}

html,
body {
    margin: 0;
    padding: 0;
    background: #080706;
    color: #ead9b7;
    font-family:
        Georgia,
        "Noto Serif KR",
        serif;
}

body {
    min-height: 100vh;
}

button {
    font-family: inherit;
    cursor: pointer;
}


/* =========================
   전체 사이트
========================= */

#app {
    width: 100%;
    max-width: 720px;
    min-height: 100vh;
    margin: auto;
    background:
        linear-gradient(
            rgba(20,15,10,.93),
            rgba(8,7,5,.98)
        );
    padding-bottom: 75px;
}


/* =========================
   상단
========================= */

header {
    position: sticky;
    top: 0;
    z-index: 50;

    height: 58px;

    display: flex;
    align-items: center;
    justify-content: space-between;

    padding: 0 16px;

    background: rgba(13,11,9,.95);

    border-bottom:
        1px solid #725538;
}

header h1 {
    margin: 0;

    font-size: 13px;

    letter-spacing: 3px;
}

.day-counter {
    font-size: 12px;
    color: #bca47d;
}


/* =========================
   화면
========================= */

.screen {
    display: none;

    min-height: calc(100vh - 58px);

    padding-bottom: 30px;
}

.screen.active {
    display: block;
}


/* =========================
   첫 화면
========================= */

.hero {

    height: 430px;

    display: flex;

    flex-direction: column;

    justify-content: center;

    align-items: center;

    text-align: center;

    padding: 25px;

    background:

        radial-gradient(
            circle at 50% 30%,
            rgba(242,216,150,.2),
            transparent 30%
        ),

        linear-gradient(
            #58472e,
            #17110c 75%
        );

    position: relative;

    overflow: hidden;
}

.hero::before {

    content: "";

    position: absolute;

    inset: 0;

    background:

        repeating-linear-gradient(
            90deg,
            transparent 0,
            transparent 70px,
            rgba(255,255,255,.025) 71px
        );

    pointer-events: none;
}

.hero-title {

    position: relative;

    font-size: 32px;

    letter-spacing: 7px;

    color: #f3dfad;

    text-shadow:
        0 0 15px rgba(255,215,130,.25);

}

.hero-sub {

    position: relative;

    margin-top: 10px;

    font-size: 12px;

    letter-spacing: 3px;

    color: #c7b38c;

}


/* =========================
   종이 박스
========================= */

.paper {

    margin: 14px;

    padding: 18px;

    background: #e7d5aa;

    color: #31271c;

    border:
        1px solid #91704a;

    box-shadow:
        0 5px 20px rgba(0,0,0,.35);

    line-height: 1.8;
}

.paper h2 {

    margin-top: 5px;

}

.paper small {

    letter-spacing: 2px;

}


/* =========================
   버튼
========================= */

.main-button {

    width: calc(100% - 28px);

    margin: 7px 14px;

    padding: 15px;

    color: #ead9b7;

    background: #292016;

    border:
        1px solid #765637;

    transition: .15s;
}

.main-button:hover {

    background: #403021;

    border-color: #a07b4d;

}

.main-button:active {

    transform: scale(.97);

}


/* =========================
   동네
========================= */

.houses {

    display: grid;

    grid-template-columns:
        repeat(2, 1fr);

    gap: 10px;

    padding: 14px;
}

.house {

    position: relative;

    height: 160px;

    width: 100%;

    margin: 0;

    padding-top: 100px;

    background:

        linear-gradient(
            145deg,
            #51402f,
            #17110d
        );

    color: #ead9b7;

    border:
        1px solid #745637;

    overflow: hidden;

    transition: .2s;
}

.house:hover {

    transform:
        translateY(-3px);

    border-color:
        #b18a59;

}

.house-window {

    position: absolute;

    top: 25px;

    left: 50%;

    transform:
        translateX(-50%);

    width: 45px;

    height: 50px;

    background:
        #0b0d0c;

    border:
        3px solid #806542;

    box-shadow:
        inset 0 0 15px
        rgba(180,220,180,.08);
}

.house-name {

    display: block;

    font-weight: bold;

}

.house-info {

    display: block;

    margin-top: 5px;

    color: #aa9879;

    font-size: 11px;

}


/* =========================
   기록
========================= */

.record {

    margin: 8px 0;

    padding: 12px;

    background: #211912;

    border-left:
        2px solid #765536;

    color: #d8c39a;

    line-height: 1.7;
}


/* =========================
   캐릭터 모달
========================= */

.modal {

    display: none;

    position: fixed;

    inset: 0;

    z-index: 100;

    padding: 14px;

    background:
        rgba(0,0,0,.82);

    align-items: center;

    justify-content: center;
}

.modal.show {

    display: flex;
}

.dialog {

    position: relative;

    width: 100%;

    max-width: 650px;

    max-height: 85vh;

    overflow-y: auto;

    padding: 20px;

    background: #e7d5aa;

    color: #302519;

    border:
        2px solid #8c6946;

    animation:
        dialogIn .2s ease;
}

@keyframes dialogIn {

    from {

        opacity: 0;

        transform:
            translateY(15px);

    }

    to {

        opacity: 1;

        transform:
            translateY(0);

    }

}

.close {

    position: absolute;

    right: 5px;

    top: 5px;

    width: auto;

    margin: 0;

    padding: 3px 10px;

    background: transparent;

    border: none;

    color: #35291d;

    font-size: 26px;
}

.secret {

    margin: 15px 0;

    padding: 14px;

    background: #d5c18e;

    line-height: 1.7;
}

.speech {

    padding: 17px;

    margin: 12px 0;

    background: #fff0ca;

    font-size: 18px;

    line-height: 1.7;
}

.voice {

    color: #765a3c;

    font-size: 13px;
}

.choice {

    width: 100%;

    margin: 7px 0;

    padding: 13px;

    text-align: left;

    background: #292016;

    color: #ead9b7;

    border:
        1px solid #735437;
}


/* =========================
   엔딩
========================= */

.ending {

    min-height: 75vh;

    display: flex;

    flex-direction: column;

    justify-content: center;

    align-items: center;

    text-align: center;

    padding: 25px;
}

.ending h1 {

    font-size: 34px;

    letter-spacing: 5px;

}

.warning {

    color: #a35446;

}


/* =========================
   하단 메뉴
========================= */

footer {

    position: fixed;

    bottom: 0;

    left: 50%;

    transform:
        translateX(-50%);

    width: 100%;

    max-width: 720px;

    height: 65px;

    display: grid;

    grid-template-columns:
        repeat(4,1fr);

    z-index: 80;

    background:
        rgba(13,10,8,.97);

    border-top:
        1px solid #604932;
}

footer button {

    width: 100%;

    margin: 0;

    padding: 7px 2px;

    background: transparent;

    border: none;

    color: #cdbb98;

    font-size: 13px;
}


/* =========================
   모바일
========================= */

@media(max-width:430px) {

    .hero {

        height: 400px;

    }

    .hero-title {

        font-size: 25px;

    }

    .houses {

        gap: 8px;

    }

    .house {

        height: 145px;

    }

}

</style>
</head>


<body>


<div id="app">


<header>

    <h1>SUNLIGHT CHILDREN</h1>

    <div class="day-counter">

        DAY
        <b id="day">01</b>
        / 50

    </div>

</header>



<!-- =========================
     HOME
========================= -->

<section
    id="home"
    class="screen active"
>

    <div class="hero">

        <div class="hero-title">

            SUNLIGHT

            <br>

            CHILDREN

        </div>

        <div class="hero-sub">

            CHILDREN'S HOME

        </div>

    </div>


    <div class="paper">

        <small>
            WELCOME HOME!
        </small>

        <h2>
            햇살 보육원
        </h2>

        <p id="welcome">

            우리 아이들은 모두
            이곳을 자신의 집처럼
            아끼고 사랑한답니다.

        </p>

    </div>


    <button
        class="main-button"
        onclick="showScreen('neighborhood')"
    >

        🏠 NEIGHBORHOOD

    </button>


    <button
        class="main-button"
        onclick="showScreen('journal')"
    >

        📖 관찰 기록

    </button>


    <button
        class="main-button"
        onclick="showScreen('rules')"
    >

        📜 보육원 규칙

    </button>


    <button
        class="main-button"
        onclick="showScreen('director')"
    >

        🔑 원장실

    </button>

</section>



<!-- =========================
     NEIGHBORHOOD
========================= -->

<section
    id="neighborhood"
    class="screen"
>

    <div class="paper">

        <button
            onclick="showScreen('home')"
            style="
                width:auto;
                margin:0;
                padding:5px 10px;
            "
        >

            ← 홈

        </button>

        <h2>
            NEIGHBORHOOD
        </h2>

        <p>

            집을 클릭하면
            그 아이에 대한 정보를
            확인할 수 있습니다.

        </p>

    </div>


    <div
        id="houses"
        class="houses"
    ></div>

</section>



<!-- =========================
     JOURNAL
========================= -->

<section
    id="journal"
    class="screen"
>

    <div class="paper">

        <button
            onclick="showScreen('home')"
            style="
                width:auto;
                margin:0;
                padding:5px 10px;
            "
        >

            ← 홈

        </button>

        <h2>
            YOUR RECORD
        </h2>

        <div id="records">

            아직 기록이 없습니다.

        </div>

    </div>

</section>



<!-- =========================
     RULES
========================= -->

<section
    id="rules"
    class="screen"
>

    <div class="paper">

        <button
            onclick="showScreen('home')"
            style="
                width:auto;
                margin:0;
                padding:5px 10px;
            "
        >

            ← 홈

        </button>

        <h2>
            HOUSE RULES
        </h2>


        <p>
            01.
            해가 지면
            복도의 문 개수를
            세지 마세요.
        </p>


        <p>
            02.
            같은 질문을 두 번 하면
            대답하지 마세요.
        </p>


        <p>
            03.
            원장님이 열어 주기 전에는
            밖으로 나가지 마세요.
        </p>


        <p>
            04.
            지하실의 노란 문은
            없는 것으로 생각하세요.
        </p>


        <p id="secretRule"></p>

    </div>

</section>



<!-- =========================
     DIRECTOR
========================= -->

<section
    id="director"
    class="screen"
>

    <div class="paper">

        <button
            onclick="showScreen('home')"
            style="
                width:auto;
                margin:0;
                padding:5px 10px;
            "
        >

            ← 홈

        </button>

        <h2>
            원장님의 사무실
        </h2>

        <div id="directorText"></div>


        <button
            class="main-button"
            onclick="directorTalk()"
        >

            원장님께 질문하기

        </button>

    </div>

</section>



<!-- =========================
     ENDING
========================= -->

<section
    id="ending"
    class="screen"
>

    <div
        id="endingContent"
    ></div>

</section>



<!-- =========================
     CHARACTER MODAL
========================= -->

<div
    id="modal"
    class="modal"
>

    <div class="dialog">

        <button
            class="close"
            onclick="closeModal()"
        >

            ×

        </button>


        <div
            id="dialogContent"
        ></div>

    </div>

</div>



<!-- =========================
     FOOTER
========================= -->

<footer>

    <button
        onclick="showScreen('home')"
    >

        ⌂
        <br>
        홈

    </button>


    <button
        onclick="showScreen('neighborhood')"
    >

        🏠
        <br>
        동네

    </button>


    <button
        onclick="showScreen('journal')"
    >

        📖
        <br>
        기록

    </button>


    <button
        onclick="nextDay()"
    >

        ☀
        <br>
        다음 날

    </button>

</footer>


</div>



<script>

/* ==================================================
   SUNLIGHT CHILDREN
   GAME DATA
================================================== */


let day =
    Number(
        localStorage.getItem(
            "sunlight_day"
        )
    ) || 1;


let records =
    JSON.parse(
        localStorage.getItem(
            "sunlight_records"
        ) || "[]"
    );



/* ==================================================
   CHARACTERS
================================================== */

const characters = {


    hana: {

        name: "해나",

        house: "햇살 하우스",

        description:
            "항상 밝고 씩씩한 아이",

        secret:
            "자신의 나이는 기억하지 못하지만 당신이 처음 온 날짜는 정확하게 기억한다.",

        lines: [

            "오늘도 햇빛이 예쁘다—↗",

            "괜찮아. 괜찮아…↘",

            "아! 왔구나.",

            "어제도 여기 있었지?"

        ],

        voice:
            "아—↗ 흐…↘"

    },


    minwoo: {

        name: "민우",

        house: "무지개 하우스",

        description:
            "장난꾸러기",

        secret:
            "복도의 길이가 매일 달라진다는 사실을 알고 있다.",

        lines: [

            "헤헤—↗",

            "쉿! 비밀이야.",

            "저 문? 원래 없었는데.",

            "나랑 숨바꼭질 할래?"

        ],

        voice:
            "흐흐↘ 아!↗"

    },


    yuri: {

        name: "유리",

        house: "구름 하우스",

        description:
            "조용한 아이",

        secret:
            "밤마다 존재하지 않는 아이의 이름을 부른다.",

        lines: [

            "……",

            "오늘은 늦었네.",

            "저기 보지 마.",

            "아직은 괜찮아."

        ],

        voice:
            "음…↘ 아—"

    },


    eunha: {

        name: "은하",

        house: "별빛 하우스",

        description:
            "똑똑한 언니",

        secret:
            "원장님의 열쇠가 어디 있는지 알고 있다.",

        lines: [

            "그건 만지지 마.",

            "원장님께는 말하지 않을게.",

            "문은 밖으로 이어지지 않아.",

            "나를 믿어도 될까?"

        ],

        voice:
            "흠↘ 아하↗"

    },


    yeji: {

        name: "예지",

        house: "꽃잎 하우스",

        description:
            "다정한 친구",

        secret:
            "사라진 아이들의 방을 매일 청소한다.",

        lines: [

            "비밀 하나 알려줄까?",

            "여기서는 이름이 중요해.",

            "네 방은 어제랑 달라.",

            "쉿. 들었지?"

        ],

        voice:
            "아…↗ 음음—"

    },


    minseo: {

        name: "민서",

        house: "017번 방",

        description:
            "기록에만 존재하는 아이",

        secret:
            "기록에는 존재하지만 017번 방은 도면 어디에도 없다.",

        lines: [

            "……",

            "여기 있어.",

            "문을 열지 마.",

            "돌아가."

        ],

        voice:
            "……아↘"

    }

};



/* ==================================================
   HOUSES
================================================== */

const houses = [

    ["hana", "햇살 하우스", 1],

    ["minwoo", "무지개 하우스", 1],

    ["yuri", "구름 하우스", 1],

    ["eunha", "별빛 하우스", 1],

    ["yeji", "꽃잎 하우스", 1],

    ["minseo", "017번 방", 7]

];



/* ==================================================
   화면 전환
================================================== */

function showScreen(id) {

    document
        .querySelectorAll(".screen")
        .forEach(
            screen =>
                screen.classList.remove(
                    "active"
                )
        );


    document
        .getElementById(id)
        .classList.add(
            "active"
        );


    window.scrollTo(
        0,
        0
    );

}



/* ==================================================
   저장
================================================== */

function saveGame() {

    localStorage.setItem(
        "sunlight_day",
        day
    );


    localStorage.setItem(
        "sunlight_records",
        JSON.stringify(
            records
        )
    );

}



/* ==================================================
   기록 추가
================================================== */

function addRecord(text) {

    records.unshift(

        "DAY " +

        String(day)
            .padStart(2,"0") +

        " — " +

        text

    );


    records =
        records.slice(
            0,
            100
        );


    saveGame();

    renderRecords();

}



/* ==================================================
   집 만들기
================================================== */

function renderHouses() {

    const container =
        document.getElementById(
            "houses"
        );


    container.innerHTML = "";


    houses.forEach(

        ([id,name,unlock]) => {


            const locked =
                day < unlock;


            const button =
                document.createElement(
                    "button"
                );


            button.className =
                "house";


            button.innerHTML = `

                <div
                    class="house-window"
                ></div>

                <span
                    class="house-name"
                >

                    ${
                        locked
                        ? "????"
                        : name
                    }

                </span>

                <span
                    class="house-info"
                >

                    ${
                        locked

                        ? unlock +
                          "일차에 열립니다."

                        : "CLICK TO ENTER"

                    }

                </span>

            `;


            button.onclick = function() {


                if(locked) {

                    addRecord(
                        "017번 방을 찾았지만 문이 없었다."
                    );


                    alert(
                        unlock +
                        "일차부터 들어갈 수 있습니다."
                    );


                    return;

                }


                openCharacter(id);

            };


            container.appendChild(
                button
            );

        }

    );

}



/* ==================================================
   캐릭터 열기
================================================== */

function openCharacter(id) {

    const character =
        characters[id];


    const line =
        character.lines[
            Math.floor(
                Math.random() *
                character.lines.length
            )
        ];


    document.getElementById(
        "dialogContent"
    ).innerHTML = `

        <h2>
            ${character.name}
        </h2>

        <p>

            <b>
                ${character.house}
            </b>

            ·

            ${character.description}

        </p>


        <div
            class="secret"
        >

            <b>
                관찰 기록
            </b>

            <br><br>

            ${character.secret}

        </div>


        <div
            class="speech"
        >

            “${line}”

        </div>


        <p
            class="voice"
        >

            [비언어 음성]

            ${character.voice}

        </p>


        <button
            class="choice"
            onclick="
                characterTalk(
                    '${id}',
                    1
                )
            "
        >

            조용히 옆에 있어 준다

        </button>


        <button
            class="choice"
            onclick="
                characterTalk(
                    '${id}',
                    2
                )
            "
        >

            “원장님은 좋은 분이지?”

        </button>


        <button
            class="choice"
            onclick="
                characterTalk(
                    '${id}',
                    3
                )
            "
        >

            방을 자세히 살펴본다

        </button>

    `;


    document
        .getElementById(
            "modal"
        )
        .classList.add(
            "show"
        );

}



/* ==================================================
   대화
================================================== */

function characterTalk(
    id,
    choice
) {

    const character =
        characters[id];


    let response = "";


    if(choice === 1) {

        response = `

            ${character.name}가

            잠시 웃는다.

            <br><br>

            그러다 갑자기
            당신의 뒤를 바라본다.

            <br><br>

            “……들었어?”

        `;

    }


    if(choice === 2) {

        if(day < 18) {

            response = `

                “응.
                원장님은 좋은 분이야.”

                <br><br>

                대답이 너무 빨랐다.

            `;

        } else {

            response = `

                “그렇게 말해야 해.”

            `;

        }

    }


    if(choice === 3) {

        response = `

            방 안의 이름표를
            살펴본다.

            <br><br>

            벽에 적힌 날짜가
            오늘 날짜와 다르다.

            <br><br>

            그리고 침대 밑에서
            작은 금속음이 들린다.

        `;

    }


    addRecord(

        character.name +

        "의 방에서 이상한 점을 발견했다."

    );


    document.getElementById(
        "dialogContent"
    ).innerHTML = `

        <h2>
            ${character.name}
        </h2>


        <div
            class="speech"
        >

            ${response}

        </div>


        <p
            class="voice"
        >

            [어딘가에서 들려오는 소리]

            ${character.voice}

        </p>


        <button
            class="main-button"
            onclick="
                closeModal()
            "
        >

            돌아가기

        </button>

    `;

}



/* ==================================================
   모달 닫기
================================================== */

function closeModal() {

    document
        .getElementById(
            "modal"
        )
        .classList.remove(
            "show"
        );

}



/* ==================================================
   기록
================================================== */

function renderRecords() {

    const container =
        document.getElementById(
            "records"
        );


    if(records.length === 0) {

        container.innerHTML =
            "아직 기록이 없습니다.";

        return;

    }


    container.innerHTML =

        records
            .map(
                record => `

                    <div
                        class="record"
                    >

                        ${record}

                    </div>

                `
            )
            .join("");

}



/* ==================================================
   원장님
================================================== */

function renderDirector() {

    let text;


    if(day < 12) {

        text =
            "어서 오세요! 아이들이 당신을 많이 기다렸답니다.";

    }

    else if(day < 25) {

        text =
            "요즘 아이들이 조금 예민하죠. 제가 모두 책임지고 있어요.";

    }

    else if(day < 38) {

        text =
            "당신은 참 관찰력이 좋군요. 하지만 모든 것을 알 필요는 없답니다.";

    }

    else if(day < 47) {

        text =
            "밖으로 나가고 싶으신가요? 처음부터 이곳에 들어온 이유를 잊으셨나 봐요.";

    }

    else {

        text =
            "내일이면 끝납니다. 당신도 우리 가족이 될 거예요.";

    }


    document.getElementById(
        "directorText"
    ).innerHTML = `

        <p
            style="
                text-align:center;
                font-size:50px;
            "
        >

            ◉‿◉

        </p>

        <p>

            ${text}

        </p>

        <p
            class="warning"
        >

            [원장님의 목소리]

            ${
                day < 30
                ? "하하—↗"
                : "……↘"
            }

        </p>

    `;

}



/* ==================================================
   원장님 대화
================================================== */

function directorTalk() {

    addRecord(
        "원장님에게 출구에 대해 질문했다."
    );


    let answer;


    if(day < 35) {

        answer =
            "출구는 있답니다. 아직 열릴 시간이 아니에요.";

    }

    else {

        answer =
            "내일이면 알게 될 거예요.";

    }


    document.getElementById(
        "directorText"
    ).innerHTML += `

        <hr>

        <p>

            <b>
                원장님:
            </b>

            <br><br>

            ${answer}

        </p>

    `;

}



/* ==================================================
   다음 날
================================================== */

function nextDay() {

    if(day >= 50) {

        showEnding();

        return;

    }


    day++;


    const events = [

        "복도 끝에 어제 없던 문이 생겼다.",

        "아이 한 명이 오늘 날짜를 틀리게 말했다.",

        "원장실에서 열쇠 소리가 났다.",

        "이름표의 잉크가 번졌다.",

        "밤에 세 번의 노크가 들렸다."

    ];


    const event =
        events[
            Math.floor(
                Math.random() *
                events.length
            )
        ];


    addRecord(event);


    saveGame();


    update();


    showScreen("home");

}



/* ==================================================
   엔딩
================================================== */

function showEnding() {

    showScreen(
        "ending"
    );


    document.getElementById(
        "endingContent"
    ).innerHTML = `

        <div
            class="ending"
        >

            <h1>
                DAY 51
            </h1>

            <p>

                복도 끝에
                처음 보는 문이 나타났다.

            </p>


            <button
                class="main-button"
                onclick="
                    finishEnding('escape')
                "
            >

                🚪 문을 연다

                <br>

                탈출한다

            </button>


            <button
                class="main-button"
                onclick="
                    finishEnding('experiment')
                "
            >

                🔑 원장님의 목소리를
                따라간다

            </button>

        </div>

    `;

}



/* ==================================================
   엔딩 결과
================================================== */

function finishEnding(type) {

    const escaped =
        type === "escape";


    document.getElementById(
        "endingContent"
    ).innerHTML = `

        <div
            class="ending"
        >

            <h1>

                ${
                    escaped
                    ? "ESCAPE"
                    : "SUBJECT 018"
                }

            </h1>


            <p>

                ${
                    escaped

                    ?

                    `
                    문밖에는
                    바깥세상이 있었다.

                    <br><br>

                    뒤돌아본 순간
                    보육원은 사라져 있었다.

                    <br><br>

                    손에는 낯선
                    이름표 하나만
                    남아 있었다.
                    `

                    :

                    `
                    눈부신 흰 방.

                    <br><br>

                    원장님은 처음 만났을 때처럼
                    웃고 있었다.

                    <br><br>

                    “어서 와요.
                    오래 기다렸답니다.”

                    <br><br>

                    기록지에
                    새로운 번호가 찍힌다.

                    <br><br>

                    <b>
                    SUBJECT 018
                    </b>
                    `

                }

            </p>


            <button
                class="main-button"
                onclick="
                    restartGame()
                "
            >

                처음부터

            </button>

        </div>

    `;

}



/* ==================================================
   처음부터
================================================== */

function restartGame() {

    localStorage.removeItem(
        "sunlight_day"
    );

    localStorage.removeItem(
        "sunlight_records"
    );

    location.reload();

}



/* ==================================================
   화면 업데이트
================================================== */

function update() {

    document.getElementById(
        "day"
    ).textContent =

        String(day)
            .padStart(
                2,
                "0"
            );


    let welcome;


    if(day < 10) {

        welcome =
            "우리 아이들은 모두 이곳을 자신의 집처럼 아끼고 사랑한답니다.";

    }

    else if(day < 20) {

        welcome =
            "오늘도 평화로운 하루입니다. 아이들은 당신이 더 오래 머물러 주길 바랍니다.";

    }

    else if(day < 30) {

        welcome =
            "복도가 조금 길어진 것 같습니다. 원장님은 모든 것을 알고 계십니다.";

    }

    else if(day < 40) {

        welcome =
            "아이들이 당신의 이름을 부르기 시작했습니다.";

    }

    else if(day < 50) {

        welcome =
            "창문 밖으로 나갈 수 없습니다.";

    }

    else {

        welcome =
            "오늘의 햇빛은 너무 밝습니다.";

    }


    document.getElementById(
        "welcome"
    ).textContent =
        welcome;


    document.getElementById(
        "secretRule"
    ).innerHTML =

        day >= 18

        ?

        `
        05.
        밤에 들리는 노래를
        따라 부르지 마세요.
        `

        :

        "";


    renderHouses();

    renderRecords();

    renderDirector();

}



/* ==================================================
   시작
================================================== */

update();

</script>

</body>
</html>
