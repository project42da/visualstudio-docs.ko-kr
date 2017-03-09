---
title: "CA1806: 메서드 결과를 무시하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1806"
  - "DoNotIgnoreMethodResults"
helpviewer_keywords: 
  - "CA1806"
  - "DoNotIgnoreMethodResults"
ms.assetid: fd805687-0817-481e-804e-b62cfb3b1076
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1806: 메서드 결과를 무시하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotIgnoreMethodResults|  
|CheckId|CA1806|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 이 경고는 여러 가지 원인으로 인해 발생할 수 있습니다.  
  
-   새 개체를 만들었지만 사용하지 않은 경우  
  
-   새 문자열을 만들어 반환하는 메서드를 호출했지만 새 문자열이 사용되지 않은 경우  
  
-   COM 또는 P\/Invoke 메서드가 반환하는 HRESULT 또는 오류 코드가 사용되지 않은 경우  규칙 설명  
  
 불필요한 개체를 생성하고 이와 연관된 사용되지 않는 개체를 가비지 수집하면 성능이 저하됩니다.  
  
 문자열은 변경할 수 없으며 String.ToUpper 등의 메서드는 호출하는 메서드의 문자열 인스턴스를 수정하는 대신 문자열의 새 인스턴스를 반환합니다.  
  
 HRESULT 또는 오류 코드를 무시하면 예기치 않은 동작으로 인해 오류가 발생하거나 리소스가 부족해질 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 메서드 A가 B 개체의 새 인스턴스를 만들었지만 인스턴스가 사용되지 않은 경우 인스턴스를 다른 메서드에 인수로 전달하거나 인스턴스를 변수에 할당합니다.  개체를 만들 필요가 없는 경우에는 개체를 제거합니다.\-또는\-  
  
 메서드 A가 메서드 B를 호출하지만 메서드 B에서 반환되는 새 문자열 인스턴스를 사용하지 않은 경우  인스턴스를 다른 메서드에 인수로 전달하거나, 인스턴스를 변수에 할당하거나,  불필요한 경우 호출을 제거합니다.  
  
 또는  
  
 메서드 A에서 메서드 B를 호출하지만 메서드가 반환하는 HRESULT 또는 오류 코드를 사용하지 않는 경우  결과를 조건문에 사용하거나 변수에 할당하거나 다른 메서드에 인수로 전달하십시오.  
  
## 경고를 표시하지 않는 경우  
 특정한 용도로 개체를 만드는 경우 이외에는 이 규칙에서 경고를 표시하십시오.  
  
## 예제  
 다음 예제에서는 String.Trim을 호출한 결과를 무시하는 클래스를 보여 줍니다.  
  
 [!CODE [FxCop.Usage.DoNotIgnoreMethodResults#1](FxCop.Usage.DoNotIgnoreMethodResults#1)]  
  
## 예제  
 다음 예제에서는 String.Trim의 결과를 호출 대상 변수에 다시 할당하여 위에 나와 있는 규칙 위반을 해결합니다.  
  
 [!CODE [FxCop.Usage.DoNotIgnoreMethodResults2#1](FxCop.Usage.DoNotIgnoreMethodResults2#1)]  
  
## 예제  
 다음 예제에서는 생성된 개체를 사용하지 않는 메서드를 보여 줍니다.  
  
> [!NOTE]
>  Visual Basic에서는 이러한 위반을 재현할 수 없습니다.  
  
 [!code-cs[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_1.cs)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_1.vb)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults3#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_1.cpp)]  
  
## 예제  
 다음 예제에서는 필요하지 않은 개체를 생성하지 않는 방법으로 위에 나와 있는 규칙 위반을 해결합니다.  
  
 [!code-cs[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_2.cs)]
 [!code-vb[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/VisualBasic/ca1806-do-not-ignore-method-results_2.vb)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults4#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_2.cpp)]  
  
## 예제  
 다음 예제에서는 네이티브 메서드 GetShortPathName이 반환하는 오류 코드를 무시하는 메서드를 보여 줍니다.  
  
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_3.cpp)]
 [!code-cs[FxCop.Usage.DoNotIgnoreMethodResults5#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_3.cs)]  
  
## 예제  
 다음 예제에서는 오류 코드를 검사하고 호출에 실패할 때 예외를 throw하여 위에 나와 있는 규칙 위반을 해결합니다.  
  
 [!code-cs[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CSharp/ca1806-do-not-ignore-method-results_4.cs)]
 [!code-cpp[FxCop.Usage.DoNotIgnoreMethodResults6#1](../code-quality/codesnippet/CPP/ca1806-do-not-ignore-method-results_4.cpp)]