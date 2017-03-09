---
title: "제네릭 매개 변수 제약 조건 형식 &lt;typename&gt;이 CLS 규격이 아닙니다. | Microsoft Docs"
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
  - "bc40040"
  - "vbc40040"
helpviewer_keywords: 
  - "BC40040"
ms.assetid: c640dd59-56a9-43ed-b199-32a60f7b9b06
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제네릭 매개 변수 제약 조건 형식 &lt;typename&gt;이 CLS 규격이 아닙니다.
제네릭 형식이 `<CLSCompliant(True)>`로 표시되었지만 해당 형식 매개 변수 중 하나의 제약 조건에서 `<CLSCompliant(False)>`으로 표시되었거나, 표시되지 않았거나, 비규격 형식이므로 사용할 수 없는 형식을 지정합니다.  
  
 형식이 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\(CLS\) 규격이 되려면 CLS 규격 형식만 사용해야 합니다. 이는 제네릭 형식의 형식 매개 변수에 대한 제약 조건에 적용됩니다.  
  
 다음 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 데이터 형식은 CLS 규격이 아닙니다.  
  
-   [SByte Data Type](/dotnet/visual-basic/language-reference/data-types/sbyte-data-type)  
  
-   [UInteger Data Type](/dotnet/visual-basic/language-reference/data-types/uinteger-data-type)  
  
-   [ULong Data Type](/dotnet/visual-basic/language-reference/data-types/ulong-data-type)  
  
-   [UShort Data Type](/dotnet/visual-basic/language-reference/data-types/ushort-data-type)  
  
 <xref:System.CLSCompliantAttribute> 특성을 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute>를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)를 참조하세요.  
  
 **오류 ID:** BC40040  
  
### 이 오류를 해결하려면  
  
-   제네릭 형식이 이 특정 형식으로 제한된 형식 매개 변수를 사용해야 하는 경우 <xref:System.CLSCompliantAttribute>를 제거합니다. 형식은 CLS 규격일 수 없습니다.  
  
-   제네릭 형식이 CLS 규격이어야 하는 경우 이 제약 조건의 형식을 가장 가까운 CLS 규격 형식으로 변경합니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer`을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger`를 `Long`으로 바꿀 수 있습니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [\<PAVE OVER\> CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)