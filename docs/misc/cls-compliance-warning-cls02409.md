---
title: "CLS 규격 경고 CLS02409 | Microsoft Docs"
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
  - "CLS02409"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS02409"
ms.assetid: 71d566ce-59c2-4d3d-97ff-72f4e9bd21ee
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS02409
속성의 getter 및 setter 메서드를 구현하는 메서드는 메타데이터에서 SpecialName으로 표시됩니다.  
  
 속성의 getter 및 setter 메서드를 구현하는 메서드가 메타데이터에서 **specialname**으로 표시되지 않았습니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 함수 선언\(MSIL 어셈블리 언어 사용\)에서는 CLS02409를 발생시키는 원인을 보여 줍니다.  
  
```  
.method public instance int32 get_MyProperty() cil managed  
```  
  
 **specialname** 키워드를 추가하면 다음 경고를 해결할 수 있습니다.  
  
```  
.method public specialname instance int32 get_MyProperty() cil managed  
```