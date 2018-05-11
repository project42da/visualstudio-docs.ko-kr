---
title: 빠른 시작 - 템플릿을 사용하여 Python 프로젝트 만들기
description: 이 빠른 시작에서 기본 Flask 앱의 기본 제공 템플릿을 사용하여 Python용 Visual Studio 프로젝트를 만듭니다.
ms.date: 03/22/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: a033d8b2709a6eaf871758d1bd46a3ad34f7a08f
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="quickstart-create-a-python-project-from-a-template-in-visual-studio"></a>빠른 시작: Visual Studio의 템플릿에서 Python 프로젝트 만들기

[Visual Studio 2017에 Python 지원을 설치](installing-python-support-in-visual-studio.md)하면 다양한 템플릿을 사용하여 새 Python 프로젝트를 쉽게 만들 수 있습니다. 이 빠른 시작에서는 템플릿을 사용하여 간단한 Flask 앱을 만듭니다. 결과 프로젝트는 [빠른 시작 - Flask를 사용하여 웹앱 만들기](../ide/quickstart-python.md)를 통해 수동으로 만든 프로젝트와 비슷합니다.

1. Visual Studio 2017을 시작합니다.

1. 상단 메뉴 모음에서 **파일 > 새로 만들기 > 프로젝트...** 를 선택한 다음, **새 프로젝트** 대화 상자에서 "비어 있는 Flask"를 검색하고, 중간 목록에서 "비어 있는 Flask 웹 프로젝트" 템플릿을 선택하고, 프로젝트에 이름을 지정하고, **확인**을 선택합니다.

    ![비어 있는 Flask 웹 프로젝트 템플릿을 사용하여 새 프로젝트 만들기](media/quickstart-python-06-blank-flask-template.png)

1. Visual Studio에서는 "이 프로젝트에는 외부 패키지가 필요합니다."라는 대화 상자를 포함한 메시지를 표시합니다. 템플릿에 Flask에 대한 종속성을 지정하는 `requirements.txt` 파일이 포함되기 때문에 이 대화 상자가 나타납니다. Visual Studio에서는 패키지를 자동으로 설치하고 *가상 환경*을 설치하는 옵션을 제공할 수 있습니다. 전역 환경에 설치하는 것보다 가상 환경을 사용하는 것이 좋습니다. 따라서 **가상 환경에 설치**를 선택하여 계속합니다.

    ![가상 환경에 Flask 설치](media/quickstart-python-07-install-into-virtual-environment.png)

1. Visual Studio에서는 **가상 환경 추가** 대화 상자를 표시합니다. 기본값을 수용하고, **만들기**를 선택한 다음, 권한 상승 요청에 동의합니다.

    > [!Tip]
    > 프로젝트를 시작하는 경우 대부분의 Visual Studio 템플릿에서 요청한 대로 바로 가상 환경을 만드는 것이 좋습니다. 라이브러리를 추가하고 제거하면 가상 환경에서는 시간이 지남에 따라 프로젝트의 정확한 요구 사항을 유지 관리합니다. 그런 다음, 원본 제어를 사용할 때 및 프로덕션 서버에 프로젝트를 배포할 때 다른 개발 컴퓨터에 해당 종속성을 다시 설치하는 데 사용하는 `requirements.txt` 파일을 쉽게 생성할 수 있습니다. 가상 환경 및 해당 기능을 사용하는 이점에 대한 자세한 내용은 [가상 환경 사용](../python/selecting-a-python-environment-for-a-project.md#using-virtual-environments) 및 [requirements.txt를 사용하여 필수 패키지 관리](../python/managing-required-packages-with-requirements-txt.md)를 참조하세요.

1. Visual Studio에서 해당 환경을 만든 후에 **솔루션 탐색기**를 탐색하여 `requirements.txt`와 함께 `app.py` 파일이 있는지 확인합니다. `app.py`를 열어서 템플릿이 두 개의 섹션 추가이 추가된 [빠른 시작 - Flask를 사용하여 웹앱 만들기](../ide/quickstart-python.md)와 같은 코드를 제공하는지 확인합니다.

    먼저 웹 호스트에 앱을 배포할 때 도움이 될 수 있는 `wsgi_app = app.wsgi_app` 줄입니다.

    둘째는 하드 코딩하는 대신 환경 변수를 통해 호스트 및 포트를 설정할 수 있는 시작 코드입니다. 이러한 코드를 사용하면 코드를 변경하지 않고 개발 및 프로덕션 컴퓨터 모두에서 구성을 쉽게 제어할 수 있습니다.

    ```python
    if __name__ == '__main__':
        import os
        HOST = os.environ.get('SERVER_HOST', 'localhost')
        try:
            PORT = int(os.environ.get('SERVER_PORT', '5555'))
        except ValueError:
            PORT = 5555
        app.run(HOST, PORT)
    ```

1. **디버그 > 디버깅하지 않고 시작**을 선택하여 앱을 실행하고 `localhost:5555`에 대한 브라우저를 엽니다.

**질문: Visual Studio에서 제공하는 다른 Python 템플릿은 무엇인가요?**

**응답**: Python 워크로드를 설치하면 Visual Studio에서는 [Flask, Bottle 및 Django 웹 프레임워크](../python/python-web-application-project-templates.md), Azure 클라우드 서비스, 다른 기계 학습 시나리오 및 Python 앱을 포함하는 기존 폴더 구조에서 프로젝트를 만드는 템플릿을 비롯한 다양한 프로젝트 템플릿을 제공합니다. **Python** 언어 노드 및 해당 자식 노드를 선택하여 **파일 > 새로 만들기 > 프로젝트...** 대화 상자를 통해 이러한 항목에 액세스합니다.

또한 Visual Studio에서는 다양한 파일 또는 ‘항목 템플릿’을 제공하여 Python 클래스, Python 패키지, Python 단위 테스트, `web.config` 파일 등을 신속하게 만듭니다. Python 프로젝트가 열려 있는 경우 **프로젝트 > 새 항목 추가** 메뉴 명령을 통해 항목 템플릿에 액세스합니다. [항목 템플릿](python-item-templates.md) 참조를 참조하세요.

템플릿을 사용하면 프로젝트를 시작하거나 파일을 만들 때 상당한 시간을 절약할 수 있고, 다른 앱 형식 및 코드 구조에 대해 알아볼 수 있습니다. 제공되는 기능에 익숙해지도록 다양한 템플릿으로 프로젝트 및 항목을 만드는 데 몇 분이 걸릴 수 있습니다.

**질문: Cookiecutter 템플릿도 사용할 수 있나요?**

**대답**: 예. 사실, Visual Studio에서는 Cookiecutter와의 직접 통합을 제공합니다. 이 기능은 [빠른 시작: Cookiecutter 템플릿으로 프로젝트 만들기](../python/quickstart-04-python-in-visual-studio-project-from-cookiecutter.md)를 통해 배울 수 있습니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [자습서: Visual Studio에서 Python 작업](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>참고 항목

- [기존 Python 인터프리터 수동 식별](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).
- [Visual Studio 2015 이하 버전에서 Python 지원 설치](installing-python-support-in-visual-studio.md)
- [설치 위치](installing-python-support-in-visual-studio.md#install-locations).
