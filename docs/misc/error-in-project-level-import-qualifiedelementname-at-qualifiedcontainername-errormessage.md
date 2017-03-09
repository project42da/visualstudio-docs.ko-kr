---
title: "&#39;&lt;qualifiedcontainername&gt;&#39;에 있는 프로젝트 수준의 가져오기 &#39;&lt;qualifiedelementname&gt;&#39;에서 오류가 발생했습니다(&lt;errormessage&gt;). | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BC30797"
  - "vbc30797"
helpviewer_keywords: 
  - "BC30797"
ms.assetid: 529f354f-f255-4adc-ab21-bd1796e58d69
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;qualifiedcontainername&gt;&#39;에 있는 프로젝트 수준의 가져오기 &#39;&lt;qualifiedelementname&gt;&#39;에서 오류가 발생했습니다(&lt;errormessage&gt;).
다른 어셈블리에 정의된 프로그래밍 요소를 문에서 액세스하지만 해당 어셈블리에 대한 프로젝트 참조가 없습니다.  
  
 예를 들어 코드에서 한정 문자열 `otherNamespace.otherClass.desiredEnumeration`을 사용하여 `desiredEnumeration`라는 열거형에 액세스할 수 있습니다. 컴파일러가 프로젝트 참조에서 `otherNamespace.otherClass`를 찾을 수 없는 경우 이 오류가 생성됩니다.  
  
 **오류 ID:** BC30797  
  
### 이 오류를 해결하려면  
  
1.  프로그래밍 요소의 한정 문자열에서 모든 요소를 올바르게 입력했는지 확인합니다.  
  
2.  프로젝트에 원하는 프로그래밍 요소를 정의하는 어셈블리에 대한 참조가 있는지 확인합니다.  
  
3.  오류 메시지를 확인하고 적절한 조치를 수행합니다.  
  
## 참고 항목  
 [NOTINBUILD: 여러 변수에 동일한 이름이 있는 경우 참조 확인](http://msdn.microsoft.com/ko-kr/9601e39f-1911-44e1-ace5-3f6e090408b9)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)