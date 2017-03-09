---
title: "컴파일러 오류 CS0040 | Microsoft Docs"
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
  - "CS0040"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0040"
ms.assetid: 6a600166-0335-4b6d-b050-6821b4624c96
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0040
디버그 정보 파일을 만드는 동안 예기치 않은 오류가 발생했습니다. 'reason'  
  
 이 오류는 [\/debug](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option) 컴파일러 옵션을 사용하는 경우에 발생할 수 있으며, 컴파일러에서 .pdb 파일에 쓸 수 없음을 나타냅니다. 이 오류를 해결하는 방법에는 Visual Studio 다시 설치, 컴파일러에 파일 또는 디렉터리에 대한 쓰기 권한이 있는지 확인, \/debug로 컴파일하지 않음 등이 포함됩니다.