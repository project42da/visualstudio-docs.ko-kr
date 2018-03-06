---
title: "Visual Studio에서 Python 환경 및 인터프리터를 관리하는 방법 | Microsoft Docs"
description: "Visual Studio에서 Python 환경 창을 사용하여 전역 및 가상 환경을 관리하며, Python 인터프리터 설치, 패키지 설치, 검색 경로 설정, Visual Studio 프로젝트의 환경 관리를 위한 사용자 지정 환경을 설정하는 방법입니다."
ms.custom: 
ms.date: 02/20/2018
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
ms.openlocfilehash: 570ce6beccf14c9f04fcd3e21b86a8d00a3d607f
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="managing-python-environments-in-visual-studio"></a>Visual Studio에서 Python 환경 관리

Python ‘환경’은 Python 코드를 실행할 컨텍스트이며 전역, 가상 및 conda 환경을 포함합니다. 환경은 인터프리터, 라이브러리(일반적으로 Python 표준 라이브러리) 및 설치된 패키지 집합으로 구성됩니다. 이러한 모든 구성 요소에 따라, 어떤 언어로 구성되고 구문이 유효한지, 어떤 운영 체제 기능에 액세스할 수 있으며 어떤 패키지를 사용할 수 있는지가 결정됩니다.

Windows의 Visual Studio에서는 이 문서에 설명된 대로 [Python 환경](#managing-python-environments-in-visual-studio) 창에서 이러한 환경을 관리하고 새 프로젝트의 기본값으로 환경을 선택합니다. 지정된 프로젝트의 경우 기본값을 사용하는 대신 특정 환경을 선택할 수도 있습니다.

**참고**: Visual Studio에서 Python을 처음 사용하는 경우 필요한 배경은 다음 문서를 참조하세요.

- [Visual Studio에서 Python 작업](overview-of-python-tools-for-visual-studio.md)
- [Visual Studio에서 Python 지원 설치](installing-python-support-in-visual-studio.md)

또한 **파일 > 열기 > 폴더** 명령을 사용하여 폴더로만 열리는 Python 코드의 환경을 관리할 수 없습니다. 대신 Visual Studio의 환경 기능을 사용하기 위해 [기존 코드에서 Python 프로젝트를 만듭니다](quickstart-01-python-in-visual-studio-project-from-existing-code.md).

## <a name="types-of-environments"></a>환경 유형

### <a name="global-environments"></a>글로벌 환경

각 Python 설치(예: Python 2.7, Python 3.6 및 Anaconda 4.4.0 등, [Python 인터프리터 선택 및 설치](installing-python-interpreters.md) 참조)는 고유한 전역 환경을 유지 관리합니다. 각 환경은 특정 Python 인터프리터, 표준 라이브러리 및 사전 설치된 패키지 집합으로 구성됩니다. 패키지를 전역 환경에 설치하면 해당 환경을 사용하는 모든 프로젝트에서 사용할 수 있습니다. 환경이 파일 시스템의 보호 영역(예: `c:\program files` 내)에 있는 경우 패키지를 설치하려면 관리자 권한이 필요합니다.

전역 환경은 컴퓨터의 모든 프로젝트에서 사용할 수 있습니다. Visual Studio에서는 특별히 프로젝트별로 다른 항목을 선택하지 않는 한 하나의 전역 환경을 모든 프로젝트에 사용되는 기본값으로 선택합니다. 자세한 내용은 [프로젝트의 환경 선택](selecting-a-python-environment-for-a-project.md)을 참조하세요.

### <a name="virtual-environments"></a>가상 환경

전역 환경에 설치된 패키지는 해당 환경을 사용하는 모든 프로젝트에서 사용 가능하므로 두 프로젝트에 호환되지 않은 패키지 또는 동일한 패키지의 서로 다른 버전이 필요한 경우 충돌이 발생할 수 있습니다. 가상 환경은 전역 환경의 인터프리터 및 표준 라이브러리를 사용하지만 해당 패키지 저장소를 격리된 폴더에서 유지 관리하여 이러한 충돌을 방지합니다.

Visual Studio에서는 프로젝트의 하위 폴더에 저장된 특정 프로젝트에 대한 가상 환경을 만들 수 있습니다([가상 환경 만들기](selecting-a-python-environment-for-a-project.md#creating-a-virtual-environment) 참조). 프로젝트 파일은 가상 환경도 식별합니다. 또한 Visual Studio는 해당 가상 환경에 설치하는 모든 패키지를 프로젝트의 `requirements.txt` 파일에 기록합니다. 프로젝트를 공유하고 다른 개발자가 컴퓨터에서 이 프로젝트를 열 경우 Visual Studio에서는 가상 환경을 다시 만드는 옵션을 제공합니다.

### <a name="conda-environments"></a>Conda 환경

Conda 환경은 `conda` 도구를 사용하여 만든 환경입니다. 일반적으로 Conda 환경은 Anaconda 설치 내의 `envs` 폴더에 저장되므로 전역 환경과 비슷하게 작동합니다. 예를 들어 새 패키지를 conda 환경에 설치하면 해당 환경을 사용하는 모든 프로젝트에서 해당 패키지를 사용할 수 있습니다.

현재 Visual Studio에서는 conda 환경을 자동으로 검색하지 않지만 Visual Studio에서 conda 환경을 수동으로 지정할 수 있습니다. [기존 환경 수동 식별](#manually-identifying-an-existing-environment)을 참조하세요.

## <a name="the-python-environments-window"></a>Python 환경 창

Visual Studio에서 인식하는 환경이 **Python 환경** 창에 표시됩니다. 창을 열려면 다음 방법 중 하나를 사용합니다.

- **보기> Other Windows(다른 창) > Python 환경** 메뉴 명령을 선택합니다.
- 솔루션 탐색기에서 프로젝트의 **Python 환경** 노드를 마우스 오른쪽 단추로 클릭하고 **모든 Python 환경 보기**를 선택합니다.

    ![솔루션 탐색기에서 모든 환경 명령 보기](media/environments-view-all.png)

두 경우 모두 **Python 환경** 창은 솔루션 탐색기의 형제 탭으로 나타납니다.

![Python 환경 창](media/environments-default-view.png)

위의 이미지는 Visual Studio에서 Anaconda 5.0.0과 함께 Python 3.6(32비트)의 설치 두 개를 발견했음을 보여줍니다.

굵게 표시된 기본 환경은 Python 3.6(이 경우 Anaconda 설치의 일부)으로, Visual Studio가 모든 새로운 프로젝트에 사용하는 환경입니다. 창의 하단 부분에 있는 명령은 선택된 Python 3.6 인터프리터에 적용되며, 여기서 볼 수 있듯이 이 인터프리터는 `C:\Python36-32`에 있는 특정 설치입니다. 원하는 환경이 표시되지 않으면 [기존 인터프리터 수동 식별](#manually-identifying-an-existing-interpreter)을 참조하세요.

나열된 각 환경의 오른쪽에는 해당 환경에 대한 대화형 창을 여는 컨트롤이 있습니다. 해당 환경의 IntelliSense 데이터베이스를 새로 고치는 다른 컨트롤이 나타날 수 있습니다.

환경 목록 아래에는 [Python 환경 창 탭 참조](python-environments-window-tab-reference.md)에 설명된 **개요**, **패키지** 및 **IntelliSense** 옵션에 대한 드롭다운 선택기가 있습니다. 또한 **Python 환경** 창을 적당히 넓게 확장하면 이러한 옵션이 탭으로 표시되어 작업하기가 더 편리할 수 있습니다.

![Python 환경 창 확장된 보기](media/environments-expanded-view.png)

> [!Note]
> Visual Studio에서는 system-site-packages 옵션을 적용하지만 Visual Studio 내에 이를 변경하는 방법은 제공하지 않습니다.

|   |   |
|---|---|
| ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기") | Visual Studio의 Python 환경에 대한 [비디오(Microsoft Virtual Academy)를 시청](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567)하세요(2분 35초).|

### <a name="what-if-no-environments-appear"></a>환경이 나타나지 않으면 어떻게 하나요?

환경이 나타나지 않으면 Visual Studio가 표준 위치에서 Python 설치를 검색하지 못한 것입니다. 예를 들어 Visual Studio 2017을 설치했지만 Python 워크로드에 대한 설치 관리자 옵션에서 모든 인터프리터 옵션을 선택 취소했을 수 있습니다. 마찬가지로 Visual Studio 2015 이하를 설치했지만 인터프리터를 수동으로 설치하지 않았을 수 있습니다([Python 인터프리터 선택 및 설치](installing-python-interpreters.md) 참조).

컴퓨터에 Python 인터프리터가 있는 것을 알지만 Visual Studio(모든 버전)가 이를 검색하지 못하는 경우 **+ 사용자 지정...** 명령을 사용하여 해당 위치를 수동으로 지정합니다. 다음 섹션 [기존 환경 수동 식별](#manually-identifying-an-existing-environment)을 참조하세요.

> [!Tip]
> Visual Studio는 python.org의 설치 관리자를 사용하여 Python2.7.11을 2.7.14로 업그레이드하는 경우와 같은 기존 인터프리터의 업데이트를 검색합니다. 설치 과정에서 **Python 환경** 목록에서 이전 환경이 사라진 후 업데이트가 그 자리에 나타납니다.
>
> 그러나 파일 시스템을 사용하여 인터프리터 및 해당 환경을 수동으로 이동할 경우 Visual Studio에서는 새 위치를 알 수 없습니다. 자세한 내용은 [인터프리터 이동](installing-python-interpreters.md#moving-an-interpreter)을 참조하세요.

## <a name="manually-identifying-an-existing-environment"></a>기존 환경 수동 식별

Conda 환경을 포함하여 비표준 위치에 설치된 환경을 식별하려면 다음 단계를 수행합니다.

1. **Python 환경** 창에서 **+ 사용자 지정...**을 선택하면 **구성** 탭이 열립니다.

    ![새 사용자 지정 환경의 기본 보기](media/environments-custom-1.png)

1. **설명** 필드에 환경에 대한 이름을 입력합니다.

1. **접두사 경로** 필드에 인터프리터의 경로를 입력하거나 찾습니다(**...*** 사용).

1. Visual Studio가 해당 위치(예: conda 환경에 대해 아래에 표시된 경로)에서 Python 인터프리터를 검색할 경우 **자동 검색** 명령을 사용할 수 있습니다. *’자동 검색’을 선택하면 나머지 필드가 완료됩니다. 해당 필드를 수동으로 완료할 수도 있습니다.

    ![자동 검색 명령 사용](media/environments-custom-2.png)

    ![자동 검색을 사용한 후 환경 필드 완료](media/environments-custom-3.png)

1. 필드에 원하는 값이 포함되면 **적용**을 선택하여 구성을 저장합니다. 이제 Visual Studio 내에서 다른 환경과 같이 해당 환경을 사용할 수 있습니다.

1. 수동으로 식별된 환경을 제거해야 하는 경우 **구성** 탭에서 **제거** 명령을 선택합니다. 자동 감지 환경에서는 이 옵션을 제공하지 않습니다. 자세한 내용은 [구성 탭](python-environments-window-tab-reference.md#configure-tab)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Python 인터프리터 설치](installing-python-interpreters.md)
- [프로젝트의 인터프리터 선택](selecting-a-python-environment-for-a-project.md)
- [종속성에 대해 requirements.txt 사용](managing-required-packages-with-requirements-txt.md)
- [검색 경로](search-paths.md)
- [Python 환경 창 참조](python-environments-window-tab-reference.md)