---
title: "Visual Studio용 R 도구 샘플 프로젝트 | Microsoft Docs"
ms.custom: 
ms.date: 4/26/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa52ed0e-cdb5-4fb2-814c-c94cac2ffc6f
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 7a873df77756e5a957d327049566c8e0db1f3a8a
ms.openlocfilehash: d58ff34914af9185ce5282bdc8848db2b12f1aea
ms.contentlocale: ko-kr
ms.lasthandoff: 05/12/2017

---

# <a name="r-tools-for-visual-studio-sample-projects"></a>Visual Studio용 R 도구 샘플 프로젝트

이 샘플 컬렉션을 통해 R, RTVS(Visual Studio용 R 도구) 및 Microsoft R Server 사용을 시작할 수 있습니다.

1. [샘플 zip 파일](https://github.com/Microsoft/RTVS-docs/archive/master.zip)을 다운로드하고 선택한 폴더로 추출합니다.
1. `examples/Examples.sln`을 엽니다. 프로젝트에 두 개의 폴더가 표시됩니다.

    - *R 개요*에서는 R을 처음 사용하는 사람에게 적당한 소개를 제공합니다.
    - *MRS 및 Machine Learning*에서는 기계 학습에 R 및 Microsoft R Server를 사용하는 방법의 예제를 제공합니다.

## <a name="a-first-look-at-r"></a>R 개요

이 샘플에서는 소스 파일의 폭넓은 주석을 통해 R을 자세히 소개합니다. 이러한 항목을 둘 다 경험하는 가장 좋은 방법은 파일 위쪽에 커서를 놓고 나서 Ctrl+Enter를 눌러 각 줄을 한 번에 하나씩 결과를 확인할 수 있는 **R 대화형** 창에 보내는 것입니다. 몇몇 줄은 1~2분이 걸릴 수 있는 패키지를 설치합니다.

- `1-Getting Started with R.R`에서는 패키지 사용, 데이터 로드 및 분석, 그리기를 포함한 많은 R 기본 사항을 설명합니다.

    ![1-Getting Started with R.R 샘플의 예제 출력](~/docs/rtvs/media/samples-getting-started-output.png)

- `2-Introduction to ggplot2.R`에서는 눈에 띄는 플롯 및 간단한 구문용으로 알려진 ggplot2 그래픽 패키지를 소개합니다. 이 예제에서는 Fiji의 지진 데이터를 시각화합니다.

    ![2-Introduction to ggplot2.R 샘플의 예제 출력](~/docs/rtvs/media/samples-ggplot-output.png)


## <a name="microsoft-r-server-and-machine-learning"></a>Microsoft R Server 및 Machine Learning

이 예제 컬렉션에서는 R 및 Microsoft R Server를 사용하여 기계 학습 모델을 만드는 방법과 [MRS(Microsoft R Server)](http://aka.ms/rtvs-msft-r)의 기능을 활용하는 방법을 보여 줍니다. 제목에 `MRS`가 있고 명시되어 있는 스크립트를 실행하려면 MRS를 설치해야 합니다.

모든 예제와 마찬가지로 이러한 항목을 경험하는 가장 좋은 방법은 파일을 열고, 위쪽에 커서를 놓고 나서, Ctrl+Enter를 사용하여 한 줄씩 단계별로 코드를 실행하는 것입니다. 자세한 내용은 각 폴더의 markdown 파일을 참조하세요.

- `Benchmarks`는 많은 계산 집약적인 벤치마크를 실행하여 신속한 병렬 선형 대수 계산을 위한 Microsoft R Open 및 Intel MKL(Math Kernel Library) 사용을 통해 가능한 성능상 이점을 보여 줍니다. 시뮬레이트된 데이터를 통해 특히 특정 매트릭스 관련 계산에 두 개의 스레드를 사용하는 경우와 하나의 스레드를 사용하는 경우를 비교합니다.   

    ![벤치마크 플롯 예제](~/docs/rtvs/media/samples-mro-benchmark-plot.png)

- `Bike_Rental_Estimation_with_MRS`에서는 Microsoft R Server를 사용하여 기록 데이터 집합을 기반으로 자전거 대여에 대한 수요 예측 모델을 만듭니다. 

- `Data_Exploration`에는 다음 세 개의 스크립트가 포함됩니다.  
    - `Import Data from URL.R`에서는 URL로 식별되는 데이터 파일을 R에 로드하는 방법을 보여 줍니다.
    - `Import Data from URL to xdf.R`에서는 URL로 식별되는 데이터 파일을 Microsoft R Server에 xdf로 로드하는 방법을 보여 줍니다. MRS가 필요합니다.
    - `Using ggplot2.R`는 대화형 3차원 그리기를 포함하여 ggplot2 기능의 더 다양한 둘러보기를 제공하는 `A First Look at R/2-Introduction to ggplot2.R` 샘플의 확장입니다.

        ![ggplot2.R 사용 예제 출력](~/docs/rtvs/media/samples-3d-interactive.png)

- `Datasets`에는 다른 샘플에서 사용되는 세 개의 `.csv` 파일이 포함됩니다.
- `Flight_Delays_Prediction_with_R` 및 `Flight_Delays_Prediction_with_MRS`는 R, 기계 학습 및 기록 정시 성능/날씨 데이터를 사용하여 항공 지연을 예측하는 방법을 보여 줍니다. 
- `Machine learning`에는 실제 문제에 대한 R 및 MRS 적용을 보여 주는 항공 지연, 하우징 가격 및 자전거 임대를 예측하기 위한 학습의 세 가지 샘플이 포함됩니다. 이러한 항목은 여러 가지 인기 있는 기계 학습 모델을 사용하고 [Azure Machine Learning](https://azure.microsoft.com/services/machine-learning/) 작업 영역을 통해 Azure 웹 서비스로 배포하는 방법을 보여 줍니다.

- `R_MRO_MRS_Comparison`은 R, Microsoft R Open 및 Microsoft R Server의 명령, 구문, 생성 및 성능에 대한 유사점과 차이점을 보여 주는 6개 부분 비교입니다.

## <a name="whats-special-about-microsoft-r-open-and-microsoft-r-server"></a>Microsoft R Open 및 Microsoft R Server가 특별한 점은 무엇인가요?

Microsoft의 R 배포인 [Microsoft R Open](http://aka.ms/rtvs-r-open)은 [CRAN R](https://cran.r-project.org/)와 다음과 같은 중요한 두 가지가 다릅니다.

1. [Intel Math Kernel Library](https://software.intel.com/intel-mkl)와 함께 사용될 경우 [계산 성능 향상](https://mran.revolutionanalytics.com/rro/#intelmkl1). 이러한 기능은 Microsoft R Open과 함께 사용하도록 Microsoft에서 무료 다운로드로 제공됩니다.

1. R 프로그램을 빌드하는 데 사용한 라이브러리가 항상 작업을 재현할 다른 사용자에게 제공되도록 하는 [재현 가능한 R 도구 키트](https://mran.revolutionanalytics.com/rro/#reproducibility).

[Microsoft R Server](http://aka.ms/rtvs-msft-r)는 추가 데이터를 더 빠르게 처리할 수 있도록 하는 R의 확장입니다. 이 확장은 R에 두 가지 강력한 기능을 제공합니다.

1. 더 큰 데이터 집합. MRS는 Hadoop 클러스터, 데이터베이스 및 데이터 웨어하우스를 포함한 다양한 소스에서 메모리 부족 데이터를 처리할 수 있습니다. RAM에 의해 다시 제한받을 필요가 없습니다.

1. 병렬, 다중 코어 처리. MRS는 사용 가능한 모든 계산 리소스에 걸쳐 계산을 효율적으로 분배할 수 있습니다. 개인 워크스테이션 또는 원격 클러스터에서 MRS는 답변을 더 빠르게 얻습니다.

다음 비교는 MKL이 있는 MRS 및 MRO의 특정 매트릭스 계산에 관련된 계산 성능이 MKL이 없는 R 및 MRO보다 크게 향상됨을 보여 줍니다. 시뮬레이트된 데이터는 다음 계산에서 사용됩니다.

![MKL이 있는 MRS/MRO 및 MKL이 없는 R/MRO 비교](~/docs/rtvs/media/samples-speed-comparison.png)

R과 MRO/MRS의 기술적인 비교를 위해 항목에서 [Lixun Zhang의 자세한 설명](http://htmlpreview.github.io/?https://github.com/lixzhang/R-MRO-MRS/blob/master/Introduction_to_MRO_and_MRS.html)을 확인하세요.

다음 그림은 로지스틱 회귀 모델에서 예약된 여객기의 도착이 15분 이상 지연될지 여부를 예측하는 데 사용되는 경과된 시간(초)을 비교합니다. 적은 수의 행을 줄이면 CRAN R에 사용되는 경과된 시간이 대폭 감소하지만 MRS만 2배 정도 증가합니다. 이 벤치마크에 대한 자세한 내용은 `Benchmarks/rxGlm_benchmark.R` 예제를 참조하세요.

![rxGlm 벤치마크](~/docs/rtvs/media/samples-rxGLM-benchmark.png)

