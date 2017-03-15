---
title: "방법: 기본 3차원 모델 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a0d97966-2df8-449b-a8cf-5a19684dc773
caps.latest.revision: 18
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
caps.handback.revision: 18
---
# 방법: 기본 3차원 모델 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 문서에서는 기본 3차원 지형 모델을 만들기 위해 모델 편집기를 사용하는 방법을 설명합니다.  
  
 이 문서는 다음과 같은 활동을 보여줍니다.  
  
-   장면에 개체 추가  
  
-   면 및 가장자리 선택  
  
-   선택 영역 변환  
  
-   **표면 분할** 및 **표면 압출** 도구상자를 사용합니다.  
  
-   **3각 측량** 명령어를 사용합니다.  
  
## 기본 3D 모델 만들기  
 모델 편집기를 게임 또는 응용프로그램에 대한 3차원 모델과 장면을 수정하고 생성하기 위해 사용할 수 있습니다.  다음 단계는 편집기를 사용하는 모델 하우스의 단순화 된 3 차원 모델을 만드는 방법을 보여 줍니다.  여전히 만들어지고 있는 충돌 감지에 대한 메쉬 또는 표시되는 개체보다 자세한 렌더링에서 이익이 멀어질 때 사용 되는 상세도가 낮은 모델은 최종 예술 애셋에서 단순화된 모델로서 사용할 수 있습니다.  
  
 작업을 마치면, 작성된 모델은 다음과 비슷합니다.  
  
 ![완료된 간이형 집 모델](../designers/media/gfx_model_demo_house_final.png "gfx\_model\_demo\_house\_final")  
  
 시작하기 전에 **속성** 창과 **도구상자** 가 표시되는지 확인하십시오.  
  
#### 하우스의 단순화 된 3 차원 모델을 만듭니다.  
  
1.  3 차원 모델에 맞게 만듭니다.  모델을 프로젝트에 추가하는 방법에 대한 내용은 [모델 편집기](../designers/model-editor.md)의 시작 단원을 참조하십시오.  
  
2.  장면에 큐브를 추가 합니다.  **도구 상자** 창의 **모양** 아래에서 **큐브** 를 선택하고 그때, 디자인 화면으로 이동합니다.  
  
3.  얼굴 선택 영역으로 전환 합니다.  모델 편집기 도구 모음에서, **표면 선택**을 선택합니다.  
  
4.  큐브의 위를 세분화 합니다.  표면 선택 모드에서, 큐브는 두 번 정품 인증을 선택하고, 맨 윗면을 선택 하려면 큐브를 선택 합니다.  모델 편집기 도구 모음에서, **표면 분할**을 선택합니다.  동일 크기의 4개의 파티션으로 분할하는 큐브의 맨 위에 새 정점을 추가 합니다.  
  
     ![정육면체의 위쪽이 나뉨](../designers/media/gfx_model_demo_house_subdiv.png "gfx\_model\_demo\_house\_subdiv")  
  
5.  큐브의 두 인접 한 면을 돌출시킵니다\-예를 들어, 전면 및 좌우 큐브입니다.  얼굴 선택 모드에서 큐브 선택 활성화 한 다음 한쪽 큐브를 한 번 선택 합니다.  컨트롤 키를 누르고 유지합니다, 처음 선택한 면의 인접한 큐브의 다른 면을 선택합니다, 그리고 모델 편집기 도구상자에서 **표면 돌출**을 선택합니다.  
  
     ![정육면체의 양쪽 면이 돌출됨](../designers/media/gfx_model_demo_house_extrude.png "gfx\_model\_demo\_house\_extrude")  
  
6.  돌출 중 하나를 확장 합니다.  돌출된 면중 하나를 선택합니다, 그때 모델 편집기 도구상자에서, **변환** 도구상자를 선택하고 돌출로서 동일한 방향으로 변환 조작자를 이동합니다.  
  
     ![정육면체의 한쪽 면이 더 돌출됨](../designers/media/gfx_model_demo_house_extend.png "gfx\_model\_demo\_house\_extend")  
  
7.  모델은 삼각 측정 해야 합니다.  **고급** 도구 모음에서 **스크립트**, **도구**, 삼각 측량을 선택합니다.  
  
8.  집의 지붕 만들기  모델 편집기 도구상자에서 **가장자리 선택** 을 선택함으로써 가장자리 선택 모드를 전환하고 그때 큐브를 활성화하기를 선택합니다.  컨트롤 키를 누르고 여기에 표시 되는 모서리를 선택 합니다.  
  
     ![지붕 끝을 형성할 가장자리](../designers/media/gfx_model_demo_house_edges.png "gfx\_model\_demo\_house\_edges")  
  
     모델 편집기 도구 모음에서 가장자리를 선택하면 선택 된 **변환** 도구를 변환 조작자 만드는 집의 지붕 위쪽으로 이동 합니다.  
  
 완료된 간이형 집 모델  다음은 최종 모델을 다시 납작한 음영을 적용합니다.  
  
 ![완료된 간이형 집 모델](../designers/media/gfx_model_demo_house_final.png "gfx\_model\_demo\_house\_final")  
  
 다음 단계로, 셰이더가 3 차원 모델에 적용할 수 있습니다.  자세한 내용은 [방법: 3차원 모델에 셰이더 적용](../designers/how-to-apply-a-shader-to-a-3-d-model.md)를 참조하십시오.  
  
## 참고 항목  
 [방법: 3차원 지형 모델 만들기](../designers/how-to-model-3-d-terrain.md)   
 [모델 편집기](../designers/model-editor.md)   
 [셰이더 디자이너](../designers/shader-designer.md)