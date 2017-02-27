---
title: "DA0007: 제어 흐름에는 예외를 사용하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.rules.DAExceptionsThrown"
  - "vs.performance.7"
  - "vs.performance.rules.DA0007"
  - "vs.performance.DA0007"
ms.assetid: ee8ba8b5-2313-46c9-b129-3f3a2a232898
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# DA0007: 제어 흐름에는 예외를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0007|  
|범주|.NET Framework 사용|  
|프로파일링 방법|모두|  
|메시지|많은 수의 예외가 지속적으로 throw되고 있습니다.  프로그램 논리에서 예외 사용을 줄여 보십시오.|  
|메시지 형식|경고|  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링하는 경우에는 적어도 25개의 샘플을 수집하여 이 규칙을 트리거해야 합니다.  
  
## 원인  
 프로파일링 데이터에서 .NET Framework 예외 처리기가 호출된 비율이 높습니다.  다른 제어 흐름 논리를 사용하여 throw되는 예외 수를 줄이는 것이 좋습니다.  
  
## 규칙 설명  
 프로그램 실행에 방해가 되는 오류와 기타 이벤트를 파악하는 예외 처리기를 사용하는 것은 좋은 습관이지만, 예외 처리기를 정규 프로그램 실행 논리의 일부로 사용하면 비용이 매우 많이 들기 때문에 피해야 합니다.  대부분의 경우 자주 발생하지 않고 예기치 못한 상황에만 예외를 사용해야 합니다.  예외는 일반적인 프로그램 흐름의 일부로 값을 반환하는 데 사용하면 안 됩니다.  대부분의 경우 값의 유효성을 검사하고 문제를 일으키는 문 실행을 중단하는 조건부 논리를 사용하여 예외가 발생하는 것을 방지할 수 있습니다.  
  
 자세한 내용은 MSDN 에서 **Microsoft Patterns and Practices** 의 **Improving .NET Application Performance and Scalability** 양에서 **Chapter 5 — Improving Managed Code Performance** 의 [예외 관리](http://go.microsoft.com/fwlink/?LinkID=177825) 를 참조하십시오.  
  
## 경고를 조사하는 방법  
 오류 목록 창에서 메시지를 두 번 클릭하여 표시 뷰로 이동합니다.  **.NET CLR Exceptions\(@ProcessInstance\)\\\# of Exceps Thrown \/ sec** 측정값이 있는 열을 찾습니다.  프로그램 실행 단계 중 예외 처리가 다른 단계보다 자주 발생하는 특정 단계가 있는지 확인합니다.  샘플링 프로파일을 사용하여 throw 문 및 자주 예외를 발생시키는 try\/catch 블록을 확인하십시오.  필요한 경우, 자주 처리되는 식을 파악하는 데 도움이 되는 논리를 캐시 블록에 추가합니다.  가능하면, 자주 실행되는 throw 문이나 catch 블록을 간단한 흐름 제어 논리나 유효성 검사 코드로 바꿉니다.  
  
 예를 들어 응용 프로그램이 자주 발생하는 DivideByZeroException 예외를 처리하는 경우 값이 0인 분모를 확인하는 논리를 프로그램에 추가하면 응용 프로그램의 성능이 향상됩니다.