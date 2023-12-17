---
layout: page
title: Home
id: home
permalink: /
---

<html lang="en">
<head>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet"> 
    <meta charset="UTF-8">
    <title>Your Company Name</title>
    <style>
        .slider {
            width: 100%;
            overflow: hidden;
        }
        .slides {
            display: flex;
            transition: transform 0.5s ease;
        }
        .slide {
            min-width: 100%;
            height: 512px;
            background-size: cover;
            background-position: center;
            position: relative; /* 텍스트 위치 조정을 위해 필요 */ 
        }
	    .slide-image { 
	     width: 50%; /* 이미지의 너비를 50%로 설정 */ 
	     height: 100%; /* 슬라이드의 전체 높이 */ 
	     background-size: cover; 
	     background-position: center; 
	     margin: 0 auto; /* 가운데 정렬 */
	      position: absolute; left: 50%; 
	      transform: translateX(-50%); /* 정중앙 정렬 */ 
	    }
	    .fadeInOut { animation: fadeInOut 10s ease-in-out; }
@keyframes fadeInOut {
	 0% { opacity: 0; } 
	25% { opacity: 1; }
	75% { opacity: 1; } 
	100% { opacity: 0; } 
	} 
.slide-text {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: white;
    font-size: 2vw; /* 뷰포트 너비에 따라 변하는 폰트 사이즈 */
    font-family: 'Roboto', sans-serif; /* Roboto 서체 적용 */
    text-align: center;
    text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000; /* 텍스트 스트로크 효과 */
}
        .indicators {
            text-align: center;
        }
        .indicator {
            display: inline-block;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: lightgray;
            margin: 5px;
            cursor: pointer;
        }
        .active {
            background-color: darkgray;
        }
        section {
            margin: 20px;
            padding: 20px;
            background-color: #f5f5f5;
            border-radius: 10px;
        }
        h2 {
            color: #333;
        }
    </style>
</head>
<body>
    <div class="slider">
        <div class="slides">
            <div class="slide">
	            <div class="slide-image" style="background-image: url('/assets/image_main_0.png');">
	            <div class="slide-text"> 자신에 대한 신뢰 없이는<br>위대한 업적을 이룰 수 없다. </div> </div>
            </div>
            <div class="slide">
	            <div class="slide-image" style="background-image: url('/assets/image_main_1.png');">
	            <div class="slide-text">나는 인간이라는 것보다<br>위대한 것을 알지 못한다.</div> </div>
            </div>
            <div class="slide">
	            <div class="slide-image" style="background-image: url('/assets/image_main_2.png');">
	            <div class="slide-text">인간은 자신이<br>이해할 수 있는 것에<br>대해서만 진실을 찾는다.</div> </div>
            </div>
            <div class="slide">
	            <div class="slide-image" style="background-image: url('/assets/image_main_3.png');">
	            <div class="slide-text"> 정신적으로 강한 자만이<br>고독을 즐길 수 있다. </div> </div>
            </div>
        </div>
        <div class="indicators">
            <span class="indicator active"></span>
            <span class="indicator"></span>
            <span class="indicator"></span>
            <span class="indicator"></span>
        </div>
    </div>

    <section id="about">
        <h2>Notice</h2>
        <p>Hello World~~</p>
    </section>

<script>
    let currentSlide = 0;
    const slides = document.querySelectorAll(".slide");
    const indicators = document.querySelectorAll(".indicator");

    function updateSlide() {
        let slideWidth = slides[0].offsetWidth;
        document.querySelector(".slides").style.transform = `translateX(-${currentSlide * slideWidth}px)`;

        // 인디케이터 업데이트
        indicators.forEach(ind => ind.classList.remove("active"));
        indicators[currentSlide].classList.add("active");

        // 텍스트 애니메이션 리셋 및 재시작
        const currentText = slides[currentSlide].querySelector(".slide-text");
        if (currentText) {
            currentText.classList.remove("fadeInOut");
            // 애니메이션을 다시 시작하기 위해 브라우저에 리플로우를 강제함
            void currentText.offsetWidth;
            currentText.classList.add("fadeInOut");
        }
    }

    function nextSlide() {
        currentSlide = (currentSlide + 1) % slides.length;
        updateSlide();
    }

    setInterval(nextSlide, 10000); // 10초마다 슬라이드 변경

    indicators.forEach((indicator, idx) => {
        indicator.addEventListener("click", () => {
            currentSlide = idx;
            updateSlide();
        });
    });

    // 초기 로딩시 첫 슬라이드에 애니메이션 적용
    if (slides.length > 0 && slides[0].querySelector(".slide-text")) {
        slides[0].querySelector(".slide-text").classList.add("fadeInOut");
    }
</script>


</body>
</html>
