<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>[작품 제목을 입력하세요]</title>

<style>

/* =========================================================
   기본 설정
========================================================= */

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

html,
body{
    width:100%;
    height:100%;
}

body{
    font-family:
        "Noto Serif KR",
        "Nanum Myeongjo",
        serif;

    color:#f4f5ff;
    background:#070a18;

    overflow:hidden;
}


/* =========================================================
   전체 배경
========================================================= */

body::before{
    content:"";

    position:fixed;
    inset:0;

    background:
        radial-gradient(
            circle at 50% 20%,
            rgba(91,115,255,.16),
            transparent 35%
        ),
        radial-gradient(
            circle at 20% 80%,
            rgba(111,92,255,.10),
            transparent 35%
        ),
        linear-gradient(
            180deg,
            #090d20 0%,
            #070a18 55%,
            #050712 100%
        );

    z-index:-5;
}


/* =========================================================
   별 배경
========================================================= */

.stars{
    position:fixed;
    inset:0;

    pointer-events:none;

    z-index:-3;
}

.star{
    position:absolute;

    width:2px;
    height:2px;

    border-radius:50%;

    background:white;

    opacity:.7;

    animation:
        twinkle
        3s
        ease-in-out
        infinite;
}

@keyframes twinkle{

    0%,
    100%{
        opacity:.2;
        transform:scale(.7);
    }

    50%{
        opacity:1;
        transform:scale(1.3);
    }

}


/* =========================================================
   달
========================================================= */

.moon{
    position:fixed;

    width:180px;
    height:180px;

    top:90px;
    right:9%;

    border-radius:50%;

    background:
        radial-gradient(
            circle at 35% 35%,
            #ffffff,
            #dbe3ff 45%,
            #9ba9dc 100%
        );

    box-shadow:
        0 0 30px rgba(190,205,255,.35),
        0 0 80px rgba(120,145,255,.18);

    opacity:.9;

    z-index:-2;
}

.moon::after{
    content:"";

    position:absolute;

    width:180px;
    height:180px;

    top:-8px;
    left:25px;

    border-radius:50%;

    background:#080b19;
}


/* =========================================================
   마법진 장식
========================================================= */

.magic-circle{
    position:fixed;

    width:520px;
    height:520px;

    left:-180px;
    bottom:-180px;

    border:

        1px solid
        rgba(151,169,255,.18);

    border-radius:50%;

    box-shadow:
        0 0 0 30px rgba(130,150,255,.03),
        0 0 0 60px rgba(130,150,255,.025);

    animation:
        rotateCircle
        35s
        linear
        infinite;

    pointer-events:none;

    z-index:-2;
}

.magic-circle::before,
.magic-circle::after{
    content:"";

    position:absolute;

    inset:50px;

    border:
        1px solid
        rgba(151,169,255,.15);

    border-radius:50%;
}

.magic-circle::after{
    inset:110px;

    border-style:dashed;
}

@keyframes rotateCircle{

    from{
        transform:rotate(0deg);
    }

    to{
        transform:rotate(360deg);
    }

}


/* =========================================================
   유성
========================================================= */

.shooting-star{
    position:fixed;

    width:130px;
    height:1px;

    background:
        linear-gradient(
            90deg,
            transparent,
            rgba(220,230,255,.8)
        );

    transform:rotate(-30deg);

    opacity:0;

    animation:
        shooting
        8s
        linear
        infinite;

    pointer-events:none;
}

.shooting-star.one{
    top:20%;
    left:-150px;
    animation-delay:2s;
}

.shooting-star.two{
    top:45%;
    left:-150px;
    animation-delay:6s;
}

@keyframes shooting{

    0%{
        transform:
            translate(0,0)
            rotate(-30deg);

        opacity:0;
    }

    10%{
        opacity:1;
    }

    25%{
        transform:
            translate(900px,500px)
            rotate(-30deg);

        opacity:0;
    }

    100%{
        opacity:0;
    }

}


/* =========================================================
   네비게이션
========================================================= */

header{
    position:fixed;

    top:0;
    left:0;

    width:100%;
    height:75px;

    display:flex;

    align-items:center;
    justify-content:space-between;

    padding:
        0 50px;

    background:
        linear-gradient(
            180deg,
            rgba(5,8,20,.88),
            rgba(5,8,20,.35)
        );

    backdrop-filter:blur(8px);

    border-bottom:
        1px solid
        rgba(180,190,255,.08);

    z-index:100;
}


/* 작품 제목 */

.logo{
    font-size:18px;

    letter-spacing:3px;

    color:#e8ebff;

    cursor:pointer;

    text-shadow:
        0 0 15px
        rgba(150,170,255,.45);
}


/* 메뉴 */

nav{
    display:flex;

    gap:28px;
}

nav button{
    border:none;

    background:none;

    color:
        rgba(235,238,255,.58);

    font-family:inherit;

    font-size:12px;

    letter-spacing:2px;

    cursor:pointer;

    transition:.3s;
}

nav button:hover{
    color:#ffffff;

    text-shadow:
        0 0 12px
        rgba(160,180,255,.8);
}


/* =========================================================
   페이지 공통
========================================================= */

.page{
    position:absolute;

    top:75px;
    left:0;

    width:100%;
    height:calc(100% - 75px);

    display:none;

    overflow:hidden;

    padding:50px;
}

.page.active{
    display:block;
}


/* =========================================================
   HOME
========================================================= */

.home{
    width:900px;
    max-width:90%;

    margin:
        13vh auto 0;

    text-align:center;
}

.home-small{
    font-size:12px;

    letter-spacing:5px;

    color:
        rgba(190,202,255,.6);

    margin-bottom:25px;
}

.home-title{
    font-size:
        clamp(
            35px,
            6vw,
            70px
        );

    font-weight:500;

    letter-spacing:7px;

    line-height:1.35;

    text-shadow:
        0 0 30px
        rgba(120,150,255,.35);
}

.home-line{
    width:90px;
    height:1px;

    margin:35px auto;

    background:
        rgba(200,210,255,.5);
}

.home-description{
    max-width:650px;

    margin:auto;

    color:
        rgba(235,238,255,.63);

    font-size:14px;

    line-height:2.1;
}


/* =========================================================
   공통 섹션 제목
========================================================= */

.section-title{
    text-align:center;

    margin-bottom:35px;
}

.section-title h2{
    font-size:27px;

    font-weight:400;

    letter-spacing:5px;
}

.section-title p{
    margin-top:10px;

    font-size:11px;

    letter-spacing:3px;

    color:
        rgba(190,200,240,.45);
}


/* =========================================================
   WORLD
========================================================= */

.world-content{
    width:850px;
    max-width:100%;

    height:calc(100% - 100px);

    margin:auto;

    overflow-y:auto;

    padding:
        20px 25px 100px;
}

.world-content::-webkit-scrollbar{
    width:5px;
}

.world-content::-webkit-scrollbar-track{
    background:rgba(255,255,255,.03);
}

.world-content::-webkit-scrollbar-thumb{
    background:
        rgba(150,170,255,.35);

    border-radius:10px;
}

.world-box{
    padding:35px;

    margin-bottom:25px;

    border:
        1px solid
        rgba(180,190,255,.12);

    background:
        rgba(255,255,255,.025);

    box-shadow:
        inset 0 0 40px
        rgba(100,120,255,.025);
}

.world-box h3{
    margin-bottom:18px;

    font-size:18px;

    letter-spacing:3px;

    font-weight:400;
}

.world-box p{
    font-size:14px;

    line-height:2.1;

    color:
        rgba(235,238,255,.68);

    white-space:pre-line;
}


/* =========================================================
   CHARACTERS
========================================================= */

.character-list{
    width:950px;
    max-width:100%;

    height:calc(100% - 100px);

    margin:auto;

    display:grid;

    grid-template-columns:
        repeat(
            auto-fit,
            minmax(210px,1fr)
        );

    gap:22px;

    overflow-y:auto;

    padding:
        10px 10px 100px;
}

.character-list::-webkit-scrollbar{
    width:5px;
}

.character-list::-webkit-scrollbar-thumb{
    background:
        rgba(150,170,255,.35);

    border-radius:10px;
}


/* 캐릭터 카드 */

.character-card{
    min-height:330px;

    border:
        1px solid
        rgba(180,190,255,.13);

    background:
        rgba(255,255,255,.025);

    cursor:pointer;

    transition:
        .35s;

    overflow:hidden;

    position:relative;
}

.character-card:hover{
    transform:
        translateY(-6px);

    border-color:
        rgba(190,205,255,.4);

    box-shadow:
        0 15px 40px
        rgba(0,0,0,.3),
        0 0 25px
        rgba(120,145,255,.08);
}


/* 이미지 */

.character-image{
    width:100%;
    height:230px;

    background:
        linear-gradient(
            135deg,
            #12182f,
            #080b18
        );

    overflow:hidden;
}

.character-image img{
    width:100%;
    height:100%;

    object-fit:cover;

    display:block;
}


/* 이미지 없을 때 */

.no-image{
    width:100%;
    height:100%;

    display:flex;

    align-items:center;
    justify-content:center;

    color:
        rgba(200,210,255,.25);

    font-size:12px;

    letter-spacing:2px;
}


/* 카드 정보 */

.character-info{
    padding:18px 20px;
}

.character-name{
    font-size:19px;

    letter-spacing:2px;

    margin-bottom:7px;
}

.character-title{
    font-size:11px;

    line-height:1.7;

    color:
        rgba(190,200,240,.55);
}


/* =========================================================
   CHARACTER DETAIL
========================================================= */

.character-detail{
    width:1000px;
    max-width:100%;

    height:calc(100% - 80px);

    margin:auto;

    overflow-y:auto;

    padding:
        10px 20px 120px;
}

.character-detail::-webkit-scrollbar{
    width:5px;
}

.character-detail::-webkit-scrollbar-thumb{
    background:
        rgba(150,170,255,.35);

    border-radius:10px;
}


/* 뒤로가기 */

.back-button{
    border:none;

    background:none;

    color:
        rgba(210,220,255,.55);

    font-family:inherit;

    letter-spacing:2px;

    font-size:11px;

    cursor:pointer;

    margin-bottom:25px;
}

.back-button:hover{
    color:white;
}


/* 상세 상단 */

.detail-top{
    display:grid;

    grid-template-columns:
        300px 1fr;

    gap:45px;

    align-items:start;
}


/* 상세 이미지 */

.detail-image{
    width:300px;
    height:420px;

    border:
        1px solid
        rgba(190,200,255,.15);

    background:
        rgba(255,255,255,.025);

    overflow:hidden;
}

.detail-image img{
    width:100%;
    height:100%;

    object-fit:cover;
}

.detail-image .no-image{
    height:100%;
}


/* 상세 이름 */

.detail-name{
    font-size:38px;

    letter-spacing:5px;

    margin-bottom:12px;
}

.detail-title{
    color:
        rgba(195,205,245,.58);

    font-size:13px;

    line-height:1.8;

    margin-bottom:30px;
}


/* 프로필 정보 */

.profile-grid{
    display:grid;

    grid-template-columns:
        repeat(2,1fr);

    gap:12px;
}

.profile-box{
    min-height:95px;

    padding:18px;

    border:
        1px solid
        rgba(180,190,255,.1);

    background:
        rgba(255,255,255,.025);
}

.profile-label{
    font-size:9px;

    letter-spacing:2px;

    color:
        rgba(180,195,245,.45);

    margin-bottom:10px;
}

.profile-value{
    font-size:13px;

    line-height:1.7;

    color:
        rgba(245,247,255,.82);

    white-space:pre-line;
}


/* 좋아하는 것 / 싫어하는 것 */

.detail-likes{
    margin-top:35px;

    display:grid;

    grid-template-columns:
        1fr 1fr;

    gap:20px;
}

.like-box,
.dislike-box{
    padding:25px;

    border:
        1px solid
        rgba(180,190,255,.1);

    background:
        rgba(255,255,255,.025);
}

.like-box h4,
.dislike-box h4{
    font-size:10px;

    letter-spacing:3px;

    margin-bottom:12px;

    color:
        rgba(200,210,255,.55);
}

.like-box p,
.dislike-box p{
    font-size:13px;

    line-height:1.8;

    white-space:pre-line;
}


/* =========================================================
   RELATION
========================================================= */

.relation-content{
    width:850px;
    max-width:100%;

    height:calc(100% - 100px);

    margin:auto;

    overflow-y:auto;

    padding:
        20px 20px 120px;
}

.relation-content::-webkit-scrollbar{
    width:5px;
}

.relation-content::-webkit-scrollbar-thumb{
    background:
        rgba(150,170,255,.35);

    border-radius:10px;
}

.relation-box{
    margin-bottom:25px;

    padding:30px;

    border:
        1px solid
        rgba(180,190,255,.1);

    background:
        rgba(255,255,255,.025);
}

.relation-box h3{
    font-size:17px;

    font-weight:400;

    letter-spacing:2px;

    margin-bottom:15px;
}

.relation-box p{
    font-size:14px;

    line-height:2.1;

    color:
        rgba(235,238,255,.65);

    white-space:pre-line;
}


/* =========================================================
   STORY
========================================================= */

/*
   ★ 핵심 ★
   STORY 전체 영역은 화면에 고정하고,
   .story 내부만 스크롤되도록 설정
*/

#story{
    overflow:hidden;
}


/* 스토리 내부 */

#story .story{
    width:800px;
    max-width:100%;

    height:calc(100% - 90px);

    margin:auto;

    display:block;

    overflow-y:auto;
    overflow-x:hidden;

    padding:
        15px 25px 150px 10px;
}


/* 스토리 스크롤바 */

#story .story::-webkit-scrollbar{
    width:6px;
}

#story .story::-webkit-scrollbar-track{
    background:
        rgba(255,255,255,.03);

    border-radius:10px;
}

#story .story::-webkit-scrollbar-thumb{
    background:
        rgba(150,170,255,.4);

    border-radius:10px;
}

#story .story::-webkit-scrollbar-thumb:hover{
    background:
        rgba(180,200,255,.65);
}


/* 스토리 챕터 */

.story-chapter{
    padding:35px;

    margin-bottom:30px;

    border:
        1px solid
        rgba(180,190,255,.12);

    background:
        rgba(255,255,255,.025);
}

.story-chapter-number{
    font-size:10px;

    letter-spacing:4px;

    color:
        rgba(180,195,255,.45);

    margin-bottom:15px;
}

.story-chapter-title{
    font-size:23px;

    letter-spacing:3px;

    font-weight:400;

    margin-bottom:25px;
}

.story-text{
    font-size:14px;

    line-height:2.25;

    color:
        rgba(240,242,255,.72);

    white-space:pre-line;
}


/* =========================================================
   ABOUT
========================================================= */

.about{
    width:700px;
    max-width:100%;

    margin:
        8vh auto 0;

    text-align:center;
}

.about h3{
    font-size:25px;

    font-weight:400;

    letter-spacing:4px;

    margin-bottom:25px;
}

.about p{
    font-size:14px;

    line-height:2.2;

    color:
        rgba(235,238,255,.62);

    white-space:pre-line;
}


/* =========================================================
   클릭 별 효과
========================================================= */

.click-star{
    position:fixed;

    width:5px;
    height:5px;

    border-radius:50%;

    background:white;

    pointer-events:none;

    animation:
        clickStar
        .8s
        ease-out
        forwards;

    box-shadow:
        0 0 10px
        rgba(200,220,255,.9);

    z-index:999;
}

@keyframes clickStar{

    0%{
        opacity:1;
        transform:scale(1);
    }

    100%{
        opacity:0;

        transform:
            translate(
                var(--x),
                var(--y)
            )
            scale(0);
    }

}


/* =========================================================
   모바일
========================================================= */

@media(
    max-width:700px
){

    header{
        height:65px;

        padding:
            0 18px;
    }

    nav{
        gap:12px;
    }

    nav button{
        font-size:9px;

        letter-spacing:1px;
    }

    .logo{
        font-size:13px;

        letter-spacing:2px;
    }

    .page{
        top:65px;

        height:calc(100% - 65px);

        padding:
            35px 18px;
    }

    .moon{
        width:110px;
        height:110px;

        top:90px;
        right:-20px;
    }

    .moon::after{
        width:110px;
        height:110px;

        left:18px;
        top:-5px;
    }

    .home{
        margin-top:12vh;
    }

    .home-title{
        font-size:31px;

        letter-spacing:4px;
    }

    .section-title h2{
        font-size:21px;
    }

    .character-list{
        grid-template-columns:
            repeat(2,1fr);

        gap:12px;
    }

    .character-card{
        min-height:260px;
    }

    .character-image{
        height:170px;
    }

    .character-info{
        padding:13px;
    }

    .character-name{
        font-size:15px;
    }

    .character-title{
        font-size:9px;
    }

    .detail-top{
        grid-template-columns:1fr;

        gap:25px;
    }

    .detail-image{
        width:100%;
        height:380px;
    }

    .detail-name{
        font-size:30px;
    }

    .detail-likes{
        grid-template-columns:1fr;
    }

    #story .story{
        padding:
            10px 10px 120px 0;
    }

    .story-chapter{
        padding:25px;
    }

    .story-chapter-title{
        font-size:19px;
    }

}

</style>
</head>


<body>


<!-- =======================================================
     배경 장식
======================================================= -->

<div class="stars" id="stars"></div>

<div class="moon"></div>

<div class="magic-circle"></div>

<div class="shooting-star one"></div>
<div class="shooting-star two"></div>


<!-- =======================================================
     HEADER
======================================================= -->

<header>

    <div
        class="logo"
        onclick="go('home')"
    >
        [작품 제목]
    </div>

    <nav>

        <button onclick="go('home')">
            HOME
        </button>

        <button onclick="go('world')">
            WORLD
        </button>

        <button onclick="go('characters')">
            CHARACTERS
        </button>

        <button onclick="go('relation')">
            RELATION
        </button>

        <button onclick="go('story')">
            STORY
        </button>

        <button onclick="go('about')">
            ABOUT
        </button>

    </nav>

</header>


<!-- =======================================================
     HOME
======================================================= -->

<section
    id="home"
    class="page active"
>

    <div class="home">

        <div class="home-small">
            [작품 장르 / 짧은 문구]
        </div>

        <h1 class="home-title">
            [작품 제목을 입력하세요]
        </h1>

        <div class="home-line"></div>

        <p class="home-description">
            [작품의 분위기나 간단한 소개를 입력하세요.]
            <br>
            [한 줄 소개를 입력하세요.]
        </p>

    </div>

</section>


<!-- =======================================================
     WORLD
======================================================= -->

<section
    id="world"
    class="page"
>

    <div class="section-title">

        <h2>
            WORLD
        </h2>

        <p>
            [세계관]
        </p>

    </div>


    <div class="world-content">


        <div class="world-box">

            <h3>
                [세계관 제목]
            </h3>

            <p>
[세계관에 대한 설명을 입력하세요.]

[세계의 역사, 배경, 시대, 사회 등에 대한 내용을 입력하세요.]

[원하는 만큼 길게 작성할 수 있습니다.]
            </p>

        </div>


        <div class="world-box">

            <h3>
                [세계의 주요 장소]
            </h3>

            <p>
[장소에 대한 설명을 입력하세요.]

[왕국 / 도시 / 마을 / 숲 / 성 / 학교 등 원하는 내용을 작성하세요.]
            </p>

        </div>


        <div class="world-box">

            <h3>
                [세계관의 특별한 설정]
            </h3>

            <p>
[마법 / 신 / 종족 / 능력 / 사건 등 필요한 설정을 입력하세요.]
            </p>

        </div>


    </div>

</section>


<!-- =======================================================
     CHARACTERS
======================================================= -->

<section
    id="characters"
    class="page"
>

    <div class="section-title">

        <h2>
            CHARACTERS
        </h2>

        <p>
            [등장인물]
        </p>

    </div>


    <div
        id="characterList"
        class="character-list"
    ></div>

</section>


<!-- =======================================================
     CHARACTER DETAIL
======================================================= -->

<section
    id="characterDetail"
    class="page"
>

    <div
        id="detailContainer"
        class="character-detail"
    ></div>

</section>


<!-- =======================================================
     RELATION
======================================================= -->

<section
    id="relation"
    class="page"
>

    <div class="section-title">

        <h2>
            RELATION
        </h2>

        <p>
            [캐릭터와 {user}의 관계]
        </p>

    </div>


    <div class="relation-content">


        <div class="relation-box">

            <h3>
                [캐릭터 1 이름] × {user}
            </h3>

            <p>
[캐릭터와 {user}의 관계를 입력하세요.]

[첫 만남 / 현재 관계 / 서로에 대한 감정 등을 작성하세요.]
            </p>

        </div>


        <div class="relation-box">

            <h3>
                [캐릭터 2 이름] × {user}
            </h3>

            <p>
[캐릭터와 {user}의 관계를 입력하세요.]
            </p>

        </div>


        <div class="relation-box">

            <h3>
                [캐릭터 3 이름] × {user}
            </h3>

            <p>
[캐릭터와 {user}의 관계를 입력하세요.]
            </p>

        </div>


    </div>

</section>


<!-- =======================================================
     STORY
======================================================= -->

<section
    id="story"
    class="page"
>

    <div class="section-title">

        <h2>
            STORY
        </h2>

        <p>
            [스토리]
        </p>

    </div>


    <!--
        ★ 이 부분만 스크롤됨 ★
    -->

    <div class="story">


        <!-- CHAPTER 01 -->

        <article class="story-chapter">

            <div class="story-chapter-number">
                CHAPTER 01
            </div>

            <h3 class="story-chapter-title">
                [챕터 제목]
            </h3>

            <p class="story-text">
[첫 번째 스토리 내용을 입력하세요.]

[여기에 원하는 만큼 긴 내용을 작성할 수 있습니다.]

[문단을 나누고 싶다면 줄을 띄워주세요.]

[내용이 화면보다 길어지면 이 영역에서 마우스 휠이나 터치 스크롤로 아래까지 내려갈 수 있습니다.]
            </p>

        </article>


        <!-- CHAPTER 02 -->

        <article class="story-chapter">

            <div class="story-chapter-number">
                CHAPTER 02
            </div>

            <h3 class="story-chapter-title">
                [챕터 제목]
            </h3>

            <p class="story-text">
[두 번째 스토리 내용을 입력하세요.]

[원하는 만큼 긴 내용을 작성하세요.]
            </p>

        </article>


        <!-- CHAPTER 03 -->

        <article class="story-chapter">

            <div class="story-chapter-number">
                CHAPTER 03
            </div>

            <h3 class="story-chapter-title">
                [챕터 제목]
            </h3>

            <p class="story-text">
[세 번째 스토리 내용을 입력하세요.]

[원하는 만큼 긴 내용을 작성하세요.]
            </p>

        </article>


        <!-- CHAPTER 04 -->

        <article class="story-chapter">

            <div class="story-chapter-number">
                CHAPTER 04
            </div>

            <h3 class="story-chapter-title">
                [챕터 제목]
            </h3>

            <p class="story-text">
[네 번째 스토리 내용을 입력하세요.]
            </p>

        </article>


        <!-- CHAPTER 05 -->

        <article class="story-chapter">

            <div class="story-chapter-number">
                CHAPTER 05
            </div>

            <h3 class="story-chapter-title">
                [챕터 제목]
            </h3>

            <p class="story-text">
[다섯 번째 스토리 내용을 입력하세요.]
            </p>

        </article>


    </div>

</section>


<!-- =======================================================
     ABOUT
======================================================= -->

<section
    id="about"
    class="page"
>

    <div class="about">

        <h3>
            [작품 제목]
        </h3>

        <p>
[작품에 대한 추가 설명을 입력하세요.]

[제작자 코멘트 / 주의사항 / 세계관 설명 / 기타 내용을 입력하세요.]

[원하는 내용을 자유롭게 작성할 수 있습니다.]
        </p>

    </div>

</section>


<script>

/* =========================================================
   별 생성
========================================================= */

const stars = document.getElementById("stars");

for(let i = 0; i < 150; i++){

    const star = document.createElement("div");

    star.className = "star";

    star.style.left =
        Math.random() * 100 + "%";

    star.style.top =
        Math.random() * 100 + "%";

    star.style.animationDelay =
        Math.random() * 3 + "s";

    star.style.animationDuration =
        (2 + Math.random() * 4) + "s";

    stars.appendChild(star);
}


/* =========================================================
   페이지 이동
========================================================= */

function go(id){

    document
        .querySelectorAll(".page")
        .forEach(page => {

            page.classList.remove("active");

        });


    const target =
        document.getElementById(id);

    if(target){

        target.classList.add("active");

    }

}


/* =========================================================
   캐릭터 데이터
=========================================================

   ★ 여기만 수정하면 캐릭터가 바뀝니다.

   사용할 수 있는 항목은 딱 8개:

   name
   title
   age
   gender
   personality
   like
   dislike
   image

========================================================= */

const characters = [

    {

        name:
            "[캐릭터 1 이름]",

        title:
            "[캐릭터 1 칭호 / 한 줄 소개]",

        age:
            "[나이]",

        gender:
            "[성별]",

        personality:
            "[성격]",

        like:
            "[좋아하는 것]",

        dislike:
            "[싫어하는 것]",

        image:
            ""

    },


    {

        name:
            "[캐릭터 2 이름]",

        title:
            "[캐릭터 2 칭호 / 한 줄 소개]",

        age:
            "[나이]",

        gender:
            "[성별]",

        personality:
            "[성격]",

        like:
            "[좋아하는 것]",

        dislike:
            "[싫어하는 것]",

        image:
            ""

    },


    {

        name:
            "[캐릭터 3 이름]",

        title:
            "[캐릭터 3 칭호 / 한 줄 소개]",

        age:
            "[나이]",

        gender:
            "[성별]",

        personality:
            "[성격]",

        like:
            "[좋아하는 것]",

        dislike:
            "[싫어하는 것]",

        image:
            ""

    },


    {

        name:
            "[캐릭터 4 이름]",

        title:
            "[캐릭터 4 칭호 / 한 줄 소개]",

        age:
            "[나이]",

        gender:
            "[성별]",

        personality:
            "[성격]",

        like:
            "[좋아하는 것]",

        dislike:
            "[싫어하는 것]",

        image:
            ""

    }

];


/* =========================================================
   캐릭터 카드 생성
========================================================= */

const characterList =
    document.getElementById(
        "characterList"
    );


characters.forEach(
    (character,index) => {

        const card =
            document.createElement(
                "div"
            );

        card.className =
            "character-card";


        let imageHTML = "";

        if(character.image){

            imageHTML = `
                <img
                    src="${character.image}"
                    alt="${character.name}"
                >
            `;

        }else{

            imageHTML = `
                <div class="no-image">
                    IMAGE
                </div>
            `;

        }


        card.innerHTML = `

            <div class="character-image">
                ${imageHTML}
            </div>

            <div class="character-info">

                <div class="character-name">
                    ${character.name}
                </div>

                <div class="character-title">
                    ${character.title}
                </div>

            </div>

        `;


        card.onclick = () => {

            showCharacter(index);

        };


        characterList.appendChild(card);

    }
);


/* =========================================================
   캐릭터 상세 페이지
========================================================= */

function showCharacter(index){

    const character =
        characters[index];

    const container =
        document.getElementById(
            "detailContainer"
        );


    let imageHTML = "";

    if(character.image){

        imageHTML = `
            <img
                src="${character.image}"
                alt="${character.name}"
            >
        `;

    }else{

        imageHTML = `
            <div class="no-image">
                IMAGE
            </div>
        `;

    }


    container.innerHTML = `

        <button
            class="back-button"
            onclick="go('characters')"
        >
            ← BACK TO CHARACTERS
        </button>


        <div class="detail-top">


            <div class="detail-image">

                ${imageHTML}

            </div>


            <div>

                <div class="detail-name">
                    ${character.name}
                </div>

                <div class="detail-title">
                    ${character.title}
                </div>


                <div class="profile-grid">


                    <div class="profile-box">

                        <div class="profile-label">
                            AGE
                        </div>

                        <div class="profile-value">
                            ${character.age}
                        </div>

                    </div>


                    <div class="profile-box">

                        <div class="profile-label">
                            GENDER
                        </div>

                        <div class="profile-value">
                            ${character.gender}
                        </div>

                    </div>


                    <div class="profile-box">

                        <div class="profile-label">
                            PERSONALITY
                        </div>

                        <div class="profile-value">
                            ${character.personality}
                        </div>

                    </div>


                    <div class="profile-box">

                        <div class="profile-label">
                            TITLE
                        </div>

                        <div class="profile-value">
                            ${character.title}
                        </div>

                    </div>


                </div>


                <div class="detail-likes">


                    <div class="like-box">

                        <h4>
                            LIKES
                        </h4>

                        <p>
                            ${character.like}
                        </p>

                    </div>


                    <div class="dislike-box">

                        <h4>
                            DISLIKES
                        </h4>

                        <p>
                            ${character.dislike}
                        </p>

                    </div>


                </div>


            </div>


        </div>

    `;


    go("characterDetail");

}


/* =========================================================
   클릭 시 별가루 효과
========================================================= */

document.addEventListener(
    "click",
    function(event){

        for(let i = 0; i < 5; i++){

            const star =
                document.createElement(
                    "div"
                );

            star.className =
                "click-star";


            star.style.left =
                event.clientX + "px";

            star.style.top =
                event.clientY + "px";


            const x =
                (Math.random() - .5) * 80;

            const y =
                (Math.random() - .5) * 80;


            star.style.setProperty(
                "--x",
                x + "px"
            );

            star.style.setProperty(
                "--y",
                y + "px"
            );


            document.body.appendChild(
                star
            );


            setTimeout(
                () => {

                    star.remove();

                },
                800
            );

        }

    }
);

</script>

</body>
</html>
