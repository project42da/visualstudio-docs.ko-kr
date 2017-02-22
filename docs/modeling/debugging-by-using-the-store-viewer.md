---
title: "저장소 뷰어를 사용하여 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어, 저장소"
  - "도메인별 언어, 저장소 뷰어"
ms.assetid: 0178db2e-ae99-4ed3-9b87-8620fa9fa8e4
caps.latest.revision: 17
caps.handback.revision: 17
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 저장소 뷰어를 사용하여 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

저장소 뷰어를 사용 하면 상태를 검사할 수 있습니다에  *저장소*  사용 하는 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)].  저장소 뷰어 요소 속성 및 요소 사이 대 한 링크와 함께 특정 저장소에는 도메인 모델 요소를 모두 표시 합니다.  
  
## 열기 저장소 뷰어  
 있을 때에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 실험 구축, 저장소 인스턴스 모델 정보가 들어 있는 코드는 중단점에서 중지 합니다. 그런 다음에 다음 명령을 입력 하 여 저장소 뷰어를 엽니다의  **직접 실행** 창:  
  
```  
Microsoft.VisualStudio.Modeling.Diagnostics.StoreViewer.Show(mystore);  
```  
  
> [!NOTE]
>  경로 `mystore` 저장소 인스턴스 이름입니다.  또한 네임 스페이스를 코드에 추가 하는 경우 저장소 뷰어 없이 정규화 된 네임 스페이스를 표시 하는 명령을 입력할 수 있습니다.  
>   
>  `using Microsoft.VisualStudio.Modeling.Diagnostics;`  
>   
>  `…`  
>   
>  `StoreViewer.Show(mystore);`  
  
 `Show` 메서드에는 여러 오버로드가 있습니다.  저장소 또는 파티션 인스턴스를 매개 변수로 지정할 수 있습니다.  
  
 대 안으로 코드의 아무 곳 이나 저장소 뷰어를 표시 하는 코드 줄을 넣을 수 있습니다 위치를 전달 하는 매개 변수는 `Show` 메서드 범위에 있습니다.  코드 줄에는 저장소의 내용을 스냅샷으로 실행 될 때이 작업을 저장할 뷰어를 표시 합니다.  
  
### 저장소 뷰어를 사용 하 여  
 저장소 뷰어를 열 때 모덜리스 Windows Forms 창, 다음 그림과 같이 표시 됩니다.  
  
 ![](../modeling/media/storeviewer2.png "storeviewer2")  
저장소 뷰어  
  
 저장소 뷰어 세 가지 창이 있습니다: 왼쪽 창과 오른쪽 창에서 오른쪽 아래 창입니다.  왼쪽된 창의 트리 뷰 형식으로 되어 있는 `DomainDataDirectory` 저장소 구성원.  파티션 노드를 확장 하 고 요소를 클릭 하면 요소의 등록 정보는 오른쪽 창에 표시 됩니다.  요소의 다른 요소에 연결 된 경우, 추가 요소 오른쪽 창에 표시 됩니다.  오른쪽 아래 창에서 요소를 두 번 클릭 하면 요소의 왼쪽된 창에서 강조 표시 됩니다.  
  
## 참고 항목  
 [프로그램 코드에서 모델 탐색 및 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)