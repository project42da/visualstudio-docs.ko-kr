---
title: "VSIX v3와 확장 폴더 안에 없는 설치 | Microsoft Docs"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 913c3745-8aa9-4260-886e-a05aecfb2225
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1b604a70c44b6fd25888ee5419efbb95f95a0a4a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="installing-outside-the-extensions-folder"></a>확장 폴더 설치

Visual Studio 2017 및 VSIX v 3부터 (버전 3), 확장 폴더 외부 확장 자산을 설치 하기 위한 이제 지원 됩니다. 현재, 다음 위치 올바른 설치 위치 (여기서 [INSTALLDIR] 디렉터리에 매핑된 Visual Studio 인스턴스 설치)로 설정 합니다.

* [INSTALLDIR] \MSBuild
* [INSTALLDIR] \Xml\Schemas
* [INSTALLDIR] \Common7\IDE\PublicAssemblies
* [INSTALLDIR] \Licenses
* [INSTALLDIR] \Common7\IDE\ReferenceAssemblies
* [INSTALLDIR] \Common7\IDE\RemoteDebugger
* [INSTALLDIR] \Common7\IDE\VC\VCTargets

>**참고:** VSIX 형식 VS 설치 폴더 구조 외부 설치를 허용 하지 않습니다.

이 디렉터리에 설치를 지원 하려면 VSIX "인스턴스별 컴퓨터별"를 설치 합니다. Extension.vsixmanifest 디자이너에 있는 "모든 사용자" 확인란을 선택 하 여이 사용할 수 있습니다.

![모든 사용자를 확인 합니다.](media/check-all-users.png)

## <a name="how-to-set-the-installroot"></a>InstallRoot를 설정 하는 방법

설치 디렉터리를 설정 하려면 사용할 수 있습니다는 **속성** Visual Studio의 창. 예를 들어, 설정할 수 있습니다는 `InstallRoot` 위의 위치 중 하나에 대 한 프로젝트의 속성:

![설치 루트 속성](media/install-root-properties.png)

이렇게 하면 해당가 일부 메타 데이터 추가 `ProjectReference` VSIX 프로젝트의.csproj 파일 안에 속성:

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
        <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
        <Name>ClassLibrary1</Name>
        <InstallRoot>PublicAssemblies</InstallRoot>
 </ProjectReference>
```

>**참고:** 원하는 경우.csproj 파일을 직접 편집할 수 있습니다.

## <a name="how-to-set-a-subpath-under-the-installroot"></a>InstallRoot 아래 하위 경로 설정 하는 방법

아래 하위 경로에 설치 하려는 경우는 `InstallRoot`를 설정 하 여 그렇게 할 수는 `VsixSubPath` 속성 처럼는 `InstallRoot` 속성입니다. 예를 들어, 우리의 프로젝트 참조의 출력에 설치 하려면 원하는 ' [INSTALLDIR]\MSBuild\MyCompany\MySDK\1.0'. 속성 디자이너와이 작업을 쉽게 수행할 수 있습니다.

![하위 경로 집합](media/set-subpath.png)

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

둘 이상의 프로젝트 참조;에 대 한 디자이너 속성 변경 내용을 적용합니다 설정할 수 있습니다는 `InstallRoot` 도 프로젝트 내에서 항목에 대 한 메타 데이터 (위에서 설명한 동일한 방법을 사용 하 여).
