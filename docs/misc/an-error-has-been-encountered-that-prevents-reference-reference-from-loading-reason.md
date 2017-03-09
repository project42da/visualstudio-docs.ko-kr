---
title: "An error has been encountered that prevents reference &#39;reference&#39; from loading. &lt;reason&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.reference_load_error"
ms.assetid: 0e922611-197b-4607-bc31-03f80bd3e7e1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# An error has been encountered that prevents reference &#39;reference&#39; from loading. &lt;reason&gt;
프로젝트 파일에서 참조를 제거할 때 심각한 오류가 발생했습니다.  이 오류가 발생한 이유는 \<reason\>에 설명되며, 다음과 같습니다.  
  
-   참조에 대한 GUID 형식이 잘못되었습니다.  COM 참조에만 해당됩니다.  
  
-   래퍼 도구가 잘못되었습니다.  현재 래퍼 도구 속성은 tlbimp, aximp, primary 중 하나입니다.  COM 참조에만 해당됩니다.  
  
-   프로젝트 참조 문자열이 잘못되었습니다.  프로젝트 대 프로젝트 참조에만 해당됩니다.  
  
 **이 오류를 해결하려면**  
  
-   프로젝트에 참조를 추가하여 이 오류를 해결하십시오.  
  
     이 진단 정보가 표시된 참조는 프로젝트에 로드되지 않습니다.  
  
## 참고 항목  
 [NIB: Project Properties \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)