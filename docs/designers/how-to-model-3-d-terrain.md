---
title: "방법: 3차원 지형 모델 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f779b1fd-82a9-4a11-8ab7-c1c9caabc883
caps.latest.revision: 17
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: 3차원 지형 모델 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 문서에서는 3차원 지형 모델을 만들기 위해 모델 편집기를 사용하는 방법을 설명합니다.  
  
 이 문서는 다음과 같은 활동을 보여줍니다.  
  
-   장면에 개체 추가  
  
-   면과 점을 선택합니다.  
  
-   선택 영역 변환  
  
-   **Subdivide face** 도구를 사용합니다.  
  
-   디자인 화면에 개체 프레이밍  
  
## 3\-D 지형 모델 만들기  
 평면을 세분화하여 추가 면을 만든 다음 꼭지점을 조작하여 흥미로운 지형 특징을 만들어 3\-D 지형을 만들 수 있습니다.  
  
 작업을 마치면 작성된 모델은 다음과 비슷합니다.  
  
 ![지형 모델을 보여 주는 3D 장면](../designers/media/digit-terrain-model.png "Digit\-Terrain\-Model")  
  
 시작하기 전에 **속성** 창과 **도구상자** 가 표시되는지 확인하십시오.  
  
#### 3차원 지형 모델을 만들려면  
  
1.  3 차원 모델에 맞게 만듭니다.  모델을 프로젝트에 추가하는 방법에 대한 내용은 [모델 편집기](../designers/model-editor.md)의 시작 단원을 참조하십시오.  
  
2.  장면으로 평면을 추가 합니다.  **도구 상자**의 **모양** 아래에서 **평면**을 선택하고 디자인 화면으로 이동합니다.  
  
    > [!TIP]
    >  작업이 쉽도록 평면 개체를 만들려면 디자인 화면에서 프레임 처리합니다.  **선택** 모드에서 평면 개체를 선택한 다음 모델 편집 도구상자에서, **프레임 개체** 단추를 선택합니다.  
  
3.  표면 선택 모드로 변경합니다.  모델 편집기 도구 모음에서, **표면 선택**을 선택합니다.  
  
4.  평면을 세분화합니다.  표면 선택 모드에서, 비행기를 정품인증으로 활성화시키기 위해 한번 선택하고, 앞면 선택을 위해 다시 선택합니다.  모델 편집기 도구 모음에서, **표면 분할**을 선택합니다.  동일 크기의 4개의 파티션으로 분할하는 평면에 새 정점을 추가 합니다.  
  
5.  자세한 세부 영역을 만듭니다.  새 표면이 선택되었으면, **표면 분할** 을 두 번 더 선택합니다.  총 64개의 면이 만들어집니다.  추가 하위 영역을 만들어 지형을 보다 자세히 제공할 수 있습니다.  
  
6.  점 선택 모드로 변경합니다.  모델 편집기 도구 모음에서, **점 선택**을 선택합니다.  
  
7.  지형 기능을 만들기 위해 점을 수정합니다.  점 선택 모드에서, 포인트 중 하나를 선택한 다음 모델 편집기 도구 모음에서 **변환** 도구를 선택합니다.  점을 나타내는 상자가 설계 표면에 나타납니다.  녹색 화살표를 사용하여 상자를 이동하므로 점의 높이가 수정됩니다.  흥미로운 지형 기능을 만들기 위해 다른 지점에 대해 이 단계를 반복합니다.  
  
    > [!TIP]
    >  여러 점을 한 번에 선택하여 일관된 방식으로 수정할 수 있습니다.  
  
 지형 모델을 완료 되었습니다.  다음은 최종 모델 다시 Phong 음영 적용입니다.  
  
 ![지형 모델을 보여 주는 3D 장면](../designers/media/digit-terrain-model.png "Digit\-Terrain\-Model")  
  
 이 지형 모델을 사용하여 [방법: 기하 도형 기반 그라데이션 셰이더 만들기](../designers/how-to-create-a-geometry-based-gradient-shader.md)에서 설명하는 그라데이션 셰이더의 효과를 보여줄 수 있습니다.  
  
## 참고 항목  
 [모델 편집기](../designers/model-editor.md)