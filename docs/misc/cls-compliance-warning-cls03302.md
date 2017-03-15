---
title: "CLS 규격 경고 CLS03302 | Microsoft Docs"
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
  - "CLS03302"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS03302"
ms.assetid: 3b99e64b-d5cb-4eb8-81b5-fd96992f2c10
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS03302
이벤트는 특정 명명 패턴을 따라야 합니다.  
  
 이벤트는 특정 명명 패턴을 따라야 합니다. 이벤트의 접근자 함수 이름은 이벤트 이름과 같고 앞에 **raise\_**, **remove\_** 또는 **add\_**가 추가됩니다.  
  
 **specialname** 특성은 적절한 이름 비교에서 무시되고 식별자 규칙을 따릅니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 함수 선언\(MSIL 어셈블리 언어 사용\)에서는 CLS03302를 발생시키는 원인을 보여 줍니다.  
  
```  
.method public specialname instance void add_MyEventaaa(class MyAssemblyDelegate __unnamed000) cil managed { } // end of method One::add_MyEvent .method public specialname instance void remove_MyEventaaa(class MyAssemblyDelegate __unnamed000) cil managed { } // end of method One::remove_MyEvent .method public specialname instance void raise_MyEventaaa(object __unnamed000, class [mscorlib]System.EventArgs __unnamed001) cil managed { } // end of method One::raise_MyEvent .event specialname MyAssemblyDelegate MyEvent { .addon instance void One::add_MyEventaaa(class MyAssemblyDelegate) .removeon instance void remove_MyEventaaa(class MyAssemblyDelegate) .fire instance void raise_MyEventaaa(object, class [mscorlib]System.EventArgs) } // end of event One::MyEvent } // end of class One  
```  
  
 접근자 메서드 이름이 이벤트의 이름과 다릅니다.  모든 이벤트 접근자 이름이 명명 패턴을 준수하는지 확인하여 CLS03302를 해결할 수 있습니다.