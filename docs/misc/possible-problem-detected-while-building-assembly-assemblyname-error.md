---
title: "&#39;&lt;assemblyname&gt;&#39; 어셈블리를 빌드하는 동안 발생 가능한 문제가 발견되었습니다. &lt;error&gt; | Microsoft Docs"
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
  - "vbc40010"
  - "bc40010"
helpviewer_keywords: 
  - "BC40010"
ms.assetid: 3a4f4a4a-a5ad-4501-bf4c-0fbf25c50734
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;assemblyname&gt;&#39; 어셈블리를 빌드하는 동안 발생 가능한 문제가 발견되었습니다. &lt;error&gt;
[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러에서 호출되는 ALink 도구가 어셈블리를 빌드하는 동안 오류를 보고합니다. 가능한 원인은 다음과 같습니다.  
  
-   서명된 어셈블리가 서명되지 않은 어셈블리를 참조합니다. 이 경우 참조된 어셈블리가 보안 기준을 충족하는지 여부를 고려해야 합니다.  
  
-   32비트 플랫폼에서 64비트 응용 프로그램을 빌드합니다. 이 경우 참조된 모든 어셈블리의 64비트 버전이 대상 플랫폼에 설치되어 있는지 확인해야 합니다. CLR\(공용 언어 런타임\) 어셈블리의 경우 이 오류 메시지가 계속 생성되지만 작업이 자동으로 처리됩니다.  
  
 이 메시지는 경고입니다. 컴파일러는 계속해서 어셈블리를 생성합니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40010  
  
### 이 오류를 해결하려면  
  
1.  따옴표 붙은 오류 메시지를 검사하고 적절한 조치를 수행합니다.  
  
2.  프로그램을 다시 컴파일하여 오류가 다시 발생하는지 확인합니다.  
  
3.  그래도 오류가 다시 발생하면 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러를 다시 설치합니다.  
  
4.  다시 설치 이후에도 오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
## 참고 항목  
 [PAVEOVER 제품 기술 지원 및 접근성](http://msdn.microsoft.com/ko-kr/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)   
 [Common Language Runtime Overview](http://msdn.microsoft.com/ko-kr/0fd9aeae-af10-435f-86d4-e76619741e4a)