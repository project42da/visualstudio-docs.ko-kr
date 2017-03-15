---
title: "CLS 규격 경고 CLS02809 | Microsoft Docs"
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
  - "CLS02809"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS02809"
ms.assetid: a6e7b8e5-1587-437e-9d07-8a32fc5c4842
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS02809
속성은 특정 이름 지정 패턴을 따라야 합니다.  
  
 속성은 특정 명명 패턴을 따라야 합니다. 속성의 접근자 함수 이름은 속성 이름과 같고 앞에 **get\_** 또는 **set\_**가 추가됩니다.  
  
 **specialname** 특성은 적절한 이름 비교에서 무시되고 식별자 규칙을 따릅니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 함수 선언\(MSIL 어셈블리 언어 사용\)에서는 CLS02809를 발생시키는 원인을 보여 줍니다.  
  
```  
.method public specialname instance void set_MyPropertya(int32 __unnamed000) cil managed { } // end of method One::set_MyProperty .method public specialname instance int32 get_MyPropertya() cil managed { } // end of method One::get_MyProperty .property instance int32 MyProperty() { .get instance int32 One::get_MyPropertya() .set instance void One::set_MyPropertya(int32) } // end of property One::MyProperty  
```  
  
 접근자 메서드 이름이 속성의 이름과 다릅니다.  모든 속성 이름이 명명 패턴을 준수하는지 확인하여 CLS02809를 해결할 수 있습니다.