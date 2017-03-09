---
title: "리소스 컴파일러 경고 RC4204 | Microsoft Docs"
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
  - "RC4204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4204"
ms.assetid: f9a83b3c-d696-4b38-9576-945d1f6d0063
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# 리소스 컴파일러 경고 RC4204
ASCII 문자가 가상 키 코드와 일치하지 않습니다.  
  
 VIRTKEY 형식 액셀러레이터의 가상 키 코드에 문자열 리터럴을 사용했습니다.  
  
 이 경고가 표시되어도 계속 진행할 수 있지만 생성된 액셀러레이터 키가 지정한 문자열과 일치하지 않을 수 있습니다. \(VIRTKEY가 ASCII 액셀러레이터와 다른 키 코드를 사용합니다.\)  
  
 문자열 리터럴이 구문상 유효한 동안에만 WINDOWS.h에서 **VK\_ \*** `#define` 값을 사용하여 원하는 액셀러레이터를 얻을 수 있는지 확인할 수 있습니다.