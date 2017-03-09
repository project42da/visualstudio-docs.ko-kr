---
title: "리소스 컴파일러 오류 RC2136 | Microsoft Docs"
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
  - "RC2136"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2136"
ms.assetid: 4e9b2ff1-402c-4ec4-8610-fc8fd5f213c0
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# 리소스 컴파일러 오류 RC2136
EXSTYLE\=\<flags\>에 '\='가 없습니다.  
  
 **EXSTYLE**\(확장 스타일 플래그\) 문에 등호\(**\=**\)가 없습니다.**EXSTYLE**이 **DIALOG** 또는 **MENU** 문에 포함되어 있는 경우 다음 형식을 사용해야 합니다.  
  
```  
EXSTYLE=FLAGS  
```