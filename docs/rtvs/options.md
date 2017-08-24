---
title: "Visual Studio의 R 도구 옵션 | Microsoft Docs"
ms.custom: 
ms.date: 6/29/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
f1_keywords:
- vs.toolsoptionspages.r_tools
- vs.toolsoptionspages.r_tools.advanced
- vs.toolsoptionspages.r_tools.#150
ms.topic: article
ms.assetid: 554dc602-ecad-4cd0-8e6f-a60bb8a2328f
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 8a544bd1e1242bb6fabe00f7842ac33ed9d9d444
ms.openlocfilehash: a2f0421ff622483fb53795dac527bb8db3c689e2
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---

# <a name="r-tools-for-visual-studio-options"></a>Visual Studio용 R 도구 옵션
 
**R 도구 > 옵션** 메뉴를 통해 액세스하거나 **도구 > 옵션**을 통해 **R 도구**로 스크롤하여 설정에 액세스합니다.
 
  ![R 도구의 [옵션] 대화 상자](media/options-dialog.png)

다음 섹션에서는 이 페이지에서 제공되는 다양한 옵션을 설명합니다.

> [!Note]
> 일반 **도구 > 옵션** 메뉴를 통해 옵션에 액세스할 경우 **R 도구** 페이지를 표시하려면 아래쪽에서 **모든 설정 표시** 상자를 선택해야 할 수 있습니다.

<a name="data-scientist-layout"</a>

**R 도구 > 데이터 과학 설정** 메뉴 항목은 데이터 과학자의 필요에 맞게 최적화된 레이아웃으로 Visual Studio IDE도 구성합니다. 특히 이 옵션을 선택하면 [대화형](interactive-repl.md), [변수 탐색기](variable-explorer.md) 및 [작업 영역](workspaces.md) 창이 열립니다.

![Visual Studio의 데이터 과학자 창 레이아웃](media/installation-data-scientist-layout-result.png)

> [!Important]      
> 나중에 다른 Visual Studio 설정으로 되돌리려면 먼저 **도구 > 설정 가져오기 및 내보내기** 명령을 사용하여 **선택한 환경 설정 내보내기**를 선택하고 파일 이름을 지정합니다. 해당 설정을 복원하려면 같은 명령을 사용하고 **선택한 환경 설정 가져오기**를 선택합니다. 데이터 과학자 레이아웃을 변경한 후 나중에 다시 해당 레이아웃으로 돌아가려는 경우에도 **데이터 과학 설정** 명령을 직접 사용하는 대신 같은 명령을 사용할 수 있습니다.

## <a name="debugging"></a>디버깅

이러한 옵션은 [변수 탐색기](variable-explorer.md) 및 [조사식] 및 [지역] 같은 디버거 창에서 값을 처리하는 방법을 제어합니다([디버깅](debugging.md) 참조).

| 옵션 | 기본값 | 설명 | 
| --- | --- | --- |
| 활성 바인딩 평가 | `True` | `True`인 경우 변수 및 속성을 검사할 때 항상 최신 값이 표시되도록 합니다. 식을 평가하면 구현 방법에 따라 부작용이 발생할 수 있습니다. |
| 점 접두사가 있는 변수 표시 | `False` | `.` 접두사가 있는 변수를 표시할지 지정합니다. |

## <a name="general"></a>일반

| 옵션 | 기본값 | 설명 | 
| --- | --- | --- |
| 설문 조사/뉴스 확인 | `Once a week` | R 도구가 서버에서 뉴스 및 설문 조사 업데이트를 확인하는 빈도를 지정합니다. | 

## <a name="help"></a>도움말

| 옵션 | 기본값 | 설명 | 
| --- | --- | --- |
| F1 웹 브라우저 | `Internal` | Ctrl+F1을 사용하여 용어를 검색하는 동안 도움말이 표시되는 방식을 제어합니다. `Internal`로 설정되면 Visual Studio의 도구 창 내에서 도움말이 렌더링됩니다. `External`로 설정되면 기본 웹 브라우저에서 도움말이 나타납니다. | 
| F1 웹 검색 문자열 | `R site:stackoverflow.com` | 편집기의 용어에서 Ctrl+F1을 누를 때 검색어가 검색 엔진에 전달되는 방식을 제어합니다. 기본적으로 문자열은 `R site:stackoverflow.com`입니다. 이 문자열은 `R`를 검색어에 추가합니다. `site:stackoverflow.com`은 `stackoverflow.com` 도메인 내의 페이지로 검색 범위를 지정하도록 알리는 검색 엔진에 대한 지시문입니다. | 
| R 도움말 브라우저 | `Automatic` | F1, `?` 또는 `??`를 사용하여 R 문서를 검색하는 동안 도움말이 표시되는 방식을 제어합니다. `Automatic`으로 설정되면 해당하는 창에서 도움말이 렌더링됩니다. 예를 들어 HTML 도움말은 Visual Studio 도구 창 내에 표시되지만 PDF는 기본 PDF 프로그램에 나타납니다. `External`로 설정되면 기본 웹 브라우저에서 도움말이 렌더링됩니다. |

## <a name="history"></a>기록

| 옵션 | 기본값 | 설명 | 
| --- | --- | --- |
| 항상 기록 저장 | `True` | RTVS가 프로젝트가 닫힐 때마다 작업 디렉터리의 `.RHistory` 파일에 명령 기록을 쓸지 제어합니다. 종료하기 전에 프로젝트를 저장하지 않은 경우에도 기록 저장이 수행됩니다. |
| 검색 필터 다시 설정 | `True` | [기록] 창에서 부분 문자열이 [R 기록] 대화 상자의 필터 용어와 일치하는 명령만 표시하도록 명령 기록을 필터링할 수 있는지 결정합니다. 이 설정에 따라 새 명령을 실행할 때마다 또는 새 프로젝트로 전환하여 다른 `.RHistory` 파일의 로드를 트리거할 때마다 기록 검색 필터를 다시 설정할지가 결정됩니다. 기본 설정 `True`는 필터 집합 관련 명령을 실행할 때 문제를 최소화하며 사용자는 방금 실행한 명령이 기록에 표시되지 않은 이유를 궁금해합니다. |
| 여러 줄 선택 사용 | `True` | 한 번 클릭으로 기록에서 여러 줄 문을 선택할 수 있는지 지정합니다. 또한 줄이 아닌 문별로 대화형 창에서 위쪽/아래쪽 화살표 탐색을 사용하도록 설정합니다. |

## <a name="html"></a>HTML

| 옵션 | 기본값 | 설명 | 
| --- | --- | --- |
| HTML 페이지 브라우저 | `External` | `ggvis` 플롯 등의 콘텐츠나 `shiny` 응용 프로그램이 렌더링되는 위치를 결정합니다. `Internal`은 Visual Studio의 도구 창 내에 HTML 출력을 표시합니다. `External`은 기본 브라우저에 HTML 출력을 표시합니다. | 

## <a name="logging"></a>로깅

| 옵션 | 기본값 | 설명 | 
| --- | --- | --- |
| 로그 이벤트 | `Normal` | RTVS 진단에 사용되는 로깅의 자세한 정도를 제어합니다. `Normal`의 기본 설정은 `TEMP` 디렉터리에서 로그 파일을 만듭니다. `Traffic`으로 설정되면 RTVS는 해당 세션의 모든 명령과 응답을 기록합니다. 이러한 로그 파일은 컴퓨터에서 유지되며 RTVS에서 문제를 진단하는 데 도움이 될 수 있습니다. |

## <a name="markdown"></a>Markdown

| 옵션 | 기본값 | 설명 | 
| --- | --- | --- |
| Markdown 미리 보기 단추 | `External` | RMarkdown HTML 출력을 표시할지 결정합니다. `Internal`은 Visual Studio의 도구 창 내에 RMarkdown HTML 문서를 표시합니다. `External`은 기본 브라우저에 RMarkdown HTML을 표시합니다. | 

## <a name="r-engine"></a>R 엔진

| 옵션 | 기본값 | 설명 | 
| --- | --- | --- |
| 코드 페이지 | `(OS Default)` | R에 대한 코드 페이지(로캘)를 설정합니다. 기본적으로 운영 체제의 기본 로캘을 사용합니다. | 
| CRAN 미러 | `(Use .Rprofile)` | 패키지 설치에 대한 기본 CRAN 미러를 설정합니다. `Use .Rprofile`의 기본 설정은 CRAN Mirror 설정을 `.RProfile` 파일에 보존합니다. |
| 작업 디렉터리 | 사용자별 폴더 | Sets가 현재 작업 디렉터리이고 대개 프로젝트가 열릴 때마다 설정됩니다. |

## <a name="workspace"></a>작업 영역

| 옵션 | 기본값 | 설명 | 
| --- | --- | --- |
| 프로젝트가 열리면 작업 영역 로드 | `No` | `Yes`로 설정하면 프로젝트가 열릴 때 `.RData` 파일에서 전역 환경으로 세션 데이터를 로드할 수 있습니다. |
| 다시 설정할 때 작업 영역 저장 메시지 표시 | `Yes` | `No`로 설정하면 대화형 창에서 [다시 설정] 단추를 클릭할 때 작업 영역을 저장할지 묻는 메시지가 표시되지 않습니다. |
| 프로젝트가 닫히면 작업 영역 저장 | `No` | `Yes`로 설정하면 프로젝트가 닫힐 때 전역 환경을 `.RData` 파일에 저장할 수 있습니다. |
| 작업 영역을 전환하기 전에 확인 대화 상자를 표시합니다. | `Yes` | `No`로 설정하면 작업 영역 간에 전환할 때 사용자에게 확인 메시지가 표시되지 않습니다. [작업 영역 간 전환](workspaces.md#switching-between-workspaces)을 참조하세요. |
 

