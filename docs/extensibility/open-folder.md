---
title: Visual Studio 열려 있는 폴더의 확장성 개요 | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 94c3f8bf-1de3-40ea-aded-7f40c4b314c7
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: d916ea30dd9b72a2d8bd59e8d3d34f9e73c74877
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="open-folder-extensibility"></a>열기 폴더 확장성

[폴더 열기](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) 기능을 사용 하면 사용자가을 열 프로젝트 또는 솔루션 파일에 대 한 필요 없이 Visual Studio에서 코드 베이스는 모든 합니다. 폴더 열기 기능 사용자와 같은 Visual Studio에서 기대를 제공 합니다.

* 솔루션 탐색기 통합 및 검색
* 편집기 색 지정
* 이동 탐색
* 검색 하면 파일에서 찾기

.NET 및 c + + 개발의 경우와 이러한 작업을 사용 하는 경우 사용자 가져오기:

* 서식 있는 Intellisense
* 특정 언어 관련 기능

폴더 열기 확장 작성자는 모든 언어에 대 한 다양 한 기능을 만들 수 있습니다. 사용자의 모든 파일의 코드 베이스에 대 한 빌드, 디버깅 및 기호 검색을 지원 하기 위해 Api 있습니다. 현재 extender는 킹 이라고 하는 프로젝트 또는 솔루션 없이 코드를 이해 하는 기존 Visual Studio 기능을 업데이트할 수 있습니다.

## <a name="an-api-without-project-systems"></a>프로젝트 시스템 없이 API

지금까지 Visual Studio 솔루션 및 프로젝트 시스템을 사용 하 여 해당 프로젝트의 파일만 인식 합니다. 프로젝트 시스템은 로드 된 프로젝트의 기능 및 사용자 상호 작용 담당 합니다. 포함의 프로젝트 파일에서 프로젝트 콘텐츠를 다른 프로젝트에 대 한 종속성을 시각적으로 및 프로젝트 파일은 기본 수정을 이해 합니다. 통해 이러한 계층 및 다른 구성 요소는 사용자를 대신 하 여 적용할 수 있는 기능입니다. 코드 베이스를 모든 프로젝트 및 솔루션 구조에도 표시 됩니다. 스크립트 언어와 Linux 용 c + +로 작성 된 오픈 소스 코드는 좋은 예입니다. 열려 있는 폴더와 Visual Studio는 사용자는 소스 코드와의 상호 작용 하는 새로운 방법을 제공 합니다.

열린 폴더 Api는는 `Microsoft.VisualStudio.Workspace.*` 네임 스페이스 extender가 생성 하 고 데이터 나 열려 있는 폴더 내의 파일 관련 작업을 사용할 수 있게 됩니다. 확장 비롯 한 다양 한 영역에 대 한 기능을 제공 하도록 이러한 Api를 사용 합니다.

- [작업 영역](workspaces.md) -작업 영역 및 해당 Api는 확장성 지점의 열려 있는 폴더를 시작 합니다.
- [컨텍스트 및 작업 파일](workspace-file-contexts.md) -특정 코드 intelligence 파일 컨텍스트를 통해 제공 된 파일입니다.
- [인덱싱](workspace-indexing.md) -수집 하 고 폴더 열기 작업 영역에 대 한 데이터를 유지 합니다.
- [언어 서비스](workspace-language-services.md) -언어 서비스 폴더 열기 작업 영역에 통합 합니다.
- [빌드](workspace-build.md) -폴더 열기 작업 영역에 대 한 지원을 합니다.

다음 형식을 사용 하는 기능 폴더 열기를 지원 하기 위해 새로운 Api를 채택 해야 합니다.

- `IVsHierarchy`
- `IVsProject`
- `DTE`

## <a name="feedback-comments-issues"></a>문제, 의견, 피드백

폴더를 열고 및 `Microsoft.VisualStudio.Workspace.*` Api는 현재 개발에 포함 합니다. 예기치 않은 동작을 보려면 관심 있는 릴리스에 대 한 알려진된 문제를 참조 하십시오. 개발자 커뮤니티에는 모든 문제를 만들고 투표 권장된 위치입니다. 각 피드백에 대 한 문제에 대 한 자세한 설명은 매우 권장 합니다. Visual Studio 버전에 대 한 개발 하는, (구현 했습니다 및 상호 작용 하)를 사용 하는 Api, 예상된 결과 실제 결과 포함 됩니다. 가능 하면 devenv.exe 프로세스의 덤프를 포함 합니다. GitHub의 문제점이 피드백을 제공 하는 것에 대 한 관리를 사용 하 여 관련 설명서 및 합니다.

## <a name="next-steps"></a>다음 단계

* [작업 영역](workspaces.md) -폴더 열기 작업 영역 API에 알아봅니다.