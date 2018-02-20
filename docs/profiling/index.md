---
layout: LandingPage
title: "Visual Studio로 앱 프로파일링 | Microsoft Docs"
description: "Visual Studio 2017을 사용하여 원하는 언어로 응용 프로그램, 서비스 및 도구의 성능을 프로파일링하는 방법을 알아보세요."
ms.technology: vs-ide-debug
ms.openlocfilehash: fa5b65a11a1275f805644efbc6a210d51c18292d
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2018
---
# <a name="profiling-in-visual-studio"></a>Visual Studio의 프로파일링

프로파일링 및 진단 도구는 메모리 및 CPU 사용량 진단 및 응용 프로그램 수준 문제 진단을 도와줍니다. 이러한 도구를 사용하면 디버거에서 응용 프로그램을 실행하는 동안 데이터(예: 변수 값, 함수 호출, 이벤트)를 누적할 수 있습니다. 코드를 실행하는 동안 다양한 지점에서 응용 프로그램 상태를 볼 수 있습니다. 

<ul class="panelContent cardsFTitle">
    <li>
        <a href="https://docs.microsoft.com/visualstudio/profiling/profiling-feature-tour">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_road-map.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>프로파일러의 기능 둘러보기</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/profiling/beginners-guide-to-performance-profiling">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_code-performance.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>진단 도구 시작(CPU 사용량)</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Profiling-with-Diagnostics-Tools-in-Visual-Studio-2017-daHnzMD6D_9211787171">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_video.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>진단 도구에 대한 비디오 보기</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/profiling/memory-usage">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_code-performance.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>메모리 사용 분석 시작</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
        <li>
        <a href="https://docs.microsoft.com/visualstudio/profiling/application-timeline">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_get-started.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>리소스 사용 분석(XAML)</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/profiling/network-usage">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_get-started.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>네트워크 사용량 분석(UWP 앱)</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/debugger/gpu-usage">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_get-started.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>GPU 사용량 분석(Direct3D)</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/profiling/analyze-energy-use-in-store-apps">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_get-started.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>에너지 사용 분석(UWP 앱)</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/visualstudio/profiling/what-s-new-in-profiling-tools">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_whats-new.svg" alt="">
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>프로파일링 도구의 새로운 기능 살펴보기</h3>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
</ul>

---