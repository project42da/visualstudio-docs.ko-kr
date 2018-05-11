---
ms.topic: include
ms.openlocfilehash: b629de8144e08c7c0019a0a116f84e5877c3a477
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
### <a name="create-a-project-using-django-20"></a>Django 2.0을 사용하여 프로젝트 만들기

현재 빈 Django 웹 프로젝트 템플릿은 최신 Django 1.x 버전을 사용합니다. Django 2.x를 사용하려면 Django 2.x 파일을 Django 1.x 프로젝트로 가져오는 것이 가장 빠릅니다. 이 프로세스를 수행하면 Visual Studio 프로젝트 템플릿에서 처리된 다른 세부 정보를 활용할 수 있습니다.

1. 이전 섹션에서 설명한 대로 “빈 Django 웹 프로젝트” 템플릿을 사용하여 Django 1.x 프로젝트를 만듭니다. 그러나 “This project requires external dependencies”(이 프로젝트에는 외부 종속성이 필요합니다.)라는 프롬프트가 표시되면 **직접 설치**를 선택합니다. 이후 단계에서 제거되는 종속성이 설치되지 않도록 하려면 이 옵션을 선택합니다.

1. 명령 프롬프트를 열고 임시 폴더로 이동합니다.

1. `pip install django`를 실행하여 전역 Python 환경에 최신 Django 패키지를 설치합니다.

1. `django-admin startproject <project_name>`을 실행합니다. 이때 `<project_name>`을 1단계에서 사용한 것과 동일한 프로젝트 이름(예: “HelloDjango”)으로 바꿉니다. `startproject` 명령은 `__init.py__`, `settings.py`, `urls.py` 및 `wsgi.py` 파일을 포함하는, `<project_name>`과 일치하는 폴더와 함께 `manage.py` 파일을 만듭니다.

1. Visual Studio에서 프로젝트의 Django 1.x 파일을 다음과 같이 Django 2.x 파일로 바꿉니다.

  a. **솔루션 탐색기**에서 `manage.py` 및 Django 앱 폴더를 삭제합니다.
  b. 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 기존 항목...** 명령을 선택한 후 4단계에서 만든 `manage.py` 파일로 이동하여 선택하고 **확인**을 선택합니다. 그러면 Visual Studio에서 해당 파일을 프로젝트에 복사합니다.
  c. 프로젝트를 다시 마우스 오른쪽 단추로 클릭하고 **추가 > 기존 폴더...** 명령을 선택한 후 4단계에서 만든 앱 폴더로 이동하여 선택하고 **확인**을 선택합니다. 그러면 Visual Studio에서 해당 폴더 전체와 파일 네 개를 프로젝트에 복사합니다.
  d. `manage.py`를 마우스 오른쪽 단추로 클릭하고 **시작 파일로 설정**을 선택합니다.

  > [!Important]
  > Visual Studio 프로젝트에 표시된 앱 이름은 `django-admin` 유틸리티에 사용된 `<project_name>`과 일치해야 하는데, 이 유틸리티는 Python 코드 파일 내에서 네임스페이스로 해당 이름을 사용하기 때문입니다.

1. `requirements.txt`를 열고 내용을 `django >=2.0, <3`으로 변경한 후 파일을 저장합니다.

1. **솔루션 탐색기**에서 **Python 환경** 노드를 마우스 오른쪽 단추로 클릭하고 **가상 환경 추가...** 를 선택합니다. 대화 상자가 표시되면 기본값을 그대로 사용하고 **만들기**를 선택합니다. 관리자 권한에 대한 프롬프트가 표시되면 수락합니다.