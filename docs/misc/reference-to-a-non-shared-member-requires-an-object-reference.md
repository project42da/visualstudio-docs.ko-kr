---
title: "공유되지 않는 멤버에 대한 참조에 개체 참조가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30469"
  - "vbc30469"
helpviewer_keywords: 
  - "BC30469"
ms.assetid: af503e8b-2e1f-4f91-a07f-b1ddd73dd4a6
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 공유되지 않는 멤버에 대한 참조에 개체 참조가 필요합니다.
코드 내에서 공유되지 않은 멤버를 참조했으며 개체 참조를 제공하지 못했습니다. 클래스 이름 자체를 사용하여 공유되지 않은 멤버를 한정할 수는 없습니다. 인스턴스는 먼저 개체 변수로 선언된 다음 변수 이름으로 참조되어야 합니다.  
  
 **오류 ID:** BC30469  
  
### 이 오류를 해결하려면  
  
1.  인스턴스를 개체 변수로 선언합니다.  
  
2.  변수 이름으로 인스턴스를 참조합니다.  
  
## 참고 항목  
 [빌드에 없음: 클래스 이해](http://msdn.microsoft.com/ko-kr/cc2355a2-cb98-4353-9440-736585aec46c)   
 [빌드에 없음: Visual Basic의 공유 멤버](http://msdn.microsoft.com/ko-kr/dbc3783f-83a2-4225-995d-c2d6d025663d)   
 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)   
 [NOTINBUILD: 여러 변수에 동일한 이름이 있는 경우 참조 확인](http://msdn.microsoft.com/ko-kr/9601e39f-1911-44e1-ace5-3f6e090408b9)