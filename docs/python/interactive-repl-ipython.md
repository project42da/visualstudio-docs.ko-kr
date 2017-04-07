---
title: "Visual Studio의 IPython REPL | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9bd06b0-2021-4e55-b933-8346476224a8
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
ms.sourcegitcommit: 7d726441c2d6953bd7b50451bec7fff05d5d71b0
ms.openlocfilehash: 9c0c0124ed508eff8621f946a40c0dda520bc05b
ms.lasthandoff: 03/10/2017

---

# <a name="using-python-in-the-interactive-window"></a>대화형 창에서 Python 사용

IPython 모드의 Visual Studio 대화형 창은 사용자에게 친숙한 고급 대화형 개발 환경으로, 대화형 병렬 컴퓨팅 기능을 지원합니다. 이 항목에서는 Visual Studio 대화형 창에서 IPython을 사용하는 방법을 단계별로 설명합니다. 이를 위해서는 IPython 및 필요한 라이브러리를 포함하는 [Anaconda](https://www.continuum.io) 환경이 설치되어 있어야 합니다.

> [!Note]
> Interactive 옵션 양식에서 IPython을 선택할 수는 있지만 IronPython은 IPython을 지원하지 않습니다. [기능 요청](https://github.com/Microsoft/PTVS/issues/84)에 찬성하거나 원하는 경우 기능 요청을 구현할 수 있습니다.

1. Python 설치 디렉터리로 이동하고 IPython Pylab 모드를 시작하여 IPython 패키지가 올바르게 설치되었는지 확인하세요.

  ```bash
  ipython --pylab
  ```

1. 다음을 입력하세요.

  ```python
  x = linspace(0, 5, 10)
  y = x ** 2
  plot(x, y, 'r')
  ```

1. 모든 항목이 제대로 구성되었다면 다음과 같은 출력이 나타납니다.

    ![IPython 구성 출력 ](media/ipython-repl-01.png)

1. Visual Studio를 열고 Python 환경 창(**보기 > 다른 창 > Python 환경**)으로 전환하고 Python 환경을 선택합니다.
1. **pip** 탭을 확인하여 `IPython` 및 `matplotlib`가 나열되어 있는지 확인합니다. 그렇지 않은 경우 여기에서 설치하세요.
1. **개요** 탭을 선택하고 **대화형 옵션 구성**을 선택하고 **대화형 모드**를 IPython으로 설정하고 **확인**을 선택합니다.

    ![대화형 모드를 IPython으로 설정](media/ipython-repl-02.png)

1. **대화형 창 열기**를 선택하여 PyLab을 지원하는 IPython 모드에서 대화형 창을 표시합니다. 대화형 모드를 방금 변경한 경우 창을 다시 설정해야 할 수 있습니다.

    ![IPython 모드의 대화형 창](media/ipython-repl-03.png)

1. 다음 코드를 입력합니다.

  ```python
  x = linspace(0, 5, 10)
  y = x ** 2
  plot(x, y, 'r', x, x ** 3, 'g', x, x ** 4, 'b')
  ```

1. 마지막 줄을 입력한 후 원할 경우 인라인 그래프(오른쪽 아래 모서리에서 끌어서 크기를 조정할 수 있음)가 표시되어야 합니다.

    ![대화형 창의 인라인 그래프](media/ipython-repl-04.png)

1. REPL을 입력하는 대신 편집기에서 코드를 작성하고 선택한 후 마우스 오른쪽 단추를 클릭하고 **Interactive로 보내기** 명령(Ctrl+E, E)을 선택할 수 있습니다. 아래 코드를 편집기에 붙여 넣고 Ctrl+A로 선택한 후 대화형 창으로 보내 보세요. (Visual Studio는 대화형 창으로 코드를 보낼 때 사용자에게 중간 또는 부분 그래프가 표시되지 않도록 한 단위로 보냅니다.)

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
        # the first bar of each set will be colored cyan.
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
    
1. IPython에는 시스템 셸로 이스케이프, 변수 대체, 캡처 출력과 같은 여러 가지 유용한 기능이 있습니다. 자세한 내용은 IPython 참조 가이드를 참조하세요.

    ![시스템 셸로 이스케이프](media/ipython-repl-06.png)

1. 모든 OS에서 모든 브라우저를 캔버스로 사용할 수 있는 "전자 필기장" 모드에서 IPython을 사용할 수도 있습니다. 백 엔드 IPython 엔진은 컴퓨터의 로컬에 있거나 원격 위치에 있을 수 있습니다. Azure에는 [Windows 또는 Linux VM에서 IPython](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-linux-jupyter-notebook)을 실행하기 위한 지원 기능이 있습니다. [Azure 전자 필기장 미리 보기](https://notebooks.azure.com)에서 Azure에 서비스로 제공되는 무료 Jupyter 노트도 확인해 보세요.

    ![IPython 전자 필기장 모드](media/ipython-repl-07.png)

