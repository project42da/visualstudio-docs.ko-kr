---
title: "이 버전에서는 &#39;System.Runtime.InteropServices.DefaultCharSetAttribute&#39; 특성이 지원되지 않습니다. | Microsoft Docs"
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
  - "bc32510"
  - "vbc32510"
helpviewer_keywords: 
  - "BC32510"
ms.assetid: e2eec233-6e0b-4f2f-a801-b0274e579c0e
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 버전에서는 &#39;System.Runtime.InteropServices.DefaultCharSetAttribute&#39; 특성이 지원되지 않습니다.
<xref:System.Runtime.InteropServices.DefaultCharSetAttribute?displayProperty=fullName> 특성을 사용하면 마샬링된 문자열에 사용할 문자 집합을 지정할 수 있습니다. 해당 값은 <xref:System.Runtime.InteropServices.CharSet?displayProperty=fullName> 열거형의 멤버를 사용합니다.  
  
 현재 버전의 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]는 이 특성을 지원하지 않습니다. 지원은 이후 버전에서 가능합니다.  
  
 **오류 ID:** BC32510  
  
### 이 오류를 해결하려면  
  
-   각 [Declare Statement](/dotnet/visual-basic/language-reference/statements/declare-statement)을 사용하여 선언하는 외부 프로시저에 대한 문자 집합을 지정합니다. 다음은 이에 대한 예입니다.  
  
    ```  
    Ansi Declare Function GetUserName Lib "advapi32.dll" _ (ByVal lpBuffer As String, ByRef nSize As Integer) As Integer Unicode Declare Sub externalProc Lib "projectlib.dll" _ (ByVal arg As Double)  
    ```  
  
     `Declare` 문에서 문자 집합을 지정하지 않은 경우 기본값은 ANSI입니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DefaultCharSetAttribute>   
 <xref:System.Runtime.InteropServices.CharSet>   
 [빌드에 없음: Visual Basic의 특성](http://msdn.microsoft.com/ko-kr/620bfc0e-4582-4c8b-8432-ebc5c3dccc22)   
 [Declare Statement](/dotnet/visual-basic/language-reference/statements/declare-statement)