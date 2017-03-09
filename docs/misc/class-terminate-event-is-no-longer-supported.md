---
title: "&#39;Class_Terminate&#39; 이벤트는 더 이상 지원되지 않습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42002"
  - "bc42002"
helpviewer_keywords: 
  - "BC42002"
ms.assetid: 11eeac74-666d-4b23-81bc-b1691290ddd0
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Class_Terminate&#39; 이벤트는 더 이상 지원되지 않습니다.
'Class\_Terminate' 이벤트는 더 이상 지원되지 않습니다. 'Sub Finalize'을 사용하여 리소스를 확보합니다.  
  
 이전 버전 Visual Basic의 `Class_Terminate` 이벤트가 클래스 소멸자로 대체되었습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42002  
  
### 이 오류를 해결하려면  
  
-   `Finalize`라는 `Sub` 프로시저를 선언하여 클래스를 종료합니다. 인스턴스에 대한 활성 참조가 더 이상 없음을 가비지 수집기가 감지하면 `Sub Finalize`가 호출됩니다.  
  
## 참고 항목  
 [Classes for Visual Basic 6.0 Users](http://msdn.microsoft.com/ko-kr/d625222c-cd32-4c8d-b25c-ea71729b88b7)   
 [빌드에 없음: 생성자 및 소멸자 사용](http://msdn.microsoft.com/ko-kr/548eebe1-86c4-4377-b2f5-447cb8be3d90)   
 [빌드에 없음: 방법: Dispose Finalize 패턴 구현\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/adf7a232-4ebb-485d-8626-8d64421eb0c4)