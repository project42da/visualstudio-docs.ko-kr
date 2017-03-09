---
title: "&#39;Class_Initialize&#39; 이벤트는 더 이상 지원되지 않습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42001"
  - "bc42001"
helpviewer_keywords: 
  - "BC42001"
ms.assetid: 31e7c383-894e-416c-b834-3688cc340ccf
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Class_Initialize&#39; 이벤트는 더 이상 지원되지 않습니다.
'Class\_Initialize' 이벤트는 더 이상 지원되지 않습니다. 클래스를 초기화하려면 'Sub New'를 사용합니다.  
  
 이전 버전 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 `Class_Initialize` 이벤트가 클래스 생성자로 대체됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42001  
  
### 이 오류를 해결하려면  
  
-   하나 이상의 `Sub` 프로시저 이름을 `New`로 선언하여 클래스를 초기화합니다. 클래스 인스턴스를 새로 만들 때 `Sub New`가 호출됩니다.  
  
## 참고 항목  
 [Class\_Initialize Changes in Visual Basic](http://msdn.microsoft.com/ko-kr/2cd023cf-2869-4836-b08d-43822294beeb)   
 [Classes for Visual Basic 6.0 Users](http://msdn.microsoft.com/ko-kr/d625222c-cd32-4c8d-b25c-ea71729b88b7)   
 [빌드에 없음: 생성자 및 소멸자 사용](http://msdn.microsoft.com/ko-kr/548eebe1-86c4-4377-b2f5-447cb8be3d90)