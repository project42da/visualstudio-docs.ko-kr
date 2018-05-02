---
title: Visual Studio에서 .NET Framework 대상 지정
ms.date: 02/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- multi-targeting [Visual Studio]
- multitargeting [Visual Studio]
- framework targeting [Visual Studio]
- .NET framework targeting [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: e44ed988c15a77511d880f1877c1038579a360b5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="visual-studio-multi-targeting-overview"></a>Visual Studio 멀티 타기팅 개요

Visual Studio에서는 프로젝트에서 대상으로 하려는 .NET Framework의 버전 또는 프로필을 지정할 수 있습니다. 응용 프로그램이 다른 컴퓨터에서 실행되려면 응용 프로그램이 대상으로 하는 Framework 버전이 컴퓨터에 설치된 Framework 버전과 호환되어야 합니다.

여러 가지 버전의 프레임워크를 대상으로 지정하는 프로젝트가 포함된 솔루션을 만들 수도 있습니다. 프레임워크 대상 지정을 통해 응용 프로그램에서 지정된 버전의 프레임워크에서 제공되는 기능만 사용하도록 할 수 있습니다.

> [!TIP]
> 다른 플랫폼에 대한 응용 프로그램을 대상으로 지정할 수도 있습니다. 자세한 내용은 [멀티 타기팅](../msbuild/msbuild-multitargeting-overview.md)을 참조하세요.

## <a name="framework-targeting-features"></a>프레임워크 대상 지정 기능

프레임워크 대상 지정에는 다음 기능이 포함됩니다.

- [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 이전 버전을 대상으로 하는 프로젝트를 열면 Visual Studio에서 프로젝트를 자동으로 업그레이드하거나 대상을 있는 그대로 유지할 수 있습니다.

- 프로젝트를 만들 경우 대상으로 지정할 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 버전을 지정할 수 있습니다.

- 기존 프로젝트에서 대상으로 지정하는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 버전을 변경할 수 있습니다.

- 같은 솔루션에 포함된 여러 프로젝트에서 각각 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 다른 버전을 대상으로 지정할 수 있습니다.

- 프로젝트에서 대상으로 지정하는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 버전을 변경하면 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에서는 필요에 따라 참조 및 구성 파일을 변경합니다.

[!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 이전 버전을 대상으로 지정하는 프로젝트 관련 작업을 할 경우 Visual Studio에서는 다음과 같이 개발 환경을 동적으로 변경합니다.

- **새 항목 추가** 대화 상자, **새 참조 추가** 대화 상자 및 **서비스 참조 추가** 대화 상자에서 항목을 필터링하여 대상 버전에서 사용할 수 없는 선택 항목을 생략합니다.

- **도구 상자**에서 사용자 지정 컨트롤을 필터링하여 대상 버전에서 사용할 수 없는 컨트롤을 제거하고 여러 컨트롤을 사용할 수 있을 경우에는 가장 최신 컨트롤만 표시합니다.

- IntelliSense를 필터링하여 대상 버전에서 사용할 수 없는 언어 기능을 생략합니다.

- **속성** 창에서 속성을 필터링하여 대상 버전에서 사용할 수 없는 속성을 생략합니다.

- 메뉴 옵션을 필터링하여 대상 버전에서 사용할 수 없는 옵션을 생략합니다.

- 빌드에는 컴파일러 버전 및 대상 버전에 적절한 컴파일러 옵션을 사용합니다.

> [!NOTE]
> 프레임워크 대상 지정을 수행해도 응용 프로그램이 제대로 실행되지 않을 수 있습니다. 응용 프로그램을 테스트하여 대상 버전에 대해 실행되는지 확인해야 합니다. .NET Framework 2.0 이전의 프레임워크 버전은 대상으로 지정할 수 없습니다.

## <a name="selecting-a-target-framework-version"></a>대상 프레임워크 버전 선택

프로젝트를 만들 때 **새 프로젝트** 대화 상자에서 대상 .NET Framework 버전을 선택합니다. 사용 가능한 프레임워크 목록에는 선택한 템플릿 유형에 적용 가능한 설치된 프레임워크 버전이 포함됩니다. .NET Framework가 필요하지 않은 템플릿 유형의 경우(예: .NET Core 템플릿), **Framework** 드롭다운 목록이 숨겨집니다.

![새 프로젝트 대화 상자의 Framework 드롭다운](media/vside-newproject-framework.png)

기존 프로젝트의 경우 [프로젝트 속성] 대화 상자에서 대상 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전을 변경할 수 있습니다. 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하세요.

## <a name="resolving-system-and-user-assembly-references"></a>시스템 및 사용자 어셈블리 참조 확인

.NET Framework 버전을 대상으로 지정하려면 먼저 적절한 어셈블리 참조를 설치해야 합니다. [.NET 다운로드](https://www.microsoft.com/net/download/windows) 페이지에서 다양한 버전의 .NET Framework 개발자 팩을 다운로드할 수 있습니다.

**참조 추가** 대화 상자에서는 실수로 프로젝트에 추가될 수 없도록 대상 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전에 관련이 없는 시스템 어셈블리가 사용되지 않습니다. 시스템 어셈블리는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전에 포함된 .dll 파일입니다. 대상 버전 이후의 프레임워크 버전에 속한 참조는 확인되지 않고 이런 참조에 따라 결정되는 컨트롤을 추가할 수 없습니다. 해당 참조를 사용하도록 설정하려면 프로젝트의 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 대상을 참조가 포함된 대상으로 다시 설정합니다.  자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하세요.

어셈블리 참조에 대한 자세한 내용은 [디자인 타임에 어셈블리 확인](../msbuild/resolving-assemblies-at-design-time.md)을 참조하세요.

## <a name="enabling-linq"></a>LINQ 사용

.NET Framework 3.5 이상을 대상으로 지정하면 System.Core에 대한 참조 및 System.Linq에 대한 프로젝트 수준 가져오기(Visual Basic에서만)가 자동으로 추가됩니다. LINQ 기능을 사용하려면 Option Infer도 켜야 합니다(Visual Basic에서만). 대상을 이전 .NET Framework 버전으로 변경하면 참조 및 가져오기가 자동으로 제거됩니다. 자세한 내용은 [LINQ 작업](/dotnet/csharp/tutorials/working-with-linq)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [멀티 타기팅(MSBuild)](../msbuild/msbuild-multitargeting-overview.md)
- [방법: 대상 프레임워크 및 플랫폼 도구 집합 수정(C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)