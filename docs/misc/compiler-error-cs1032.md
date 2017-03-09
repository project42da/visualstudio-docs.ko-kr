---
title: "컴파일러 오류 CS1032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1032"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1032"
ms.assetid: fe318a6c-4403-4b9b-b3d8-753ec31c00ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1032
파일의 첫 토큰 뒤에 전처리기 기호를 정의\/정의 해제할 수 없습니다.  
  
 `#define` 및 `#undef` [전처리기 지시문](/dotnet/csharp/language-reference/preprocessor-directives/index)은 네임스페이스 선언에서 사용되는 것과 같이 다른 키워드 이전에 프로그램의 시작 부분에 사용해야 합니다.  
  
 다음 샘플에서는 CS1032를 생성합니다.  
  
```  
// CS1032.cs namespace x { public class clx { #define a   // CS1032, put before namespace public static void Main() { } } }  
```