---
title: "빠른 시작: Visual Studio를 사용하여 첫 번째 Python 웹앱 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 12/1/2017"
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
ms.devlang: python
author: kraigb
ms.author: kraigb
manager: ghogen
dev_langs: python
ms.workload: python
ms.openlocfilehash: bf0a6e187a98a03d3beed33537fe5244ecd5d35d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-use-visual-studio-to-create-your-first-python-web-app"></a>빠른 시작: Visual Studio를 사용하여 첫 번째 Python 웹앱 만들기

Visual Studio IDE(통합 개발 환경)에 대한 5~10분 분량의 소개에서는 간단한 Python 웹 응용 프로그램을 만듭니다. 아직 Visual Studio를 설치하지 않은 경우 [여기](http://www.visualstudio.com)에서 평가판을 설치합니다.

## <a name="create-the-project"></a>프로젝트를 만듭니다.

1. Visual Studio 2017을 엽니다.

1. 메뉴 모음에서 **파일 > 새로 만들기 > 프로젝트...**를 차례로 선택합니다.

1. **새 프로젝트** 대화 상자의 왼쪽 창에서 **다른 언어**를 확장한 다음 **Python**을 선택합니다. 가운데 창에서 **웹 프로젝트**를 선택하고 프로젝트 이름(예: "HelloPython")을 입력한 다음 **확인**을 선택합니다.

    Python 프로젝트 템플릿이 표시되지 않으면 **새 프로젝트** 대화 상자를 취소하고 나가서 위쪽 메뉴 모음에서 **도구 > 도구 및 기능 가져오기...**를 선택하여 Visual Studio 설치 관리자를 엽니다. **Python 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

    ![Visual Studio 설치 관리자의 Python 개발 작업](../python/media/installation-python-workload.png)

1. 오른쪽 창의 **솔루션 탐색기**에 새 프로젝트가 열립니다. 프로젝트에 다른 파일이 없기 때문에 이 시점에는 프로젝트가 비어 있습니다.

    ![새로 만든 빈 프로젝트를 보여주는 솔루션 탐색기](media/quickstart-python-01-empty-project.png)

## <a name="install-the-falcon-library"></a>Falcon 라이브러리 설치

Python의 웹앱은 다수의 사용 가능한 Python 라이브러리 중 하나를 웹 요청 라우팅과 응답 형성과 같은 낮은 수준의 세부 사항을 처리하기 위해 거의 항상 사용합니다. Visual Studio의 Python 개발 워크로드에는 Bottle, Flask 및 Django 라이브러리를 기반으로 구축된 [다양한 웹앱 템플릿](../python/template-web.md)이 제공됩니다.

이 빠른 시작에서는 [Falcon](https://falconframework.org/)이라는 다른 라이브러리를 사용하여 패키지를 설치하고 처음부터 웹앱을 만드는 과정을 경험합니다. 간단히 설명하기 위해, 다음 단계는 Falcon을 기본 전역 환경에 설치합니다.

1. 프로젝트에서 **Python 환경** 노드를 확장하여 프로젝트의 기본 환경을 확인합니다.

    ![기본 환경을 보여 주는 솔루션 탐색기](media/quickstart-python-02-default-environment.png)

1. 환경을 마우스 오른쪽 단추로 클릭하고 **Python 패키지 설치...**를 선택합니다. 이 명령은 **패키지** 탭에 **Python 환경** 창을 엽니다. 검색 필드에 "falcon"을 입력하고 **"pip install falcon" from PyPI**을 선택합니다. 관리자 권한에 대한 프롬프트가 표시되면 수락하고 Visual Studio의 **출력** 창에서 진행률을 살펴봅니다.

    ![Falcon 라이브러리 설치하기](media/quickstart-python-03-install-package.png)

1. 설치 후에는 **솔루션 탐색기**의 환경에 라이브러리가 표시되며 Python 코드에서 해당 라이브러리를 사용할 수 있습니다.

    ![Falcon 라이브러리가 설치됨](media/quickstart-python-04-package-installed.png)

일반적으로 개발자는 전역 환경에 라이브러리를 설치하는 대신 특정 프로젝트에 대한 라이브러리를 설치하는 "가상 환경"을 만듭니다. Visual Studio의 여러 Python 프로젝트 템플릿에는 템플릿이 의존하는 라이브러리가 나열된 `requirements.txt` 파일이 있습니다. 이러한 템플릿 중 하나에서 프로젝트를 생성하면 라이브러리가 설치될 가상 환경 만들기가 트리거됩니다. 자세한 내용은 [Python 환경 - 가상 환경](../python/python-environments.md#virtual-environments)을 참조하세요.

## <a name="add-a-code-file"></a>코드 파일 추가

이제 작은 웹앱을 구현하기 위해 약간의 Python 코드를 추가할 준비가 되었습니다.

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목...**을 차례로 선택합니다. 대화 상자가 나타나면 **빈 Python 파일**을 선택하고 이름을 `hello.py`라고 지정하고 **확인**을 선택합니다. Visual Studio의 편집기 창에서 파일이 자동으로 열립니다. (일반적으로 **추가 > 새 항목...** 명령은 프로젝트에 여러 종류의 파일을 추가하는 좋은 방법입니다. 항목 템플릿에 유용한 상용구 코드가 종종 제공되기 때문입니다.)

1. `hello.py`에 다음 코드를 복사하여 붙여넣거나 입력합니다.

    ```python
    import falcon
    api = falcon.API()

    # In Falcon, define a class for each resource; the on_get 
    # method then handles any GET requests.

    class HelloResource:
        def on_get(self, req, resp):
            resp.status = falcon.HTTP_200  # 200 is the default
            resp.body = "Hello, Python!"

    # Resources are represented by long-lived class instances
    hello = HelloResource()

    # Instruct Falcon to route / and /hello to the HelloResource
    api.add_route('/', hello)
    api.add_route('/hello', hello)

    if __name__ == "__main__":
        from wsgiref.simple_server import make_server

        # Run the web server on localhost:8080
        print("Starting web app server")
        srv = make_server('localhost', 8080, api)
        srv.serve_forever()
    ```

Falcon에 대한 자세한 내용은 [Falcon 빠른 시작](https://falcon.readthedocs.io/en/stable/user/quickstart.html)(falcon.readthedocs.io)을 참조하세요.

## <a name="run-the-application"></a>응용 프로그램 실행

1. **솔루션 탐색기**에서 `hello.py`를 마우스 오른쪽 단추로 클릭하고, **시작 파일로 설정**을 선택합니다. 이 명령은 앱을 실행할 때 Python으로 실행할 코드 파일을 식별합니다.

1. **솔루션 탐색기**에서 "Hello Python" 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. 그런 다음 **디버그** 탭을 선택하고 **포트 번호** 속성을 `8080`으로 설정합니다. 이 단계를 수행하면 Visual Studio가 임의의 포트를 사용하는 대신 `localhost:8080`으로 브라우저를 시작합니다.

1. **디버그 > 디버깅하지 않고 시작**(Ctrl+F5)을 선택하여 변경 내용을 파일에 저장하고 앱을 실행합니다.

1. 명령 창에 "Starting web app server"(웹앱 서버 시작 중) 메시지가 표시된 다음 브라우저 창에 `localhost:8080`이 열리고 "Hello, Python!"이라는 메시지가 표시됩니다. 명령 창에 GET 요청도 나타납니다. (명령 창에 Python 대화형 셸만 보이거나 창이 화면에서 잠시 깜박이면 위의 1단계에서 `hello.py`를 시작 파일로 설정했는지 확인합니다.)

1. 명령 창을 닫아서 앱을 중지합니다.

## <a name="next-steps"></a>다음 단계

빠른 시작을 완료하셨습니다. 지금까지 Python과 Visual Studio IDE에 대해 살펴보았습니다. 대화형 창 사용, 디버깅, 데이터 시각화 및 Git 작업을 포함하여, Visual Studio의 Python에 대한 자습서를 계속 진행하려면 아래 단추를 선택하십시오.

> [!div class="nextstepaction"]
> [자습서: Visual Studio에서 Python 시작](../python/vs-tutorial-01-01.md).

- [Visual Studio의 Python 웹앱 템플릿](../python/template-web.md)에 대해 알아보기
- [Visual Studio IDE](../ide/visual-studio-ide.md)에 대해 자세히 알아보기
- [Visual Studio 디버거](../debugger/debugger-feature-tour.md) 사용 방법 알아보기