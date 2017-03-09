---
title: "가상 기본 클래스 계층 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "가상 기본 클래스가 클래스 [c + +]"
  - "클래스 계층 구조를 가상 기본 클래스"
  - "파생된 클래스에서 클래스 계층 구조 고려 사항"
  - "가상 기본 클래스 계층의 가상 함수"
  - "가상 기본 클래스"
  - "가상 기본 클래스 계층 구조"
  - "가상 기본 클래스 계층 구조"
ms.assetid: d24fda17-f829-48d6-84ec-8100f26bc5cf
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 가상 기본 클래스 계층
일부 클래스 계층 구조는 광범위하지만 여러 가지 공통점이 있습니다. 공용 코드는 기본 클래스에서 구현되지만 특정 코드는 파생 클래스에 있습니다.  
  
 파생 클래스가 최대한의 기능을 얻을 수 있는 프로토콜을 기본 클래스에서 설정해야 합니다. 이러한 프로토콜은 일반적으로 가상 함수를 사용하여 구현됩니다. 기본 클래스가 이러한 함수에 대한 기본 구현을 제공하는 경우도 있습니다. 와 같은 클래스 계층 구조에는 `Document` 그림 샘플의 방향이 있는 비순환 그래프 계층 구조 \(참조 [단일 상속](/visual-cpp/cpp/single-inheritance)\), 두 가지 유용한 함수는 `Identify` 및 `WhereIs`합니다.  
  
 `Identify` 함수는 호출되는 경우 문서의 종류에 적합한 올바른 ID를 반환합니다. `Book`의 경우 `doc->Identify()`와 같은 함수 호출은 ISBN 번호를 반환해야 합니다. 그러나 `HelpFile`의 경우에는 제품 이름 및 수정 번호가 보다 적합할 수 있습니다. 마찬가지로 `WhereIs`는 `Book`의 경우 행 및 선반을 반환해야 하지만, `HelpFile`의 경우 디렉터리 및 파일 이름과 같은 디스크 위치를 반환해야 합니다.  
  
 `Identify` 및 `WhereIs` 함수의 모든 구현은 같은 종류의 정보를 반환해야 합니다. 이 경우에는 문자열이 적절합니다.  
  
 이러한 함수는 가상 함수로 구현된 다음 기본 클래스에 대한 포인터를 사용하여 호출됩니다. 실제 코드에 대한 바인딩은 런타임에 발생하여 올바른 `Identify` 또는 `WhereIs` 함수를 선택합니다.  
  
## 참고 항목  
 [파생 클래스 개요](../misc/overview-of-derived-classes.md)