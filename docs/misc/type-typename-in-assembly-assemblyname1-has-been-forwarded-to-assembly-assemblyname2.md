---
title: "&#39;&lt;assemblyname1&gt;&#39; 어셈블리의 &#39;&lt;typename&gt;&#39; 형식이 &#39;&lt;assemblyname2&gt;&#39; 어셈블리로 전달되었습니다. | Microsoft Docs"
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
  - "vbc31424"
  - "bc31424"
helpviewer_keywords: 
  - "BC31424"
  - "형식 전달"
ms.assetid: 0f53e613-c1cb-4722-acb5-afa3091e277b
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;assemblyname1&gt;&#39; 어셈블리의 &#39;&lt;typename&gt;&#39; 형식이 &#39;&lt;assemblyname2&gt;&#39; 어셈블리로 전달되었습니다.
'\<assemblyname1\>' 어셈블리의 '\<typename\>' 형식이 '\<assemblyname2\>' 어셈블리로 전달되었습니다. 프로젝트에 '\<assemblyname2\>'에 대한 참조가 없거나 '\<assemblyname2\>' 어셈블리에 '\<typename\>' 형식이 없습니다.  
  
 어셈블리에 대한 소스 코드의 식이 다른 어셈블리로 전달된 형식을 참조하지만 대상 어셈블리에서 형식을 찾을 수 없습니다.  
  
 *형식 전달*은 클래스, 구조체, 인터페이스, 대리자 또는 열거형의 정의를 원래 정의한 어셈블리와 다른 어셈블리에 다시 할당하는 것을 의미합니다. 이는 어셈블리를 두 개 이상의 어셈블리로 분할하거나 코드를 다른 어셈블리로 이동하는 *코드 리팩터링*과 함께 자주 사용됩니다.  
  
 원본 어셈블리에서 일시적으로 형식을 사용할 수 있지만 코드 리팩터링을 통해 원본 어셈블리에서 제거되면 정의되지 않게 됩니다.  
  
 **오류 ID:** BC31424  
  
### 이 오류를 해결하려면  
  
-   대상 어셈블리에 형식이 있는지 확인합니다.  
  
-   프로젝트에 대상 어셈블리에 대한 참조가 있는지 확인합니다.  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>   
 [Type Forwarding \(C\+\+\/CLI\)](/visual-cpp/windows/type-forwarding-cpp-cli)   
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)