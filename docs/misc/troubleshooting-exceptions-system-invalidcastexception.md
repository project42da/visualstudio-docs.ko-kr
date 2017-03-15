---
title: "예외 문제 해결: System.InvalidCastException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "InvalidCastException 클래스"
ms.assetid: a855dfe1-5c06-45a6-9c2f-c9e799ccf8f0
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.InvalidCastException
<xref:System.InvalidCastException> 예외는 명시적 참조를 변환하는 동안 문제가 발생한 경우에 throw됩니다. 참조 변환은 한 참조 형식에서 다른 참조 형식으로의 변환입니다. 참조 변환을 통해 참조의 형식은 변경할 수 있지만 변환 대상의 형식이나 값을 변경할 수는 없습니다. 일반적으로 한 형식에서 다른 형식으로 개체를 캐스트하면 이 예외가 발생합니다.  
  
## 관련 팁  
 **대상 형식에 대한 소스 형식을 검사하여 변환이 유효한지 확인하십시오.**  
 시스템에서 지원하는 변환에 대한 자세한 내용은 <xref:System.Convert>를 참조하십시오.  
  
## 설명  
 명시적 참조 변환을 성공적으로 수행하려면 소스 값이 Null\(Visual Basic의 경우 `Nothing`\)이거나 소스 인수에서 참조하는 개체 형식이 암시적 참조 변환에서 대상 형식으로 변환할 수 있는 형식이어야 합니다.  
  
 사용자 정의 컨트롤에서 사용자 지정 이벤트를 호출하는 Visual Basic 6.0 응용 프로그램을 새 버전의 Visual Basic으로 업그레이드하고 실행하면 이 예외가 발생하고 "지정한 캐스트가 잘못되었습니다"라는 정보가 추가로 나타납니다. 이 오류를 해결하려면 `Form1`에서 다음과 같은 코드 줄을 찾습니다.  
  
 `Call UserControl11_MyCustomEvent(UserControl11, New UserControl1.MyCustomEventEventArgs(5))`  
  
 그런 다음 이 코드 줄을 다음과 같이 바꿉니다.  
  
 `Call UserControl11_MyCustomEvent(UserControl11(0), New UserControl1.MyCustomEventEventArgs(5))`  
  
## 참고 항목  
 <xref:System.InvalidCastException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [How to: Convert an Object to Another Type in Visual Basic](../Topic/How%20to:%20Convert%20an%20Object%20to%20Another%20Type%20in%20Visual%20Basic.md)   
 [문자열을 .NET Framework 데이터 형식으로 변환](../Topic/Converting%20Strings%20to%20.NET%20Framework%20Data%20Types.md)   
 [방법: 구조체 간의 사용자 정의 변환 구현](../Topic/How%20to:%20Implement%20User-Defined%20Conversions%20Between%20Structs%20\(C%23%20Programming%20Guide\).md)