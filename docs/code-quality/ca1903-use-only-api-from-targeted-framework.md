---
title: "CA1903: 대상 프레임워크에서 API만 사용하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "UseOnlyAPIFromTargetedFramework"
  - "CA1903"
helpviewer_keywords: 
  - "CA1903"
  - "UseOnlyApiFromTargetedFramework"
ms.assetid: efdb5cc7-bbd8-4fa7-9fff-02b91e59350e
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 8
---
# CA1903: 대상 프레임워크에서 API만 사용하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UseOnlyApiFromTargetedFramework|  
|CheckId|CA1903|  
|범주|Microsoft.Portability|  
|변경 수준|주요 변경 \- 외부에서 볼 수 있는 멤버 또는 형식의 시그너처에 대해 발생한 경우<br /><br /> 주요 변경 아님 – 메서드 본문에서 발생한 경우|  
  
## 원인  
 멤버 또는 형식이 프로젝트의 대상 프레임워크에 포함되지 않은 서비스 팩에 도입된 멤버 또는 형식을 사용합니다.  
  
## 규칙 설명  
 새로운 멤버 및 형식이 .NET Framework 2.0 서비스 팩 1과 2, .NET Framework 3.0 서비스 팩 1과 2 및 .NET Framework 3.5 서비스 팩 1에 포함되었습니다.  .NET Framework의 주요 버전을 대상으로 하는 프로젝트가 이러한 새로운 프로젝트에 대한 종속성을 본의 아니게 사용할 수 있습니다.  이러한 종속성이 발생하지 않도록 하기 위해 프로젝트의 대상 프레임워크에 기본적으로 포함되지 않은 새로운 멤버 및 형식을 사용하게 되면 이 규칙이 실행됩니다.  
  
 **대상 프레임워크 및 서비스 팩 종속성**  
  
|||  
|-|-|  
|대상 프레임워크|다음에 도입된 멤버를 사용할 경우 발생|  
|.NET Framework 2.0|.NET Framework 2.0 SP1, .NET Framework 2.0 SP2|  
|.NET Framework 3.0|.NET Framework 2.0 SP1, .NET Framework 2.0 SP2, .NET Framework 3.0 SP1, .NET Framework 3.0 SP2|  
|.NET Framework 3.5|.NET Framework 3.5 SP1|  
|.NET Framework 4|N\/A|  
  
 프로젝트의 대상 프레임워크를 변경하려면 [특정 대상 .NET Framework 버전 지정](../ide/targeting-a-specific-dotnet-framework-version.md)을 참조하십시오.  
  
## 위반 문제를 해결하는 방법  
 서비스 팩에 대한 종속성을 없애려면 새 멤버 또는 형식의 모든 사용을 제거합니다.  의도적인 종속성인 경우에는 경고를 비활성화하거나 이 규칙을 해제합니다.  
  
## 경고를 표시하지 않는 경우  
 지정된 서비스 팩에 대한 의도적인 종속성이 아닌 경우에는 이 규칙에서 경고를 표시해야 합니다.  이 경우 이 서비스 팩을 설치하지 않으면 시스템에서 응용 프로그램이 실행되지 않을 수 있습니다.  의도적인 종속성인 경우에는 경고를 비활성화하거나 이 규칙을 해제합니다.  
  
## 예제  
 다음 예제에서는 .NET 2.0 서비스 팩 1에서만 사용할 수 있는 DateTimeOffset 형식을 사용하는 클래스를 보여 줍니다.  이 예제에서는 프로젝트 속성의 대상 프레임워크 드롭다운 목록에서 .NET Framework 2.0을 선택해야 합니다.  
  
 [!code-cs[FxCop.Portability.UseOnlyApiFromTargetedFramework#1](../code-quality/codesnippet/CSharp/ca1903-use-only-api-from-targeted-framework_1.cs)]  
  
## 예제  
 다음 예제에서는 DateTimeOffset 형식을 DateTime 형식으로 바꿔 사용하여 위에 나와 있는 규칙 위반을 해결합니다.  
  
 [!code-cs[FxCop.Portability.UseOnlyApiFromTargetedFramework2#1](../code-quality/codesnippet/CSharp/ca1903-use-only-api-from-targeted-framework_2.cs)]  
  
## 참고 항목  
 [이식성 경고](../code-quality/portability-warnings.md)   
 [특정 대상 .NET Framework 버전 지정](../ide/targeting-a-specific-dotnet-framework-version.md)