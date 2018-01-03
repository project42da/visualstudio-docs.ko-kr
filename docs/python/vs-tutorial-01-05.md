---
title: "Visual Studio에서 Python 사용, 5단계 | Microsoft Docs"
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
ms.openlocfilehash: 2acd8aebda03d7d9809563a6c1959c8dd69bf96e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="step-5-installing-packages-in-your-python-environment"></a>5단계: Python 환경에서 패키지 설치

**이전 단계: [디버거에서 코드 실행](vs-tutorial-01-04.md)**

Python 개발자 커뮤니티에서는 사용자 소유의 프로젝트에 통합할 수 있는 유용한 패키지가 무수히 만들어졌습니다. Visual Studio는 Python 환경에서 패키지를 관리하기 위한 UI를 제공합니다.

1. **보기> Other Windows(다른 창) > Python 환경** 메뉴 명령을 선택합니다. **Python 환경** 창이 솔루션 탐색기에 대한 피어로 열리고 사용할 수 있는 다양한 환경을 표시합니다. 목록에는 Visual Studio 설치 관리자를 사용하여 설치한 환경과 별도로 설치한 환경이 모두 포함됩니다. 굵게 표시된 환경은 새 프로젝트에 사용되는 기본 환경입니다.

  ![Python 환경 창](media/environments-default-view-blue.png)

1. 환경의 **개요** 탭에서는 환경의 설치 폴더 및 인터프리터와 함께 해당 환경에 대한 대화형 창에 빠르게 액세스할 수 있습니다. 예를 들어 **대화형 창 열기**를 선택하면 Visual Studio에서 해당 특정 환경에 대한 대화형 창이 나타납니다.

1. **패키지** 탭을 선택하면 현재 환경에 설치되어 있는 패키지 목록이 표시됩니다.

  ![환경에 설치된 패키지](media/environments-installed-packages-blue.png)

1. 검색 필드에 해당 이름을 입력하여 `matplotlib`를 설치한 다음 `pip install`을 선택합니다.

  ![환경에 matplotlib 설치](media/environments-add-matplotlib1.png)

1. 메시지가 표시되면 권한 상승에 동의하여 수행합니다.
 
1. 패키지가 설치된 후 Python 환경 창에 나타납니다. 패키지의 오른쪽에 있는 **X**를 누르면 제거됩니다. 

  ![환경에 matplotlib 설치 완료](media/environments-add-matplotlib2.png)

  환경 아래에 있는 작은 진행률 표시줄은 Visual Studio에서 새로 설치된 패키지에 대한 IntelliSense 데이터베이스를 빌드 중임을 나타냅니다. **IntelliSense** 탭에 더 자세한 정보가 표시됩니다. 해당 데이터베이스가 완료될 때까지 자동 완성 및 구문 검사와 같은 IntelliSense 기능은 해당 패키지에 대한 편집기에서 활성화되지 않습니다.

1. **파일 > 새로 만들기 > 프로젝트**로 새 프로젝트를 만들면서 “Python 응용 프로그램” 템플릿을 선택합니다. 표시되는 코드 파일에서 이전 자습서 단계와 같이 코사인 웨이브를 만드는, 이번에만 도표로 표시된 다음 코드를 붙여넣습니다.

    ```python
    import numpy as np     # installed with matplotlib
    import matplotlib.pyplot as plt
    from math import radians

    def main():
        x = np.arange(0, radians(1800), radians(12))
        plt.plot(x, np.cos(x), 'b')
        plt.show()

    main()
    ```

1. 디버거를 사용하거나(F5) 디버거를 사용하지 않고(Ctrl + F5) 프로그램을 실행하여 출력을 확인합니다.

  ![matplotlib의 출력 예제](media/environments-add-matplotlib3.png)

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [Git 작업](vs-tutorial-01-06.md)

### <a name="going-deeper"></a>자세히 알아보기

- [Python 환경](python-environments.md)
