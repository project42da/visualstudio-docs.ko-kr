---
title: "CA2210: 어셈블리 이름을 사용 해야 올바른 강력한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AssembliesShouldHaveValidStrongNames
- CA2210
helpviewer_keywords:
- AssembliesShouldHaveValidStrongNames
- CA2210
ms.assetid: 8ed33d1c-8ec6-4b47-a692-e22dc8693088
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 11e50cb87364a85d0c97ae5e566b1209696febbd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2210-assemblies-should-have-valid-strong-names"></a>CA2210: 어셈블리에는 올바른 강력한 이름을 사용해야 합니다.
|||  
|-|-|  
|TypeName|AssembliesShouldHaveValidStrongNames|  
|CheckId|CA2210|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 강력한 이름의 어셈블리 서명이 없습니다 강력한 이름을 확인할 수 없거나, 또는 강력한 이름 없이 컴퓨터의 현재 레지스트리 설정을 사용할 수 없습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙을 검색 하 고 어셈블리의 강력한 이름을 확인 합니다. 다음 중 하나에 해당할 경우 위반이 발생:  
  
-   어셈블리에 강력한 이름이 없습니다.  
  
-   어셈블리가 서명 후 변경 되었습니다.  
  
-   어셈블리 서명이 연기 됩니다.  
  
-   어셈블리, 잘못 서명 하거나 서명 하지 못했습니다.  
  
-   어셈블리 확인을 통과 하는 레지스트리 설정이 필요 합니다. 예를 들어, 강력한 이름 도구 (Sn.exe)를 어셈블리에 대 한 확인을 건너뛰려면 사용 되었습니다.  
  
 강력한 이름은 클라이언트에서 무단으로 변경된 어셈블리를 모르는 사이에 로드하지 못하도록 보호합니다. 강력한 이름이 없는 어셈블리는 극히 제한된 시나리오 이외에는 배포하면 안 됩니다. 제대로 서명되지 않은 어셈블리를 공유하거나 배포하면 어셈블리가 무단으로 변경되거나, 공용 언어 런타임에서 어셈블리를 로드할 수 없거나, 사용자가 자신의 컴퓨터에서 확인을 사용하지 못하게 될 수 있습니다. 강력한 이름이 없는 어셈블리에 다음과 같은 단점이 있습니다.  
  
-   원본은 확인할 수 없습니다.  
  
-   공용 언어 런타임에서 어셈블리의 내용이 변경 된 경우 사용자가 경고 수 없습니다.  
  
-   전역 어셈블리 캐시에 로드할 수 없습니다.  
  
 로드 하 고 서명이 연기 된 어셈블리를 분석할를 어셈블리에 대 한 확인 사용 하지 않도록 설정 해야 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 **키 파일을 만들려면**  
  
 다음 절차 중 하나를 사용 합니다.  
  
-   제공 하는 어셈블리 링커 도구 (Al.exe)를 사용 하 여는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] SDK입니다.  
  
-   에 대 한는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] v1.0 또는 v 1.1을 사용 하 여는 <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> 또는 <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName> 특성입니다.  
  
-   에 대 한는 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]를 사용 하 여는 `/keyfile` 또는 `/keycontainer` 컴파일러 옵션 [/KEYFILE (지정 키 또는 키 쌍 어셈블리에 서명 하)](/cpp/build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly) 또는 [/KEYCONTAINER (어셈블리에 서명할 키 컨테이너 지정)](/cpp/build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly) c + +에서 링커 옵션).  
  
 **Visual Studio에서 강력한 이름으로 어셈블리를 서명 하려면**  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 솔루션을 엽니다.  
  
2.  **솔루션 탐색기**, 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성입니다.**  
  
3.  클릭는 **서명** 탭을 선택 된 **어셈블리에 서명** 확인란 합니다.  
  
4.  **강력한 이름 키 파일 선택**선택, **새로**합니다.  
  
     **강력한 이름 키 만들기** 창에 표시 됩니다.  
  
5.  **키 파일 이름**를 강력한 이름 키의 이름을 입력 합니다.  
  
6.  암호를 사용 하 여 키를 보호 하 고 클릭 것인지 선택할 **확인**합니다.  
  
7.  **솔루션 탐색기**, 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **빌드**합니다.  
  
 **Visual Studio 외부 강력한 이름의 어셈블리를 서명 하려면**  
  
-   제공 되는 강력한 이름 도구 (Sn.exe)를 사용 하 여는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] SDK입니다. 자세한 내용은 [Sn.exe(강력한 이름 도구)](/dotnet/framework/tools/sn-exe-strong-name-tool)를 참조하세요.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 환경에서 어셈블리를 사용 하는 경우에이 규칙에서 경고를 표시를 내용으로 변조 문제가 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName>   
 <xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>   
 [방법: 강력한 이름으로 어셈블리 서명](/dotnet/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name)   
 [Sn.exe(강력한 이름 도구)](/dotnet/framework/tools/sn-exe-strong-name-tool)