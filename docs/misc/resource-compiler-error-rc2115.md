---
title: "리소스 컴파일러 오류 RC2115 | Microsoft Docs"
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
  - "RC2115"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2115"
ms.assetid: 1b90feb0-f1fb-4f3c-8a9a-c44f9f8dc366
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# 리소스 컴파일러 오류 RC2115
컨트롤에서 텍스트 문자열 또는 서수가 필요합니다.  
  
 **DIALOG** 문에서 CONTROL 문의 *text* 필드는 컨트롤의 형식에 대한 서수 참조 또는 텍스트 문자열이어야 합니다. 서수를 사용하는 경우 컨트롤을 위한 `#define` 문이 있는지 확인합니다.