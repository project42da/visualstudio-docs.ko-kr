---
title: "The project file &#39;&lt;filename&gt;&#39; cannot be updated | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.UpgradeErrors"
ms.assetid: ecd1e161-c51c-4aaa-ab80-8fc443bdad81
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# The project file &#39;&lt;filename&gt;&#39; cannot be updated
이전 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 만든 프로젝트를 열려고 했습니다.  프로젝트를 현재 형식으로 업데이트해야 하지만, 지정한 프로젝트 파일\(.vbproj\)이 읽기 전용으로 표시되어 있거나 파일이 소스 컨트롤 아래에 있고 현재 다른 사용자에 의해 잠겨 있기 때문에 업데이트할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  파일 탐색기에서 지정 된 프로젝트 파일을 찾습니다.  
  
2.  **파일** 메뉴에서 **속성**을 선택합니다.  
  
3.  **속성** 대화 상자에서 **읽기 전용** 특성의 선택을 취소합니다.  
  
 파일이 소스 코드 컨트롤 아래에 있고 다른 사용자에 의해 잠겨 있으면 파일을 사용할 수 있을 때까지 기다렸다가 로컬로 체크 아웃합니다.  
  
## 참고 항목  
 [NIB: Project Properties \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)