---
title: "방법: 3차원 모델의 피벗 점 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c20b4ec8-29f5-4ca5-bc39-d4548ca6f573
caps.latest.revision: 14
caps.handback.revision: 14
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
---
# 방법: 3차원 모델의 피벗 점 수정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

모델 편집기를 사용하여 수정하는 방법은 이 문서에서 *피벗 지점* 3 차원 모델입니다.  피벗 지점은 회전 및 크기 조정에 대한 수학적 중심을 정의하는 공간의 지점입니다.  
  
 이 문서는 다음과 같은 활동을 보여줍니다.  
  
-   개체의 피벗 점 수정  
  
## 3 차원 모델의 피벗 포인트를 수정합니다.  
 3 차원 모델의 원점을 해당 피벗 포인트를 수정하여 재정의할 수 있습니다.  
  
 **속성** 창과 **도구 상자**가 표시되는지 확인하십시오.  
  
#### 3차원 모델의 피벗 점 수정하기  
  
1.  [방법: 기본 3차원 모델 만들기](../designers/how-to-create-a-basic-3-d-model.md)에 설명된 것과 같은 기존 3D 모델로 시작합니다.  
  
2.  피벗 모드로 변경합니다.  **모델 편집 모드** 도구 모음에서, **피벗 모드** 단추를 선택하여 피벗 모드를 활성화합니다.  **피벗 모드** 단추 주위에 표시되는 상자는 모델 편집기가 현재 피벗 모드에 있음을 나타냅니다.  피벗 모드에서 변환과 같은 동작은 공간에서의 개체 구조 대신에 물체의 피벗점에 영향을 줍니다.  
  
3.  개체의 피벗 점을 수정합니다.  **선택** 모드에서 개체를 선택한 다음 **모델 뷰어** 도구 모음에서 **변환** 도구를 선택합니다.  피벗 점을 나타내는 상자가 설계 표면에 나타납니다.  상자를 이동하여 개체의 피벗 점을 수정합니다.  
  
     상자를 이동하여 피벗 점을 모두 세 방향으로 이동할 수 있습니다.  한 축을 따라 피벗 점을 변환하려면 해당 축에 해당하는 화살표를 이동합니다.  변환의 영향을 받는 축을 표시하기 위해 상자와 화살표가 노란색으로 변경됩니다.  
  
     **속성** 창의 **피벗 변환** 속성을 사용하여 피벗 점을 지정할 수도 있습니다.  
  
    > [!TIP]
    >  개체를 회전하여 새로운 피벗의 효과를 볼 수 있습니다.  회전하려면 **회전** 도구를 사용하거나 **회전** 속성을 수정합니다.  
  
 여기에 수정된 피벗 점이 있는 모델이 있습니다.  
  
 ![수정된 피벗 점이 있는 집 모델](../designers/media/digit-modified-model.png "Digit\-Modified\-Model")  
  
## 참고 항목  
 [방법: 기본 3차원 모델 만들기](../designers/how-to-create-a-basic-3-d-model.md)   
 [모델 편집기](../designers/model-editor.md)