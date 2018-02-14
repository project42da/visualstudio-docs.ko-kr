---
title: "Visual Studio의 IPython REPL | Microsoft Docs"
description: "IPython 모드의 Visual Studio 대화형 창은 대화형 병렬 컴퓨팅 기능이 있는, 사용자에게 친숙한 대화형 개발 환경에 사용합니다."
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 7ee982a1068f2ea89299b75ca825f7a7c1c4e6b0
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="using-ipython-in-the-interactive-window"></a>대화형 창에서 IPython 사용

IPython 모드의 Visual Studio 대화형 창은 사용자에게 친숙한 고급 대화형 개발 환경으로, 대화형 병렬 컴퓨팅 기능을 지원합니다. 이 항목에서는 일반적인 [대화형 창](python-interactive-repl-in-visual-studio.md) 기능도 모두 사용할 수 있는 Visual Studio 대화형 창에서 IPython을 사용하는 과정을 안내합니다.

이 연습에서는 IPython 및 필요한 라이브러리를 포함하는 [Anaconda](https://www.continuum.io) 환경이 설치되어 있어야 합니다.

> [!Note]
> Interactive 옵션 양식에서 IPython을 선택할 수는 있지만 IronPython은 IPython을 지원하지 않습니다. 자세한 내용은 [기능 요청](https://github.com/Microsoft/PTVS/issues/84)을 참조하세요.

1. Visual Studio를 열고 Python 환경 창(**보기 > 다른 창 > Python 환경**)으로 전환한 다음 IPython을 시작할 때 표시된 Python 환경을 선택합니다.

1. **패키지**(또는 **pip**) 탭을 확인하여 `IPython` 및 `matplotlib`가 나열되는지 확인합니다. 그렇지 않은 경우 여기에서 설치하세요.

1. **개요** 탭을 선택한 다음 **IPython 대화형 모드 사용**을 선택합니다. Visual Studio 2015에서는 **대화형 옵션 구성**을 선택하여 **옵션** 대화 상자를 열고 **대화형 모드**를 IPython으로 설정한 다음 **확인**을 선택합니다.

1. **대화형 창 열기**를 선택하여 IPython 모드에서 대화형 창을 표시합니다. 대화형 모드를 방금 변경한 경우 창을 다시 설정해야 할 수 있습니다. >>> 프롬프트만 표시되는 경우 Enter 키를 눌러야 할 수도 있습니다.

    ![IPython 모드의 대화형 창](media/ipython-repl-03.png)

1. 다음 코드를 입력합니다.

  ```python
  x = linspace(0, 5, 10)
  y = x ** 2
  plot(x, y, 'r', x, x ** 3, 'g', x, x ** 4, 'b')
  ```

1. 마지막 줄을 입력한 후 원할 경우 인라인 그래프(오른쪽 아래 모서리에서 끌어서 크기를 조정할 수 있음)가 표시되어야 합니다.

    ![대화형 창의 인라인 그래프](media/ipython-repl-04.png)

1. REPL을 입력하는 대신 편집기에서 코드를 작성하여 선택하고 마우스 오른쪽 단추를 클릭한 다음 **Interactive로 보내기** 명령을 선택할 수 있습니다(또는 Ctrl+Enter 누름). 아래 코드를 편집기의 새 파일에 붙여넣고 Ctrl+A로 선택한 다음 대화형 창으로 보내보세요. Visual Studio는 중간 또는 부분 그래프가 제공되지 않도록 코드를 한 단위로 보냅니다. 또한 다른 환경을 선택하여 Python 프로젝트가 열린 경우가 아니라면 Visual Studio는 **Python 환경** 창에서 기본값으로 선택된 환경과 관계없이 대화형 창을 엽니다.

    ```python
    from mpl_toolkits.mplot3d import Axes3D
    import matplotlib.pyplot as plt
    import numpy as np
    fig = plt.figure()
    ax = fig.add_subplot(111, projection='3d')
    for c, z in zip(['r', 'g', 'b', 'y'], [30, 20, 10, 0]):
        xs = np.arange(20)
        ys = np.random.rand(20)
        # You can provide either a single color or an array. To demonstrate this,
        # the first bar of each set is colored cyan.
        cs = [c] * len(xs)
        cs[0] = 'c'
        ax.bar(xs, ys, zs=z, zdir='y', color=cs, alpha=0.8)

    ax.set_xlabel('X')
    ax.set_ylabel('Y')
    ax.set_zlabel('Z')
    plt.show()
    ```

    ![편집기에서 대화형 창으로 코드 보내기](media/ipython-repl-05.png)

1. 대화형 창 외부에서 그래프를 보려면 **디버그 > 디버깅하지 않고 시작** 명령을 사용하는 대신 코드를 실행합니다.

IPython에는 시스템 셸로 이스케이프, 변수 대체, 캡처 출력과 같은 다른 여러 유용한 기능이 있습니다. 자세한 내용은 [IPython 설명서](http://ipython.org/documentation.html)를 참조하세요.

## <a name="related-topics"></a>관련 항목

- 설치하지 않고 쉽게 Jupyter를 사용하려면 노트북을 유지하고 다른 사용자와 공유할 수 있도록 해주는 무료 [Azure Notebook 호스티드 서비스](https://notebooks.azure.com/)를 시도해보세요.

- Azure의 해당 Windows 또는 Linux 가상 컴퓨터에서 Jupyter(이전의 IPython)를 실행할 수도 있습니다. 자세한 내용은 [Azure VM 만들기, Jupyter 설치, Azure에서 Jupyter Notebook 실행](/azure/virtual-machines/virtual-machines-linux-jupyter-notebook)을 참조하세요.
