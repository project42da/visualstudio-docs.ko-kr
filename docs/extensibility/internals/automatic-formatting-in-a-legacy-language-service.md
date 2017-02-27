---
title: "자동 레거시 언어 서비스의 형식 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스, 자동 서식 지정"
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 자동 레거시 언어 서비스의 형식 지정
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자가 알려진된 코드 구조를 입력을 시작 하면 자동 서식, 언어 서비스 자동으로 코드 조각을 삽입 합니다.  
  
## 자동 서식 문제  
 예를 들어, 입력할 때 `if`, 언어 서비스에서 일치 하는 중괄호를 자동으로 삽입 하거나 ENTER 키를 누르면 언어 서비스 삽입 지점이 새 줄의 여부를 새 범위 앞 줄을 엽니다에 따라 적절 한 들여쓰기 수준에 강제로.  
  
 또한 자동 서식에 대 한 나머지 언어 서비스에 사용 되는 명령 필터를 사용할 수 있습니다.  호출 하 여 일치 하는 중괄호를 강조할 수 있습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>.  
  
## 참고 항목  
 [언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)