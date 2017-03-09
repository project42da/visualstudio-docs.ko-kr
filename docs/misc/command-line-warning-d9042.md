---
title: "명령줄 경고 D9042 | Microsoft Docs"
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
  - "D9042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9042"
ms.assetid: d710693b-e422-40b2-b2dd-79e1b163b9e6
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# 명령줄 경고 D9042
'value' 값을 '\/option'에 사용할 수 없습니다. 'value'로 가정합니다. 이 컴파일러 버전에서는 코드 분석 경고를 사용할 수 없습니다.  
  
 **\/wd**, **\/we**, **\/wo** 또는 **\/wl** 명령줄 옵션에 코드 분석 경고 번호가 추가되었는데 코드 분석을 지원하지 않는 플랫폼에서 **\/analyze** 명령줄 옵션이 지정되었습니다. 이 경고를 해결하려면 x86 버전의 Visual Studio Team System으로 전환하거나 **\/analyze** 명령줄 옵션을 제거합니다.  
  
## 예제  
 다음 명령줄 예제에서는 x64 또는 Itanium 시스템에 경고 D9042를 생성합니다.  
  
```  
cl /EHsc /LD /wd6001 /analyze filename.cpp  
```  
  
 이 경고를 해결하려면 x86 버전의 Visual Studio Team System으로 전환하거나 **\/analyze** 및 **\/wd6001** 명령줄 옵션을 제거합니다.  
  
## 참고 항목  
 [명령줄 오류\(D8000~D9999\)](/visual-cpp/error-messages/tool-errors/command-line-errors-d8000-through-d9999)   
 [컴파일러 옵션](/visual-cpp/build/reference/compiler-options)