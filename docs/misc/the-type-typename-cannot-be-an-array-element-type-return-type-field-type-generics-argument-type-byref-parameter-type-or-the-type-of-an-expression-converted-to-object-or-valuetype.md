---
title: "&#39;&lt;typename&gt;&#39; 형식은 배열 요소 형식, 반환 형식, 필드 형식, 제네릭 인수 형식, &#39;ByRef&#39; 매개 변수 형식 또는 &#39;Object&#39;나 &#39;ValueType&#39;으로 변환된 식의 형식일 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31396"
  - "BC31396"
helpviewer_keywords: 
  - "BC31396"
ms.assetid: 56998a2c-a705-482e-87ee-5eff707f8a48
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식은 배열 요소 형식, 반환 형식, 필드 형식, 제네릭 인수 형식, &#39;ByRef&#39; 매개 변수 형식 또는 &#39;Object&#39;나 &#39;ValueType&#39;으로 변환된 식의 형식일 수 없습니다.
식에서 변수, 프로시저 매개 변수, 형식 매개 변수, 함수 반환 또는 배열을 제한된 형식으로 선언합니다.  
  
 CLR\(공용 언어 런타임\)에서 특수한 언어 지원을 위해 특정 형식을 노출하는데 이러한 형식은 응용 프로그램에서 데이터 형식으로 사용될 수 없습니다. 이러한 형식에는 <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle> 및 <xref:System.TypedReference> 구조체가 포함됩니다.  
  
 **오류 ID:** BC31396  
  
### 이 오류를 해결하려면  
  
-   선언된 데이터 형식으로 제한된 구조체를 사용하지 마세요.  
  
## 참고 항목  
 <xref:System.ArgIterator>   
 <xref:System.RuntimeArgumentHandle>   
 <xref:System.TypedReference>