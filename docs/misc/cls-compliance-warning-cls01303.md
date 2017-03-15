---
title: "CLS 규격 경고 CLS01303 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLS01303"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS01303"
ms.assetid: a8aa0cda-a2dd-41da-bcc2-53221207ea70
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS01303
CLS 규격 리터럴에는 리터럴\(또는 해당 리터럴이 enum인 경우 기본 형식\)과 정확히 같은 필드 초기화 메타데이터에 지정된 값이 있어야 합니다.  
  
 리터럴 정적 값은 필드 초기화 메타데이터를 사용하여 지정됩니다. CLS 규격 리터럴에는 리터럴\(또는 해당 리터럴이 enum인 경우 기본 형식\)과 정확히 같은 필드 초기화 메타데이터에 지정된 값이 있어야 합니다.  
  
 필드 리터럴의 형식이 리터럴\(또는 리터럴이 열거형인 경우 기본 형식\)과 정확히 동일한지 확인합니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 선언\(MSIL 어셈블리 언어 사용\)에서는 CLS01303을 발생시키는 원인을 보여 줍니다.  
  
```  
.field public static literal char Field2 = int32(0x00000002)  
```  
  
 이니셜라이저의 형식을 리터럴 형식과 동일하게 지정하여 이 경고를 해결할 수 있습니다.  
  
```  
.field public static literal char Field2 = char(0x00000002)  
```