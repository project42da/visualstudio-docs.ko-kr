---
title: "Visual Studio에서 Python 사용, 6단계 | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: 46048b135dc0023e2a7b918b72ec226af3ed22b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="step-6-working-with-git"></a>6단계: Git 작업

**이전 단계: [패키지 설치 및 Python 환경 관리](vs-tutorial-01-05.md)**

Visual Studio는 로컬 Git 리포지토리 및 GitHub 및 Visual Studio Team Services와 같은 서비스에 상주하는 것과의 직접 통합을 제공합니다. 통합은 리포지토리 복제, 변경 내용 커밋 및 분기 관리를 포함합니다.

이 항목에서는 기존 프로젝트에 대한 로컬 Git 리포지토리 만들기를 설명합니다. 원격 Git 리포지토리에서 프로젝트를 만드는 연습은 [빠른 시작: Visual Studio에서 Python 코드의 리포지토리 복제](quickstart-03-project-from-repository.md)를 참조하세요.

1. [이전 단계](vs-tutorial-01-05.md)의 프로젝트와 같은 Visual Studio에서 열린 프로젝트를 사용하여 솔루션을 마우스 오른쪽 단추로 클릭하고 **소스 제어에 솔루션 추가**를 선택합니다. Visual Studio는 프로젝트 코드를 포함하는 로컬 Git 리포지토리를 만들고 Visual Studio 창의 아래쪽을 따라 표시되는 Git 관련 컨트롤도 표시합니다. 컨트롤은 보류 중인 커밋, 변경 내용, 리포지토리의 이름 및 분기를 표시합니다. 추가 정보를 보려면 마우스로 컨트롤을 가리킵니다.

  ![추가 정보는 Visual Studio 창에서 Git 컨트롤을 마우스로 가리킬 때 표시됩니다.](media/working-with-git-01.png)

1. **팀 탐색기** 창도 리포지토리 헤더를 선택하여 사용할 수 있는 다양한 Git 옵션과 함께 표시됩니다. 표시된 대로 **동기화** 창은 원격 리포지토리에 게시를 위한 옵션을 제공합니다.

  ![로컬 리포지토리를 만든 후 Visual Studio의 팀 탐색기](media/working-with-git-02.png)

1. **변경 내용**을 선택하여 커밋되지 않은 변경 내용을 검토하고 필요한 경우 커밋합니다.

  ![커밋되지 않은 변경 내용을 보여 주는 Visual Studio의 팀 탐색기](media/working-with-git-03.png)

1. **분기**를 선택하여 분기를 검사하고 병합을 수행하고 작업을 다시 지정합니다.

  ![분기를 보여 주는 Visual Studio의 팀 탐색기](media/working-with-git-04.png)

1. 로컬 저장소를 사용하는 경우 커밋된 변경 내용은 리포지토리로 직접 이동합니다. 원격 저장소에 연결된 경우 **동기화**를 선택하여 로컬 커밋을 푸시합니다.

## <a name="going-deeper"></a>자세히 알아보기

Git 작업에 대한 보다 광범위한 자습서는 [Visual Studio 2017 및 VSTS Git와 코드 공유](https://docs.microsoft.com/vsts/git/share-your-code-in-git-vs-2017)를 참조하세요.

## <a name="tutorial-review"></a>자습서 검토

Visual Studio의 Python에 대한 이 자습서 완료를 축하합니다. 이 자습서에서는 다음 방법을 학습했습니다.

- 프로젝트를 만들고 프로젝트의 내용을 봅니다.
- 코드 편집기를 사용하고 프로젝트를 실행합니다.
- 대화형 창을 사용하여 새 코드를 개발하고 해당 코드를 편집기에 쉽게 복사합니다.
- Visual Studio 디버거에서 완성된 프로그램을 실행합니다.
- 패키지 설치 및 Python 환경 관리
- Git 리포지토리에서 코드 작업

여기에서 다음을 포함하여 개념 및 방법 가이드를 살펴봅니다.

- [Python용 C++ 확장 만들기](cpp-and-python.md)
- [Azure App Service에 게시](publishing-to-azure.md)
- [프로파일링](profiling.md)
- [유닛 테스트](unit-testing.md)
