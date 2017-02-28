---
title: "Visual Studio에서 Python 시작 | Microsoft 문서"
ms.custom: 
ms.date: 1/3/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33f4f6fb-0ae4-4234-9df2-531f2d3af17f
caps.latest.revision: 11
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
ms.sourcegitcommit: 7d0b0b0b12b9d65f26b67d6f797abc0cf7a0c2c9
ms.openlocfilehash: e7cc978dabb401a8e9bab6791988aa737edb76b0
ms.lasthandoff: 02/22/2017

---
# <a name="getting-started-with-python-in-visual-studio"></a>Visual Studio에서 Python 시작

Python([http://python.org/download/](http://python.org/download/))은 안정적이고, 유연하고, 배우기 쉽고, 무료로 사용할 수 있고, 강력한 개발자 커뮤니티에서 지원하고, 많은 무료 라이브러리가 제공되는 널리 사용되는 프로그래밍 언어입니다. Python은 모든 주요 운영 체제에서 작동하고 웹 응용 프로그램, 웹 서비스, 데스크톱 앱, 스크립팅, 과학적 컴퓨팅을 비롯한 다양한 목적에 유용합니다. 따라서 많은 대학교, 과학자, 일반 개발자, 전문 개발자에 의해 사용됩니다.

이 언어에 대한 자세히 알아보려면 [Python for Beginners](https://www.python.org/about/gettingstarted/)(초보자를 위한 Python)(python.org)에서 시작하세요.

## <a name="python-tools-for-visual-studio"></a>Python Tools for Visual Studio

PTVS(Visual Studio용 Python 도구)는 프로젝트 시스템 및 템플릿, 다양한 편집 기능 및 IntelliSense, 전체 기능을 제공하는 디버깅, 다양한 기타 도구를 비롯하여 강력한 Python 개발 환경을 제공하는 Visual Studio용 무료 오픈 소스 확장입니다.

이 확장은 다음 기능을 제공합니다.

- 여러 해석기 지원: 다양한 버전의 CPython, IronPython 및 IPython
- Python 코드의 폴더 구조를 암시적으로 선택하고 앱 코드, 테스트 코드, 웹 페이지, JavaScript, 빌드 스크립트 등을 식별할 수 있도록 명시적으로 제어할 수 있는 프로젝트 시스템
- 콘솔, 웹, Azure, 데이터 과학 및 기타 형식의 프로젝트에 대한 프로젝트 템플릿
- 색 지정, 모든 코드 및 라이브러리에 대한 자동 완성, 시그니처 도움말, 클래스 뷰, 정의로 이동, 모든 참조 찾기, 리팩터링 등을 포함한 다양한 편집 및 코드 이해 기능
- 대화형(REPL) 창
- Visual Studio 프로젝트 없이 풍부한 디버깅, 기존 실행 파일에 대한 기능, 혼합 모드 디버깅, Mac/Windows/Linux로 원격 디버깅 및 대화형 창 내에서 디버깅

- 데이터 시각화를 사용한 IPython
- IronPython 및 .NET/WPF 지원
- 프로파일링 도구
- 테스트 도구
- [Python용 Azure SDK](#azure-sdk-for-python)

다음 리소스는 시작하는 데 도움이 될 수 있습니다.

- [Visual Studio용 Python 도구 설치](https://www.visualstudio.com/vs/python/).
- [설치 가이드](https://github.com/Microsoft/PTVS/wiki/PTVS-Installation)
- [Getting started and deep dive short videos](https://www.youtube.com/playlist?list=PLReL099Y5nRdLgGAdrb_YeTdEnd23s6Ff)(PTVS 시작 및 자세히 알아보기 동영상)
- 설치 및 기능 데모(27분)](https://www.youtube.com/watch?v=JNNAOypc6Ek)
- [문서](https://github.com/Microsoft/PTVS/wiki)
- [소스 코드](https://github.com/Microsoft/ptvs)


## <a name="azure-sdk-for-python"></a>Python용 Azure SDK

Windows, Mac 및 Linux를 지원하는 Python용 Azure SDK을 통해 Microsoft Azure 서비스를 쉽게 이용하고 관리할 수 있습니다. 자세한 내용은 다음 리소스를 참조하세요.

- SDK를 설치하려면 [Python Package Index](https://pypi.python.org/pypi/azure)(Python 패키지 인덱스)를 사용하거나 Azure 문서에서 [Python 및 SDK 설치](https://azure.microsoft.com/documentation/articles/python-how-to-install/)를 따르세요.
- [Python 개발자 센터용 Azure SDK](http://azure.microsoft.com/en-us/develop/python/)에는 설치부터 자습서 포함 설명서에 이르기까지 많은 도움말이 있습니다.  중요 사항은 다음과 같습니다.
- 방법 가이드:
  - [Python에서 Azure Blob Storage를 사용하는 방법](http://azure.microsoft.com/en-us/develop/python/how-to-guides/blob-service/)
  - [Python에서 큐 저장소를 사용하는 방법](http://azure.microsoft.com/en-us/develop/python/how-to-guides/queue-service/)
  - [Python에서 테이블 저장소를 사용하는 방법](http://azure.microsoft.com/en-us/develop/python/how-to-guides/table-service/)
  - [Service Bus 큐를 사용하는 방법](http://azure.microsoft.com/en-us/develop/python/how-to-guides/service-bus-queues/)   - [Service Bus 토픽 및 구독을 사용하는 방법](http://azure.microsoft.com/en-us/develop/python/how-to-guides/service-bus-topics/)
  - [Python에서 서비스 관리를 사용하는 방법](http://azure.microsoft.com/en-us/develop/python/how-to-guides/service-management/)
- [SDK's GitHub repository](https://github.com/Azure/azure-sdk-for-python)(SDK의 GitHub 리포지토리)에는 API에 대한 좋은 정보 출처이기도 한 [unit tests](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-mgmt/tests)(단위 테스트)가 있습니다.


## <a name="scientific-computing"></a>과학적 컴퓨팅
모든 Python 데이터 과학자 라이브러리 외에도 Visual Studio용 Python 도구는 Azure에서 호스트할 수 있는 IPython 및 IPython Notebook을 지원합니다.

[University of California, Irvine](http://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy-stack)(캘리포니아 대학교 어바인 캠퍼스)에서 IPython 및 과학적 컴퓨팅 라이브러리(matplotlib, scipy, numpy 등)를 가져오는 것이 좋습니다.

## <a name="see-also"></a>참고 항목
 [PTVS 시작: Visual Studio 설정](../python/getting-started-with-ptvs-setting-up-visual-studio.md)
 [PTVS 시작: 코딩 시작(프로젝트)](../python/getting-started-with-ptvs-start-coding-projects.md)
 [PTVS 시작: 코드 편집](../python/getting-started-with-ptvs-editing-code.md)
 [PTVS 시작: 디버깅](../python/getting-started-with-ptvs-debugging.md)
 [PTVS 시작: 대화형 Python](../python/getting-started-with-ptvs-interactive-python.md)
 [PTVS 시작: Azure에서 웹 사이트 빌드](../python/getting-started-with-ptvs-building-a-website-in-azure.md)
