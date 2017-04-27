---
title: "Visual Studio용 Python 도구에서 Django 웹 프로젝트 템플릿 | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c479be58-13eb-4d77-9a27-c97ddc290963
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
ms.sourcegitcommit: a42f5a30375192c89c9984e40ba0104da98d7253
ms.openlocfilehash: 7f65641fbf15edfe16931badc19602a0fc773bff
ms.lasthandoff: 03/07/2017

---

# <a name="django-web-project-template"></a>Django 웹 프로젝트 템플릿

[Django](https://www.djangoproject.com/)는 신속하고 안전하며 확장성 있는 웹 개발을 위해 고안된 상위 수준 Python 프레임워크입니다. PTVS(Python Tools for Visual Studio)는 Django 기반 웹 응용 프로그램의 구조를 설정하기 위한 프로젝트 템플릿을 제공합니다. Visual Studio에서 템플릿을 사용하려면 **파일 > 새로 만들기 > 프로젝트**를 선택하고 "Django"를 검색하고 "Django 웹 프로젝트" 템플릿을 선택합니다. 결과 프로젝트에는 기본 SQLite 데이터베이스와 상용구 코드가 포함됩니다. "빈 Django 웹 프로젝트" 템플릿도 이와 유사하지만 데이터베이스를 포함하지 않습니다.

PTVS는 Django 프로젝트용 전체 IntelliSense를 제공합니다.

- 템플릿에 전달된 컨텍스트 변수:

    ![컨텍스트 변수에 대한 IntelliSense](media/template-django-intellisense.png)

- 기본 제공 및 사용자 정의 항목에 대한 태깅 및 필터링

    ![태그 및 필터에 대한 IntelliSense](media/template-django-intellisense-filter.png)

- 포함된 CSS 및 JavaScript에 대한 구문 색 지정:

    ![CSS IntelliSense](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)


PTVS에서는 Django 프로젝트에 대해 전체 [디버깅 지원](debugging.md)도 제공합니다. 

![중단점](media/template-django-debugging.png)

## <a name="django-management-console"></a>Django 관리 콘솔

Django 관리 콘솔은 **프로젝트** 메뉴에서 다양한 명령을 통해서나 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하여 액세스합니다.

- **Django Shell 열기...**: 모델을 조작할 수 있는 응용 프로그램 컨텍스트에서 셸을 엽니다.

    ![콘솔](media/template-django-console-shell.png)

- **Django Sync DB**: 대화식 창에서 `manage.py syncdb`를 실행합니다.

    ![콘솔](media/template-django-console-sync-db.png)

- **Collect Static**: `manage.py collectstatic --noinput`을 실행하여 `settings.py`의 `STATIC_ROOT`에 지정된 경로에 모든 정적 파일을 복사합니다. [Microsoft Azure에 게시](template-web.md#publishing-to-azure-app-service)할 때 정적 파일은 게시 작업의 일부로 자동으로 수집됩니다.

    ![콘솔](media/template-django-console-collect-static.png)

- **Validate**: `manage.py validate`를 실행하여 `settings.py`의 `INSTALLED_APPS`에 지정된 설치된 모델에서 모든 유효성 검사 오류를 보고합니다.

    ![콘솔](media/template-django-console-validate.png)