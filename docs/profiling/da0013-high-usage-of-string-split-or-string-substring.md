---
title: "DA0013: String.Split 또는 String.Substring 사용률이 높습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.13"
  - "vs.performance.rules.DAAvoidStringSubstr"
  - "vs.performance.DA0013"
  - "vs.performance.rules.DA0013"
helpviewer_keywords: 
  - "vs.performance.13"
  - "vs.performance.rules.DA0013"
ms.assetid: f501f423-bef9-4e08-bf96-c9ac9957e5a2
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0013: String.Split 또는 String.Substring 사용률이 높습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0013|  
|범주|.NET Framework 사용 지침|  
|프로파일링 방법|샘플링|  
|메시지|String.Split 및 String.Substring 함수 사용을 줄여 보십시오.|  
|규칙 유형|경고|  
  
## 원인  
 System.String.Split 또는 System.String.Substring 메서드에 대한 호출이 프로파일링 데이터의 상당 비율을 차지합니다.  문자열에 부분 문자열이 있는지 테스트할 경우 System.String.IndexOf 또는 System.String.IndexOfAny를 사용하는 것이 좋습니다.  
  
## 규칙 설명  
 Split 메서드는 String 개체에 대해 작동하며 원본의 부분 문자열을 포함하는 새 문자열 배열을 반환합니다.  해당 함수는 반환된 배열 개체에 대한 메모리를 할당하고 찾은 각 배열 요소에 새 문자열 개체를 할당합니다.  마찬가지로 Substr 메서드는 String 개체에 작동하며 요청된 부분 문자열과 동일한 새 문자열을 반환합니다.  
  
 응용 프로그램에서 메모리 할당 관리가 중요한 경우, String.Split 및 String.Substr 메서드 대신 다른 방법을 사용하는 것이 좋습니다.  예를 들어 IndexOf 또는 IndexOfAny 메서드를 사용하여 문자열 클래스의 새 인스턴스를 만들지 않고 문자 문자열에서 특정 부분 문자열을 찾을 수 있습니다.  
  
## 경고를 조사하는 방법  
 오류 목록 창에서 메시지를 두 번 클릭하여 샘플링 프로필 데이터의 [함수 정보 뷰](../profiling/function-details-view.md)로 이동합니다.  호출 함수를 검토하여 System.String.Split 또는 System.String.Substr 메서드를 자주 사용하는 프로그램의 부분을 찾습니다.  가능한 경우 IndexOf 또는 IndexOfAny 메서드를 사용하여 문자열 클래스의 새 인스턴스를 만들지 않고도 특정 문자 문자열 내의 부분 문자열을 찾을 수 있습니다.