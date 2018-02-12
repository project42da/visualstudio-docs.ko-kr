---
title: "Visual Studio에서 Python Code의 성능 측정 | Microsoft Docs"
description: "CPython 기반 인터프리터를 사용할 때 Visual Studio 프로파일러를 통해 Python 코드의 성능을 확인하는 방법입니다."
ms.custom: 
ms.date: 01/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 7f9fb355d35a5c2dcebff6fc1c94c52234e672a0
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="profiling-python-code"></a>Python 코드 프로파일링

CPython 기반 인터프리터를 사용하는 경우 Visual Studio는 Python 응용 프로그램을 프로파일링하도록 지원합니다.

프로파일링은 **분석 > Python 프로파일링 시작** 메뉴 명령을 통해 시작하여 구성 대화 상자를 열 수 있습니다.

![프로파일링 구성 대화 상자](media/profiling-start.png)

**확인**을 선택하면 프로파일러가 실행되고 응용 프로그램에서 소요된 시간을 탐색할 수 있는 성능 보고서를 엽니다.

![프로파일링 성능 보고서](media/profiling-results.png)

데모의 경우 비디오 [Python 프로파일링](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=s6FoC6LWE_1005918567)(Microsoft Virtual Academy, 3m00s)을 참조하세요.

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Profiling-Python-s6FoC6LWE_1005918567]

## <a name="profiling-for-ironpython"></a>IronPython에 대한 프로파일링

IronPython이 CPython 기반 인터프리터가 아니기 때문에 위의 프로파일링 기능이 작동하지 않습니다.

대신, `ipy.exe`을 직접 대상 응용 프로그램으로 시작하여 Visual Studio .NET 프로파일러를 사용하고 시작 스크립트를 시작하기 위해 적절한 인수를 사용합니다. 명령줄에 `-X:Debug`를 포함하면 모든 Python 코드를 디버그하고 프로파일링할 수 있습니다. 이 인수는 IronPython 런타임 및 사용자 코드 모두에 소요된 시간을 포함하는 성능 보고서를 생성합니다. 코드는 변환된 이름을 사용하여 식별됩니다.

또는 IronPython에 고유한 기본 제공 프로파일링의 일부가 포함되지만 현재 이를 위한 시각화 도우미가 마땅하지 않습니다. 제공되는 기능은 [IronPython 프로파일러](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx)(MSDN 블로그)를 참조하세요.