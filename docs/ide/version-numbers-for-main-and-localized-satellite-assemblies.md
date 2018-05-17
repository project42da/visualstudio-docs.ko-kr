---
title: 주 어셈블리 및 지역화된 위성 어셈블리의 버전 번호
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- satellite assemblies, version numbers
- SatelliteContractVersionAttribute
- version numbers, assemblies
- assemblies [Visual Studio], version numbers
- versioning, assemblies
ms.assetid: 5489aea1-57b4-4561-9bb4-24d490269602
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: db2d6c8da22278d830423643fb8ad869d5123a19
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="version-numbers-for-main-and-localized-satellite-assemblies"></a>주 어셈블리 및 지역화된 위성 어셈블리의 버전 번호
<xref:System.Resources.SatelliteContractVersionAttribute> 클래스는 Resource Manager를 통해 지역화된 리소스를 사용하는 주 어셈블리에 대한 버전 관리 지원을 제공합니다. <xref:System.Resources.SatelliteContractVersionAttribute>를 응용 프로그램의 주 어셈블리에 적용하면 위성 어셈블리를 업데이트하지 않고 어셈블리를 업데이트 및 재배포할 수 있습니다. 예를 들어 위성 어셈블리를 다시 빌드 및 다시 배포하지 않고 새 리소스를 도입하지 않은 서비스 팩과 함께 <xref:System.Resources.SatelliteContractVersionAttribute> 클래스를 사용할 수 있습니다. 지역화된 리소스를 사용하려면 주 어셈블리의 위성 계약 버전이 위성 어셈블리의 <xref:System.Reflection.AssemblyVersionAttribute> 클래스와 일치해야 합니다. <xref:System.Resources.SatelliteContractVersionAttribute>에서 정확한 버전 번호를 지정하고 와일드카드 문자(예: “*”)는 허용되지 않습니다. 자세한 내용은 [리소스 검색](/dotnet/framework/resources/retrieving-resources-in-desktop-apps)을 참조하세요.

## <a name="update-assemblies"></a>어셈블리 업데이트
 <xref:System.Resources.SatelliteContractVersionAttribute> 클래스를 사용하여 위성 어셈블리를 업데이트할 필요 없이 주 어셈블리를 업데이트하거나 그 반대로 할 수 있습니다. 주 어셈블리가 업데이트되면 해당 어셈블리 버전 번호가 변경됩니다. 기존 위성 어셈블리를 계속 사용하려면 주 어셈블리의 버전 번호를 변경하고 위성 계약 버전 번호는 동일하게 유지합니다. 예를 들어 첫 번째 릴리스에서 주 어셈블리 버전은 1.0.0.0일 수 있습니다. 위성 계약 버전 및 위성 어셈블리의 어셈블리 버전도 1.0.0.0입니다. 서비스 팩을 적용하기 위해 주 어셈블리를 업데이트해야 할 경우 어셈블리 버전을 1.0.0.1로 업데이트할 수 있지만 위성 계약 버전 및 위성의 어셈블리 버전은 1.0.0.0으로 유지합니다.

 주 어셈블리를 업데이트하지 않고 위성 어셈블리를 업데이트해야 할 경우에는 위성 어셈블리의 <xref:System.Reflection.AssemblyVersionAttribute>를 변경합니다. 위성 어셈블리와 함께 새 위성 어셈블리가 이전 위성 어셈블리와 호환됨을 명시하는 정책 어셈블리를 전달해야 합니다. 정책에 대한 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)을 참조하세요.

 다음 코드는 위성 계약 버전을 설정하는 방법을 보여 줍니다. 코드는 *AssemblyInfo.vb* 또는 *AssemblyInfo.cs* 파일이나 빌드 스크립트에 삽입할 수 있습니다.

```vb
<Assembly: SatelliteContractVersionAttribute("4.3.2.1")>

```

```csharp
[assembly: SatelliteContractVersionAttribute("4.3.2.1")]
```

## <a name="see-also"></a>참고 항목

- [런타임에서 어셈블리를 찾는 방법](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [어셈블리 특성 설정](/dotnet/framework/app-domains/set-assembly-attributes)
- [보안 및 지역화된 위성 어셈블리](../ide/security-and-localized-satellite-assemblies.md)
- [응용 프로그램 지역화](../ide/localizing-applications.md)
- [세계화 및 지역화 응용 프로그램](../ide/globalizing-and-localizing-applications.md)