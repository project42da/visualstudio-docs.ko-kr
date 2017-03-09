---
title: "&#39;&lt;filename&gt;&#39; 파일에 대한 참조를 생성할 수 없습니다(TLBIMP 유틸리티를 사용하여 COM DLL 참조). &lt;error message&gt; | Microsoft Docs"
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
  - "vbc30142"
  - "bc30142"
helpviewer_keywords: 
  - "BC30142"
ms.assetid: ee0f2c77-3714-4ec2-bddf-d098ab77722f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;filename&gt;&#39; 파일에 대한 참조를 생성할 수 없습니다(TLBIMP 유틸리티를 사용하여 COM DLL 참조). &lt;error message&gt;
[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러가 어셈블리 링커\(Al.exe, Alink라고도 함\)를 호출하여 매니페스트를 사용해 어셈블리를 생성합니다. 링커가 COM\+ DLL 파일의 유효성 검사 또는 오류 발생을 보고했습니다.  
  
 **오류 ID:** BC30142  
  
### 이 오류를 해결하려면  
  
1.  따옴표 붙은 오류 메시지를 파악한 다음 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/ko-kr/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) 항목에서 추가 설명과 권장 사항을 확인합니다.  
  
2.  원하는 참조가 COM\+ DLL이 아닌 COM DLL인 경우 [Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)를 사용하여 참조를 생성합니다.  
  
3.  오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.  
  
## 참고 항목  
 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Al.exe 도구 오류 및 경고](http://msdn.microsoft.com/ko-kr/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [PAVEOVER 제품 기술 지원 및 접근성](http://msdn.microsoft.com/ko-kr/14e1d293-7b6d-40a6-bf3e-a92f8ee6c88c)