---
title: "VSIX v&3;에서 Ngen 지원 | Microsoft 문서"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1472e884-c74e-4c23-9d4a-6d8bdcac043b
caps.latest.revision: 1
author: gregvanl
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 8163a0e1230712734936b7548bef1753ee0c1d2a
ms.openlocfilehash: 46b6f4d13b4c1938797dbe6cf6023e3c8c42d1ed
ms.lasthandoff: 03/07/2017

---
# <a name="ngen-support-in-vsix-v3"></a>VSIX v&3;에서 Ngen 지원

Visual Studio 2017 및 새 VSIX v3 (버전 3) 확장 매니페스트에서 형식으로 확장 개발자 있습니다 "ngen" 설치 시 어셈블리입니다.

다음은 어떤 "ngen" 설명 하는 MSDN에서 발췌 한 것이입니다.

>네이티브 이미지 생성기(Ngen.exe)는 관리되는 응용 프로그램의 성능을 향상시키는 도구입니다. Ngen.exe는 컴파일된 프로세서별 컴퓨터 코드가 포함된 파일인 네이티브 이미지를 만들어서 로컬 컴퓨터의 네이티브 이미지 캐시에 설치합니다. 런타임은 JIT(Just-In-Time) 컴파일러를 사용하지 않고 캐시의 네이티브 이미지를 사용하여 원본 어셈블리를 컴파일할 수 있습니다.
>
>[Ngen.exe (네이티브 이미지 생성기)](https://msdn.microsoft.com/en-us/library/6t9t5wcf(v=vs.110).aspx)

어셈블리가 "ngen" 순서로 VSIX "인스턴스별 컴퓨터별" 설치 되어야 합니다. Extension.vsixmanifest 디자이너에서 "모든 사용자" 확인란을 선택 하 여이 사용할 수 있습니다.

![모든 사용자를 확인 합니다.](~/docs/extensibility/media/check-all-users.png)

## <a name="how-to-enable-ngen"></a>Ngen을 사용 하는 방법

어셈블리에 대 한 ngen을 사용 하려면 사용할 수는 **속성** Visual Studio의 창.

4 개의 속성을 설정할 수 있습니다.

1. **Ngen** (부울) – Visual Studio 설치 관리자를 true 인 경우, "ngen" 어셈블리를 됩니다.
2. **Ngen 응용 프로그램** (문자열)-Ngen 어셈블리 종속성을 해결 하기 위해 응용 프로그램의 app.config 파일을 사용 하 여 기회를 제공 합니다. 응용 프로그램 (Visual Studio 설치 디렉터리)에 상대적인 사용 하려면 해당 app.config에이 값을 설정 해야 합니다.
3. **Ngen 아키텍처** (enum) – 아키텍처를 기본적으로 어셈블리를 컴파일합니다. 옵션은:는 합니다. NotSpecified b입니다. X86 c입니다. X64 d입니다. 모두
4. **Ngen 우선 순위** (1과 3 사이의 정수) – The Ngen 우선 순위 수준에 설명 되어 [Ngen.exe 우선 순위 수준을](https://msdn.microsoft.com/en-us/library/6t9t5wcf(v=vs.110).aspx#Anchor_3)합니다.

여기에 살펴보겠습니다는 **속성** 작업에서 창:

![속성에서 ngen](~/docs/extensibility/media/ngen-in-properties.png)

메타 데이터는 VSIX 프로젝트의.csproj 파일 내에서 프로젝트 참조에 추가 됩니다.

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
    <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
    <Name>ClassLibrary1</Name>
    <Ngen>True</Ngen>
    <NgenApplication>vsn.exe</NgenApplication>
    <NgenArchitecture>X86</NgenArchitecture>
    <NgenPriority>2</NgenPriority>
</ProjectReference>
 ```

 >**참고:** 원하는 경우.csproj 파일을 직접 편집할 수 있습니다.

## <a name="extra-information"></a>추가 정보

디자이너 속성 변경 이외의 프로젝트 참조;에 적용 항목에 대 한 Ngen 메타 데이터도 프로젝트 내에서 설정할 수 있습니다 (사용 하 여 위에서 설명한 것과 같은 메서드) 만큼의 항목은.NET 어셈블리입니다.
