---
title: "Visual Studio에서 Python 검색 경로를 적용하는 편집 | Microsoft Docs"
ms.custom: 
ms.date: 03/05/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 2135515859ea32c8d134ec6c5824195c554ee97e
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="how-visual-studio-uses-python-search-paths"></a>Visual Studio에서 Python 검색 경로를 사용하는 방법

일반적인 Python 사용에서 `PYTHONPATH` 환경 변수(또는 `IRONPYTHONPATH` 등)는 모듈 파일에 대한 기본 검색 경로를 제공합니다. 즉, `from <name> import...` 또는 `import <name>` 문을 사용하는 경우 Python은 다음 위치에서 일치하는 이름을 순서대로 검색합니다.

1. Python의 기본 제공 모듈입니다.
1. 실행 중인 Python 코드를 포함하는 폴더입니다.
1. 적용 가능한 환경 변수에 정의된 “모듈 검색 경로” 입니다. (코어 Python 설명서의 [모듈 검색 경로](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) 및 [환경 변수](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) 참조)

그러나 Visual Studio에서는 변수가 전체 시스템에 대해 설정된 경우에도 검색 경로 환경 변수를 무시합니다. 이렇게 무시되는 이유는 실제로 엄밀히 말해 전체 시스템에 대해 설정되었기 *때문이며* 따라서 자동으로 해결할 수 없는 다음과 같은 특정 질문이 제기됩니다. 참조된 모듈이 Python 2.7 또는 Python 3.3용인가? 이 모듈이 표준 라이브러리 모듈을 재정의하게 되는가? 개발자가 이 동작을 알고 있는가 아니면 악의적인 하이재킹 시도인가?

따라서 Visual Studio에서는 환경 및 프로젝트 모두에서 검색 경로를 직접 지정하는 방법을 제공합니다. Visual Studio에서 실행하거나 디버그하는 코드는 `PYTHONPATH` 값으로 검색 경로(및 기타 동등한 변수)를 받습니다. Visual Studio는 검색 경로를 추가하여 해당 위치의 라이브러리를 검사하고 필요한 경우(Visual Studio 2017 버전 15.5 및 이전 버전) 라이브러리에 대한 IntelliSense 데이터베이스를 빌드합니다(라이브러리 수에 따라 데이터베이스를 구성하는 데 다소 시간이 걸릴 수 있음).

검색 경로를 추가하려면 솔루션 탐색기에서 **검색 경로** 항목을 마우스 오른쪽 단추로 클릭하고 **검색 경로에 폴더 추가...**를 선택하고 포함할 폴더를 선택합니다. 이 경로는 프로젝트와 연결된 환경에 사용됩니다. (환경이 Python 3을 기반으로 하고 Python 2.7 모듈에 검색 경로를 추가하려는 경우 오류가 표시될 수 있습니다.)

`.zip` 또는 `.egg` 확장명이 있는 파일도 **검색 경로에 Zip 보관 파일 추가...**를 선택하여 검색 경로로 추가할 수 있습니다. 폴더와 마찬가지로 이러한 폴더의 내용을 검색하고 IntelliSense에 제공합니다.

정기적으로 동일한 검색 경로를 사용하고 그 내용이 자주 변경되지 않는 경우 site-packages 폴더에 설치하는 것이 더 효율적일 수 있습니다. 검색 경로가 분석되어 IntelliSense 데이터베이스에 저장되며 항상 의도한 환경과 연결되고 각 프로젝트에 대해 검색 경로를 추가할 필요가 없습니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio에서 Python 환경 관리](managing-python-environments-in-visual-studio.md)
- [프로젝트의 인터프리터 선택](selecting-a-python-environment-for-a-project.md)
- [종속성에 대해 requirements.txt 사용](managing-required-packages-with-requirements-txt.md)
- [Python 환경 창 참조](python-environments-window-tab-reference.md)