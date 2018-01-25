---
title: "Visual Studio의 Python용 Django 웹 프로젝트 템플릿 | Microsoft Docs"
ms.custom: 
ms.date: 07/13/2017
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
ms.workload:
- python
- data-science
ms.openlocfilehash: b9a6c3240075107edfc5109fa6c62aaf6c23d92b
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2018
---
# <a name="django-web-project-template"></a>Django 웹 프로젝트 템플릿

[Django](https://www.djangoproject.com/)는 신속하고 안전하며 확장성 있는 웹 개발을 위해 고안된 상위 수준 Python 프레임워크입니다. Visual Studio의 Python 지원은 Django 기반 웹 응용 프로그램의 구조를 설정하기 위한 프로젝트 템플릿을 제공합니다. Visual Studio에서 템플릿을 사용하려면 **파일 > 새로 만들기 > 프로젝트**를 선택하고 "Django"를 검색하고 **Django 웹 프로젝트** 템플릿을 선택합니다. 결과 프로젝트에는 기본 SQLite 데이터베이스와 상용구 코드가 포함됩니다. **빈 Django 웹 프로젝트** 템플릿도 이와 유사하지만 데이터베이스를 포함하지 않습니다.

Visual Studio는 Django 프로젝트용 전체 IntelliSense를 제공합니다.

- 템플릿에 전달된 컨텍스트 변수:

    ![컨텍스트 변수에 대한 IntelliSense](media/template-django-intellisense.png)

- 기본 제공 및 사용자 정의 항목에 대한 태깅 및 필터링

    ![태그 및 필터에 대한 IntelliSense](media/template-django-intellisense-filter.png)

- 포함된 CSS 및 JavaScript에 대한 구문 색 지정:

    ![CSS IntelliSense](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)

Visual Studio에서는 Django 프로젝트에 대해 전체 [디버깅 지원](debugging.md)도 제공합니다. 

![중단점](media/template-django-debugging.png)

`manage.py` 파일을 통해 Django 프로젝트를 관리하는 것이 일반적이며, Visual Studio는 이 가정을 따릅니다. 해당 파일을 진입점으로 사용하지 않으면 기본적으로 프로젝트 파일이 손상됩니다. 이 경우 Django 프로젝트로 표시하지 않고 [기존 파일에서 프로젝트를 다시 만들어야](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) 합니다.

## <a name="django-management-console"></a>Django 관리 콘솔

Django 관리 콘솔은 **프로젝트** 메뉴의 다양한 명령을 통해서나 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하여 액세스합니다.

- **Django Shell 열기...**: 모델을 조작할 수 있는 응용 프로그램 컨텍스트에서 셸을 엽니다.

    ![콘솔](media/template-django-console-shell.png)

- **Django Sync DB**: 대화식 창에서 `manage.py syncdb`를 실행합니다.

    ![콘솔](media/template-django-console-sync-db.png)

- **Collect Static**: `manage.py collectstatic --noinput`을 실행하여 `settings.py`의 `STATIC_ROOT`에 지정된 경로에 모든 정적 파일을 복사합니다. [Microsoft Azure에 게시](template-web.md#publishing-to-azure-app-service)할 때 정적 파일은 게시 작업의 일부로 자동으로 수집됩니다.

    ![콘솔](media/template-django-console-collect-static.png)

- **Validate**: `manage.py validate`를 실행하여 `settings.py`의 `INSTALLED_APPS`에 지정된 설치된 모델에서 모든 유효성 검사 오류를 보고합니다.

    ![콘솔](media/template-django-console-validate.png)