---
title: "빌드 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 06/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bceb3b-14fb-455c-805a-63acefa4b3ed
caps.latest.revision: 13
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3fb5627d2cc92c36e9dcf34f4b94796b6620321f
ms.openlocfilehash: 86f7fef0365a47e8ea88bc3fc46cb0016efd4628
ms.contentlocale: ko-kr
ms.lasthandoff: 06/15/2017

---
# <a name="customize-your-build"></a>빌드 사용자 지정
MSBuild 15 이전 버전에서는 솔루션의 프로젝트에 대한 새로운 사용자 지정 속성을 제공하려면 해당 속성에 대한 참조를 솔루션의 모든 프로젝트 파일에 수동으로 추가해야 했습니다. 또는 .props 파일에서 속성을 정의하고 나서 무엇보다 솔루션의 모든 프로젝트에서 .props 파일을 명시적으로 가져와야 했습니다.

그러나 지금은 리포지토리 루트에서 Directory.Build.props라는 단일 파일에 새 속성을 정의하여 한 단계로 모든 프로젝트에 새 속성을 추가할 수 있습니다. MSBuild가 실행되면 Microsoft.Common.props는 Directory.Build.props 파일에 대한 디렉터리 구조를 검색하고 Microsoft.Common.targets는 Directory.Build.targets를 검색합니다. 속성을 찾으면 해당 속성을 가져옵니다. Directory.Build.props는 디렉터리에 있는 프로젝트에 대한 사용자 지정을 제공하는 사용자 정의 파일입니다.

## <a name="directorybuildprops-example"></a>Directory.Build.props 예제
예를 들어 모든 프로젝트가 새 Roslyn **/deterministic** 기능(속성 `$(Deterministic)`에 의해 Roslyn CoreCompile 대상에 표시됨)에 액세스하도록 허용하려면 다음을 수행합니다.

1. Directory.Build.props라는 리포지토리의 루트에 새 파일을 만듭니다.
2. 파일에 다음 XML을 추가합니다.

  ```xml
  <Project>
    <PropertyGroup>
      <Deterministic>true</Deterministic>
    </PropertyGroup>
  </Project>
  ```
3. MSBuild를 실행합니다. 프로젝트의 기존 Microsoft.Common.props 및 Microsoft.Common.targets 가져오기는 파일을 찾아서 가져옵니다.

## <a name="search-scope"></a>검색 범위
Directory.Build.props 파일을 검색할 때 MSBuild는 프로젝트 위치($(MSBuildProjectFullPath))에서 위쪽으로 디렉터리 구조를 이동하여 Directory.Build.props 파일을 찾은 후 멈춥니다. 예를 들어 $(MSBuildProjectFullPath)가 c:\users\username\code\test\case1인 경우 MSBuild는 여기에서 검색을 시작하고 Directory.Build.props 파일을 찾을 때까지 위쪽으로 다음 디렉터리 구조와 같은 디렉터리 구조를 검색합니다.

```
c:\users\username\code\test\case1
c:\users\username\code\test
c:\users\username\code
c:\users\username
c:\users
c:\
```
솔루션 파일 위치는 Directory.Build.props와 관련이 없습니다.

## <a name="import-order"></a>가져오기 순서

Directory.Build.props는 Microsoft.Common.props에서 초기에 가져오므로 나중에 정의된 속성을 적용할 수 없습니다. 따라서 아직 정의되지 않은 속성을 참조하지 마세요. 참조할 경우 비어 있는 것으로 평가됩니다.

Directory.Build.targets는 NuGet 패키지에서 .targets 파일을 가져온 후 Microsoft.Common.targets에서 가져옵니다. 따라서 대부분의 빌드 논리에 정의된 속성 및 대상을 재정의하는 데 사용될 수 있지만, 마지막으로 가져온 후 프로젝트 파일 내에서 사용자 지정을 수행해야 할 수 있습니다.

## <a name="see-also"></a>참고 항목  
 [MSBuild 개념](../msbuild/msbuild-concepts.md)   
 [MSBuild 참조](../msbuild/msbuild-reference.md)   

