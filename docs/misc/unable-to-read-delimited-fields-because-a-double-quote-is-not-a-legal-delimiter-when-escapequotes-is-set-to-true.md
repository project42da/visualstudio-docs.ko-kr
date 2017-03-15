---
title: "EscapeQuotes가 True로 설정되어 있으면 큰따옴표가 올바른 구분 기호가 아니므로 구분된 필드를 읽을 수 없습니다. | Microsoft Docs"
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
  - "vbrTextFieldParser_IllegalDelimiter"
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# EscapeQuotes가 True로 설정되어 있으면 큰따옴표가 올바른 구분 기호가 아니므로 구분된 필드를 읽을 수 없습니다.
`TextFieldParser`는 따옴표\("\)가 구분 기호로 제공되고 `EscapeQuotes`가 `True`로 설정되므로 파일에서 읽을 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   `EscapeQuotes`를 `False`로 설정합니다.  
  
## 참고 항목  
 [TextFieldParser.SetDelimiters 메서드](http://msdn.microsoft.com/ko-kr/21fa40ec-5866-4d0e-9fd9-c708a190dcc9)   
 [TextFieldParser.Delimiters 속성](http://msdn.microsoft.com/ko-kr/4eb18f4d-3011-40a9-b668-be93eed0444f)   
 [How to: Read From Comma\-Delimited Text Files](../Topic/How%20to:%20Read%20From%20Comma-Delimited%20Text%20Files%20in%20Visual%20Basic.md)   
 [TextFieldParser Object](/dotnet/visual-basic/language-reference/objects/textfieldparser-object)