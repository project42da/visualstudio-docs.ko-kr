---
title: "빠른 시작: Visual Studio의 Cookiecutter 템플릿에서 Python 프로젝트 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 876fdbd4507fd7ed55e7b29834d4a3bc5e68dfad
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2017
---
# <a name="quickstart-create-a-project-from-a-cookiecutter-template"></a>빠른 시작: Cookiecutter 템플릿에서 프로젝트 만들기

[Visual Studio 2017에 Python 지원을 설치](installation.md)하면 GitHub에 게시되는 여러 개를 포함하여 Cookiecutter 템플릿에서 새 프로젝트를 쉽게 만들 수 있습니다. [Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/)는 템플릿을 검색하고, 템플릿 옵션을 입력하며, 프로젝트와 파일을 만들 수 있는 그래픽 사용자 인터페이스를 제공합니다. Visual Studio 2017에 포함되어 있으며, 이전 버전의 Visual Studio에서는 개별적으로 설치할 수 있습니다.

1. 이 빠른 시작의 경우 먼저 여기에 표시된 Cookiecutter 템플릿에 대한 필요한 Python 패키지를 포함하는 Anaconda3 Python 배포를 설치합니다. Visual Studio 설치 관리자를 실행하고, **수정**을 선택하고, 오른쪽의 **Python 개발**에 대한 옵션을 확장하고, "Anaconda3"(32비트 또는 64비트)을 선택합니다. 설치는 인터넷 속도에 따라 다소 시간이 걸릴 수 있지만 필요한 패키지를 설치하는 가장 간단한 방법입니다.

1. Visual Studio를 실행합니다.

1. **파일 > 새로 만들기 > Cookiecutter에서...**를 선택합니다. 이 명령은 템플릿을 검색할 수 있는 Visual Studio에서 창을 엽니다. 

    ![Cookiecutter 템플릿에서 새 프로젝트](media/projects-from-cookiecutter1.png)

1. "Microsoft/python-sklearn-classifier-cookiecutter" 템플릿을 선택한 후 **다음**을 선택합니다. (Cookiecutter를 처음으로 사용할 때 프로세스는 몇 분 정도 걸릴 수 있습니다.)

1. 다음 단계에서는 **Create To** 필드에서 새 프로젝트에 대한 위치를 설정한 다음 **만들기**를 선택합니다.

    ![Cookiecutter를 사용하는 두 번째 단계, 프로젝트 속성 설정](media/projects-from-cookiecutter2.png)

1. 프로세스가 완료되면 "파일이 성공적으로 만들어졌습니다."라는 메시지가 나타납니다. **솔루션 탐색기에서 열기** 명령을 선택하여 프로젝트를 엽니다.

1. Ctrl+F5 키를 누르거나 **디버그 > 디버깅하지 않고 시작**을 선택하여 프로그램을 실행합니다. 

    ![python-sklearn-classifier-cookiecutter 템플릿 프로젝트의 출력](media/projects-from-cookiecutter4.png)


## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [자습서: Visual Studio에서 Python 작업](vs-tutorial-01-01.md)

## <a name="see-also"></a>참고 항목

- [Cookiecutter 확장 사용](cookiecutter.md)
- [기존 Python 인터프리터에 대한 환경 만들기](python-environments.md#creating-an-environment-for-an-existing-interpreter)
- [Visual Studio 2015 이하 버전에서 Python 지원 설치](installation.md)
- [설치 위치](installation.md#install-locations)
