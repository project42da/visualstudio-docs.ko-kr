---
title: "&#39;&lt;typename&gt;&#39; 형식을 포함하는 &#39;&lt;assemblyidentity&gt;&#39; 어셈블리에 대한 참조가 필요하지만 순환 참조가 발생할 수 있으므로 적합한 참조를 찾을 수 없습니다. &lt;referencedependencylist&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30962"
  - "vbc30962"
helpviewer_keywords: 
  - "BC30962"
ms.assetid: 6f338158-bfb4-4cc0-bbf7-1111c708613c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식을 포함하는 &#39;&lt;assemblyidentity&gt;&#39; 어셈블리에 대한 참조가 필요하지만 순환 참조가 발생할 수 있으므로 적합한 참조를 찾을 수 없습니다. &lt;referencedependencylist&gt;
식은 프로젝트 외부에 정의된 클래스, 구조체, 인터페이스, 열거형 또는 대리자와 같은 형식을 사용합니다. 그러나 해당 어셈블리에 대한 프로젝트 참조가 순환 참조 집합의 일부입니다.  
  
 여러 프로젝트 간에 참조가 있는 경우 참조가 *순환*될 수 있습니다. 예를 들어 두 프로젝트에 서로에 대한 참조가 있을 수 있습니다. 보다 일반적으로, 한 프로젝트에서 다음 프로젝트로의 참조 체인이 최종적으로 시작 프로젝트로 돌아갈 수 있습니다. 이러한 경우 체인의 끝에 참조를 확인할 수 있는 최종 프로젝트가 없습니다.  
  
 다른 어셈블리에 정의된 형식에 액세스하려면 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러에 해당 어셈블리에 대한 참조가 있어야 합니다. 이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.  
  
 **오류 ID:** BC30962  
  
### 이 오류를 해결하려면  
  
-   프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리를 생성하는 프로젝트에 대한 직접 참조를 추가합니다.  
  
## 참고 항목  
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB: 네임스페이스 및 구성 요소 참조](http://msdn.microsoft.com/ko-kr/568fa759-796b-44cd-bf5e-1cf8de6e38fd)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)