---
title: "CA1409: COM 노출 형식을 만들 수 있어야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ComVisibleTypesShouldBeCreatable"
  - "CA1409"
helpviewer_keywords: 
  - "ComVisibleTypesShouldBeCreatable"
  - "CA1409"
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1409: COM 노출 형식을 만들 수 있어야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ComVisibleTypesShouldBeCreatable|  
|CheckId|CA1409|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 COM\(Component Object Model\)에 표시되는 것으로 특별히 표시된 참조 형식에 매개 변수가 있는 public 생성자가 있지만 매개 변수가 없는 public 기본 생성자가 없습니다.  
  
## 규칙 설명  
 COM 클라이언트에서는 public 기본 생성자가 없는 형식을 만들 수 없습니다.  그러나 다른 방법으로 형식을 만들고 클라이언트에 전달할 수 있으면\(예: 메서드 호출의 반환 값을 통해\) COM 클라이언트에서 해당 형식에 여전히 액세스할 수 있습니다.  
  
 이 규칙에서는 <xref:System.Delegate?displayProperty=fullName>에서 파생된 형식은 무시합니다.  
  
 기본적으로 어셈블리, public 형식, public 형식의 public 인스턴스 멤버, public 값 형식의 모든 멤버는 COM에서 볼 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 public 기본 생성자를 추가하거나 형식에서 <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName>를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 개체를 만들고 COM 클라이언트에 전달할 수 있는 다른 방법이 있으면 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 관련 규칙  
 [CA1017: ComVisibleAttribute로 어셈블리 표시](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## 참고 항목  
 [상호 운용할 .NET 형식의 정규화](../Topic/Qualifying%20.NET%20Types%20for%20Interoperation.md)   
 [비관리 코드와의 상호 운용](../Topic/Interoperating%20with%20Unmanaged%20Code.md)