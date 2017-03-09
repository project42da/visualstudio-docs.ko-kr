---
title: "매개 변수 값이 동일하더라도 이 프로젝트에서 &#39;&lt;attributename&gt;&#39; 특성을 두 번 이상 지정할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc41000"
  - "vbc41000"
helpviewer_keywords: 
  - "BC41000"
ms.assetid: 7e846177-7b89-44da-8f17-cdc8606ef148
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 매개 변수 값이 동일하더라도 이 프로젝트에서 &#39;&lt;attributename&gt;&#39; 특성을 두 번 이상 지정할 수 없습니다.
사용자 지정 특성이 동일한 프로그래밍 요소에 두 번 이상 지정되었지만 <xref:System.AttributeUsageAttribute>가 사용자 지정 특성에 적용되었으며 해당 <xref:System.AttributeUsageAttribute.AllowMultiple%2A> 속성이 `False`로 설정되었습니다.<xref:System.AttributeUsageAttribute.AllowMultiple%2A>은 특성이 다중 사용인지 여부를 제어합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC41000  
  
### 이 오류를 해결하려면  
  
-   사용자 지정 특성의 추가 사양을 제거하거나 <xref:System.AttributeUsageAttribute>를 적용하여 <xref:System.AttributeUsageAttribute.AllowMultiple%2A>을 `True`로 설정합니다.  
  
## 참고 항목  
 <xref:System.AttributeUsageAttribute>   
 <xref:System.AttributeUsageAttribute.AllowMultiple%2A>   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)