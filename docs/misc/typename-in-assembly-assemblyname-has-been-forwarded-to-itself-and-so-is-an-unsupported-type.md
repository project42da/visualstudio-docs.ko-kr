---
title: "&#39;&lt;assemblyname&gt;&#39; 어셈블리의 &#39;&lt;typename&gt;&#39;이 자신에게 전달되었습니다. 이는 지원되지 않는 형식입니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31425"
  - "vbc31425"
helpviewer_keywords: 
  - "BC31425"
  - "형식 전달"
ms.assetid: e3275d55-3f4c-4bbc-9c8f-f55c4e973063
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;assemblyname&gt;&#39; 어셈블리의 &#39;&lt;typename&gt;&#39;이 자신에게 전달되었습니다. 이는 지원되지 않는 형식입니다.
어셈블리가 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>를 사용하여 해당 형식 중 하나를 다른 어셈블리로 전달하지만 동일한 어셈블리에서 동일한 형식을 지정합니다.  
  
 *형식 전달*은 클래스, 구조체, 인터페이스, 대리자 또는 열거형의 정의를 원래 정의한 어셈블리와 다른 어셈블리에 다시 할당하는 것을 의미합니다. 이는 어셈블리를 두 개 이상의 어셈블리로 분할하거나 코드를 다른 어셈블리로 이동하는 *코드 리팩터링*과 함께 자주 사용됩니다.  
  
 자체에 형식을 전달하면 순환 전달이 발생합니다. 다른 어셈블리가 전달된 형식에 액세스하려는 경우 전달되지 않은 형식에 도착하지 않고 무한 전달됩니다.  
  
 **오류 ID:** BC31425  
  
### 이 오류를 해결하려면  
  
-   다른 어셈블리의 형식으로 형식을 전달하거나 어느 곳도 형식을 전달하지 않아야 합니다.  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>   
 [Type Forwarding \(C\+\+\/CLI\)](/visual-cpp/windows/type-forwarding-cpp-cli)   
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)