---
title: "컴파일러 경고(수준 3) CS0282 | Microsoft Docs"
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
  - "CS0282"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0282"
ms.assetid: fd4cda5d-81c7-40e3-8424-c938b3447356
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 3) CS0282
partial 클래스 또는 구조체 'type'의 여러 선언에서 필드 간 순서가 정의되어 있지 않습니다. 순서를 지정하려면 모든 인스턴스 필드가 같은 선언에 있어야 합니다.  
  
 이 오류를 해결하려면 모든 멤버 변수를 단일 partial 클래스 정의에 넣습니다.  
  
 이 오류는 일반적으로 둘 이상의 위치에 정의된 partial `struct`의 멤버 변수가 일부분씩 다른 정의에 나뉘어 있는 경우 발생합니다.  
  
 다음 코드에서는 CS0282를 생성합니다.  
  
## 예제  
 이 코드에는 `struct`에 대한 설명이 포함됩니다. 이 두 모듈을 함께 단일 단계에서 다음 명령을 사용하여 컴파일합니다.  
  
 `csc /targt:library cs0282_1.cs cs0282_2.cs`  
  
```  
partial struct A { int i; }  
```  
  
## 예제  
 이 코드에는 동일한 `struct`에 대해 충돌하는 설명이 포함됩니다.  
  
```  
partial struct A { int j; }  
```