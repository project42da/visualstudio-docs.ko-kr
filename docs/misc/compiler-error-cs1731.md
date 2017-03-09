---
title: "컴파일러 오류 CS1731 | Microsoft Docs"
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
  - "CS1731"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1731"
ms.assetid: 267b32aa-a692-4a54-8654-0540ee36c0a0
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1731
블록의 반환 형식 중 일부를 암시적으로 대리자 반환 형식으로 변환할 수 없으므로 'expression'을 대리자로 변환할 수 없습니다.  
  
 이 오류는 람다 식 또는 무명 메서드에 대리자의 반환 형식과 호환되지 않는 반환 형식이 있을 때 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  대리자 또는 식의 반환 형식을 변경합니다.  
  
## 예제  
 다음 코드에서는 CS1731을 생성합니다.  
  
```  
class CS1731 { delegate double D(); D d = () => { return "Who knows the real sword of Gryffindor?"; }; }  
```