---
title: "Visual Studio에서 PyLint 사용 | Microsoft Docs"
ms.custom: 
ms.date: 4/10/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc668a4b-10ae-4199-90b8-c984456b6003
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
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
translationtype: Human Translation
ms.sourcegitcommit: 9328c347d548a03a536cea16bd5851817c03d5a2
ms.openlocfilehash: c8bfaf9f20e7fecb3633ca101170b0f3e686aa53
ms.lasthandoff: 04/10/2017

---

# <a name="using-pylint-to-check-python-code"></a>PyLint를 사용하여 Python 코드 검사

Python 코드의 오류를 검사하고 적절한 Python 코딩 패턴을 권장하며 널리 사용되는 도구인 [PyLint](https://www.pylint.org/)는 Python 프로젝트용 Visual Studio에 통합되어 있습니다.

[솔루션 탐색기]에서 Python 프로젝트를 마우스 오른쪽 단추로 클릭하고 **Python > PyLint 실행...**을 차례로 선택합니다.

![Python 프로젝트의 상황에 맞는 메뉴에 있는 PyLint 명령](media/code-pylint-command.png)

이 명령을 사용하면 필요한 경우 활성 환경에 PyLint를 설치하라는 메시지가 표시됩니다.

[오류 목록] 창에 PyLint 경고 및 오류가 표시됩니다.

![PyLint 오류 목록](media/code-pylint-error-list.png)

오류를 두 번 클릭하면 문제가 발생한 원본 코드로 직접 이동합니다.

> [!Tip]
> 모든 PyLint 출력 메시지에 대한 자세한 목록은 [PyLint 기능 참조](https://pylint.readthedocs.io/en/latest/reference_guide/features.html)(영문)를 참조하세요.

## <a name="setting-pylint-command-line-options"></a>PyLint 명령줄 옵션 설정

PyLint 설명서의 [명령줄 옵션](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) 섹션에서는 `.pylintrc` 구성 파일을 통해 PyLint의 동작을 제어하는 방법에 대해 설명합니다. 이러한 파일은 Visual Studio 또는 해당 설정을 적용하려는 범위에 따라 다른 곳에 있는 Python 프로젝트의 루트에 배치할 수 있습니다.

예를 들어 프로젝트에서 `.pylintrc` 파일을 사용하여 이전 이미지에 표시된 "docstring이 없습니다"라는 경고를 표시하지 않으려면 다음을 수행합니다.

1. 명령줄에서 프로젝트 루트(`.pyproj` 파일을 찾을 위치)로 이동하고 다음 명령을 실행하여 주석 처리된 구성 파일을 생성합니다.

   ```bash
   pylint --generate-rcfile > .pylintrc
   ```

1. Visual Studio 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하여 **추가 > 항목 종료 중...**을 선택하고, 새 `.pylintrc` 파일로 이동하여 선택하고 **추가**를 선택합니다.

1. 편집을 위해 파일을 열면 작업할 수 있는 다양한 설정이 표시됩니다. 경고를 사용하지 않도록 설정하려면 `[MESSAGES CONTROL]` 섹션을 찾은 다음 그 아래에 있는 `disable` 설정을 찾습니다. 특정 메시지의 긴 문자열이 표시되며, 원하는 경고를 추가할 수 있습니다. 이 예제에서는 `,missing-docstring`을 추가합니다(쉼표로 구분된 기호 포함).

1. `.pylintrc` 파일을 저장하고 PyLint를 다시 실행하여 해당 경고가 표시되지 않는지 확인합니다.
