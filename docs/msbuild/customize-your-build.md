---
title: "빌드 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 06/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bceb3b-14fb-455c-805a-63acefa4b3ed
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5b11acd4360aa86d4727a4c697a56eaa753d522c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="customize-your-build"></a>빌드 사용자 지정
MSBuild 15 이전 버전에서는 솔루션의 프로젝트에 대한 새로운 사용자 지정 속성을 제공하려면 해당 속성에 대한 참조를 솔루션의 모든 프로젝트 파일에 수동으로 추가해야 했습니다. 또는 *.props* 파일에서 속성을 정의하고 나서 무엇보다 솔루션의 모든 프로젝트에서 *.props* 파일을 명시적으로 가져와야 했습니다.

그러나 지금은 리포지토리 루트에서 *Directory.Build.props*라는 단일 파일에 새 속성을 정의하여 한 단계로 모든 프로젝트에 새 속성을 추가할 수 있습니다. MSBuild가 실행되면 *Microsoft.Common.props*는 *Directory.Build.props* 파일에 대한 디렉터리 구조를 검색하고 *Microsoft.Common.targets*는 *Directory.Build.targets*를 검색합니다. 속성을 찾으면 해당 속성을 가져옵니다. *Directory.Build.props*는 디렉터리에 있는 프로젝트에 대한 사용자 지정을 제공하는 사용자 지정 파일입니다.

## <a name="directorybuildprops-example"></a>Directory.Build.props 예제
예를 들어 모든 프로젝트가 새 Roslyn **/deterministic** 기능(속성 `$(Deterministic)`에 의해 Roslyn `CoreCompile` 대상에 표시됨)에 액세스하도록 허용하려면 다음을 수행합니다.

1. *Directory.Build.props*라는 리포지토리의 루트에 새 파일을 만듭니다.
2. 파일에 다음 XML을 추가합니다.

  ```xml
  <Project>
    <PropertyGroup>
      <Deterministic>true</Deterministic>
    </PropertyGroup>
  </Project>
  ```
3. MSBuild를 실행합니다. 프로젝트의 기존 *Microsoft.Common.props* 및 *Microsoft.Common.targets* 가져오기는 파일을 찾아서 가져옵니다.

## <a name="search-scope"></a>검색 범위
*Directory.Build.props* 파일을 검색할 때 MSBuild는 프로젝트 위치(`$(MSBuildProjectFullPath)`)에서 위쪽으로 디렉터리 구조를 이동하여 *Directory.Build.props* 파일을 찾은 후 멈춥니다. 예를 들어 `$(MSBuildProjectFullPath)`가 *c:\users\username\code\test\case1*인 경우 MSBuild는 여기에서 검색을 시작하고 *Directory.Build.props* 파일을 찾을 때까지 위쪽으로 다음 디렉터리 구조와 같은 디렉터리 구조를 검색합니다.

```
c:\users\username\code\test\case1
c:\users\username\code\test
c:\users\username\code
c:\users\username
c:\users
c:\
```
솔루션 파일 위치는 *Directory.Build.props*와 관련이 없습니다.

## <a name="import-order"></a>가져오기 순서

*Directory.Build.props*는 *Microsoft.Common.props*에서 초기에 가져오므로 나중에 정의된 속성을 적용할 수 없습니다. 따라서 아직 정의되지 않은 속성을 참조하지 마세요. 참조할 경우 비어 있는 것으로 평가됩니다.

*Directory.Build.targets*는 NuGet 패키지에서 *.targets* 파일을 가져온 후 *Microsoft.Common.targets*에서 가져옵니다. 따라서 대부분의 빌드 논리에 정의된 속성 및 대상을 재정의하는 데 사용될 수 있지만, 마지막으로 가져온 후 프로젝트 파일 내에서 사용자 지정을 수행해야 할 수 있습니다.

## <a name="use-case-multi-level-merging"></a>사용 사례: 다단계 병합

이 표준 솔루션 구조체가 있다고 가정합니다.

````
\
  MySolution.sln
  Directory.Build.props     (1)
  \src
    Directory.Build.props   (2-src)
    \Project1
    \Project2
  \test
    Directory.Build.props   (2-test)
    \Project1Tests
    \Project2Tests
````

모든 프로젝트 *(1)*의 공통 속성, *src* 프로젝트*(2-src)*의 공통 속성 및 *test* 프로젝트*(2-test)*의 공통 속성이 있는 것이 바람직할 수도 있습니다.

MSBuild에서 “내부” 파일(*2-src* 및 *2-test*)을 “외부” 파일(*1*)과 올바르게 병합하려면 MSBuild가 *Directory.Build.props* 파일을 찾으면 추가 검사를 중지하도록 고려해야 합니다. 계속 검사하고 외부 파일에 병합하려면 해당 항목을 모든 내부 파일에 배치합니다.

`<Import Project="$([MSBuild]::GetPathOfFileAbove('Directory.Build.props', '$(MSBuildThisFileDirectory)../'))" />`

MSBuild의 일반적인 방법의 요약 정보는 다음과 같습니다.

- 지정된 프로젝트의 경우 MSBuild는 솔루션 구조체에서 위쪽으로 첫 번째 *Directory.Build.props*를 찾고, 기본값과 병합하고, 추가 검사를 중지합니다.
- 다단계를 찾고 병합하려는 경우 "내부" 파일에서 "외부" 파일을 [`<Import...>`](../msbuild/property-functions.md#msbuild-getpathoffileabove)(위에 표시)합니다.
- "외부" 파일이 자체로 상위 항목을 가져오지 않으면 거기서 검색을 중지합니다.
- 검사/병합 프로세스를 제어하려면 `$(DirectoryBuildPropsPath)` 및 `$(ImportDirectoryBuildProps)`를 사용합니다.

간단히 말하면 아무것도 가져오지 않는 첫 번째 *Directory.Build.props*에서 MSBuild가 중지됩니다.

## <a name="see-also"></a>참고 항목  
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [MSBuild 참조](../msbuild/msbuild-reference.md)   
