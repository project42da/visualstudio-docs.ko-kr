---
title: "VSIX v&3; 사용 하 여 확장 폴더 외부 설치 | Microsoft 문서"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 913c3745-8aa9-4260-886e-a05aecfb2225
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
ms.openlocfilehash: 6d87c86d0a7793f661c6a3b28e95340f3a28c616
ms.lasthandoff: 03/07/2017

---
# <a name="installing-outside-the-extensions-folder"></a>확장 폴더 설치

Visual Studio 2017 및 VSIX v3부터 (버전 3), 확장 폴더 외부 확장 자산 설치 이제 지원 됩니다. 현재는 다음 위치는 올바른 설치 위치 (여기서 [installdir] 매핑되는 Visual Studio 인스턴스의 설치 디렉터리)로 사용 됩니다.

* [installdir] \Common7\IDE\PublicAssemblies
* [installdir] \Common7\IDE\ReferenceAssemblies
* [installdir] \MSBuild
* [installdir] \Schemas
* [installdir] \Licenses
* [installdir] \RemoteDebugger
* [installdir] \VSTargets

>**참고:** VSIX 형식 VS 설치 폴더 구조 외부 설치를 허용 하지 않습니다.

이 디렉터리에 설치를 지원 하려면 VSIX "인스턴스별 컴퓨터별" 설치 되어야 합니다. Extension.vsixmanifest 디자이너에서 "모든 사용자" 확인란을 선택 하 여이 사용할 수 있습니다.

![모든 사용자를 확인 합니다.](~/docs/extensibility/media/check-all-users.png)

## <a name="how-to-set-the-installroot"></a>InstallRoot를 설정 하는 방법

설치 디렉터리를 설정 하려면 사용할 수는 **속성** Visual Studio의 창. 예를 들어, 설정할 수는 `InstallRoot` 위의 위치 중 하나에 대 한 프로젝트의 속성:

![설치 루트 속성](~/docs/extensibility/media/install-root-properties.png)

일부 메타 데이터에 해당 요소에 추가 됩니다 `ProjectReference` VSIX 프로젝트의.csproj 파일 안에 속성:

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
        <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
        <Name>ClassLibrary1</Name>
        <InstallRoot>PublicAssemblies</InstallRoot>
 </ProjectReference>
```

>**참고:** 원하는 경우.csproj 파일을 직접 편집할 수 있습니다.

## <a name="how-to-set-a-subpath-under-the-installroot"></a>InstallRoot 아래 하위 경로 설정 하는 방법

아래에 있는 하위 경로를 설치 하려는 `InstallRoot`를 설정 하 여 수행할 수는 `VsixSubPath` 속성 처럼는 `InstallRoot` 속성입니다. 예를 들어, 우리의 프로젝트 참조를 설치 하는 출력 원하는 ' [installdir]\MSBuild\MyCompany\MySDK\1.0'. 속성 디자이너와이 작업을 쉽게 수행할 수 있습니다.

![집합의 하위 경로](~/docs/extensibility/media/set-subpath.png)

해당.csproj 변경 내용을 다음과 같이 표시 됩니다.

```xml
<ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
       <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
       <Name>ClassLibrary1</Name>
       <InstallRoot>MSBuild</InstallRoot>
       <VSIXSubPath>MyCompany\MySDK\1.0</VSIXSubPath>
</ProjectReference>
```

## <a name="extra-information"></a>추가 정보

디자이너 속성 변경 이외의 프로젝트 참조;에 적용 설정할 수는 `InstallRoot` 도 프로젝트 내에서 항목에 대 한 메타 데이터 (위에서 설명한 것과 같은 메서드를 사용 하 여).

