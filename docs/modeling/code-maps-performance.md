---
title: 코드 맵 느린가
ms.date: 05/16/2018
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.workload:
- multiple
ms.openlocfilehash: 2dece1e63fffdba67678422ad9241babc63b7abd
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="improve-performance-for-code-maps"></a>성능 향상을 위해 코드 맵

맵을 처음으로 생성하는 경우 Visual Studio는 검색된 모든 종속성을 인덱싱합니다. 이 작업은 특히 큰 솔루션에 대 한 다소 시간이 걸릴 수도 있지만 이후 성능이 향상 됩니다. 코드가 변경되면 Visual Studio는 업데이트된 코드만 다시 인덱싱합니다. 맵 렌더링을 완료 하는 데 걸린 시간을 최소화 하려면 다음 사항을 고려 합니다.

- [원하는 종속성을 매핑하십시오.](#create-a-code-map-to-see-specific-dependencies)

- 전체 솔루션에 대한 맵을 생성하기 전에 솔루션 범위를 줄입니다.

- 솔루션에 대 한 자동 빌드를 선택 하 여 해제할 **빌드 건너뛰기** 코드 맵 도구 모음에서 합니다.

- 선택 하 여 부모 항목의 자동 추가 해제 **부모 포함** 코드 맵 도구 모음에서 합니다.

   ![빌드 건너뛰기 및 상위 포함 단추](../modeling/media/codemapsfilterskipbuildicons.png)

- 코드 맵 파일을 직접 편집하여 필요하지 않은 노드 및 링크를 제거합니다. 맵을 변경해도 기본 코드에 영향을 미치지 않습니다. [DGML 파일을 편집하여 코드 맵 사용자 지정](../modeling/customize-code-maps-by-editing-the-dgml-files.md)을 참조하세요.

맵에 항목을 추가 하거나 맵을 만드는 데 시간이 더 걸릴 수 있습니다 **솔루션 탐색기** 때 프로젝트 항목의 **출력 디렉터리로 복사** 속성이 **항상 복사**합니다. 성능을 높이려면 이 속성을 **변경된 내용만 복사** 또는 `PreserveNewest`로 변경합니다. 참조 [증분 빌드](../msbuild/incremental-builds.md)합니다.

완료 된 맵에 성공적으로 작성된 된 코드에 대 한 종속성을 표시 합니다. 특성 구성 요소에 대해 빌드 오류가 발생하면 해당 오류가 맵에 나타납니다. 이 맵을 기반으로 아키텍처 관련 사항을 결정하기 전에 구성 요소가 실제로 빌드되는지와 해당 구성 요소에 종속성이 있는지를 확인해야 합니다.