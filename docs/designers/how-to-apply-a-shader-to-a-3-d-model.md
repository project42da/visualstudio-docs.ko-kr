---
title: "방법: 3차원 모델에 셰이더 적용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a3877bd6-abd8-4a9d-842c-6848b6c2f335
caps.latest.revision: 15
caps.handback.revision: 15
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
---
# 방법: 3차원 모델에 셰이더 적용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 문서에서는 모델 편집기를 사용하여 DGSL\(Directed Graph Shader Language\) 셰이더를 3차원 모델에 적용하는 방법을 보여줍니다.  
  
 이 문서는 다음과 같은 활동을 보여줍니다.  
  
-   셰이더를 3\-D 모델에 적용  
  
## 셰이더를 3\-D 모델에 적용  
 3차원 모델에 셰이더 효과를 적용하여 흥미로운 모양을 제공할 수 있습니다.  
  
 시작하기 전에 **속성** 창과 도구 상자가 표시되는지 확인하십시오.  
  
#### 3차원 모델에 셰이더를 적용하려면  
  
1.  하나 이상의 모델을 포함 하는 3 차원 장면으로 시작 합니다.  적합 한 3 차원 장면이 없으면, 새로 생성합니다. 자세한 내용은 [방법: 기본 3차원 모델 만들기](../designers/how-to-create-a-basic-3-d-model.md)를 참조하십시오.  DGSL 셰이더 모델에 적용할 수 있을 수도 있습니다.  적합 한 셰이더를 설정 하지 않은 경우, 새로 생성합니다, 자세한 설명은 [방법: 기본 색 셰이더 만들기](../designers/how-to-create-a-basic-color-shader.md)를 참조하십시오. 그리고 저장 한 파일을 계속 작업하기 전에 저장되어 있는지 확인합니다.  
  
2.  **선택**모드에서, 셰이더를 적용시킬 모델을 선택하고 **속성** 창에서, **파일명** 속성인 **효과** 속성 그룹에서, 모델을 적용시킬 DGSL 셰이더를 지정합니다.  
  
 다음은 기본 색 효과를 적용 된 모델입니다.  
  
 ![기본 색 효과를 보여 주는 3D 장면](../designers/media/digit-3d-model-effect.png "Digit\-3D\-Model\-Effect")  
  
 셰이더 모델에 적용한 후, 셰이더 디자인에서 모델을 선택함으로써 열 수 있습니다, 그리고 **속성** 창에서, **\(고급\)** 속성인 **효과** 속성 그룹에서, 타원 단추\(**...**\) 를 선택할 수 있습니다.  
  
## 참고 항목  
 [방법: 기본 3차원 모델 만들기](../designers/how-to-create-a-basic-3-d-model.md)   
 [방법: 기본 색 셰이더 만들기](../designers/how-to-create-a-basic-color-shader.md)   
 [모델 편집기](../designers/model-editor.md)   
 [셰이더 디자이너](../designers/shader-designer.md)