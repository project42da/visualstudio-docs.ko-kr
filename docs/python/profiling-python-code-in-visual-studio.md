---
title: "Visual Studio에서 Python Code의 성능 측정 | Microsoft Docs"
description: "CPython 기반 인터프리터를 사용할 때 Visual Studio 프로파일러를 통해 Python 코드의 성능을 확인하는 방법입니다."
ms.custom: 
ms.date: 01/09/2018
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
ms.openlocfilehash: 0faae917aba237a85c6a01743d89cf66adf06296
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2018
---
# <a name="profiling-python-code"></a>Python 코드 프로파일링

CPython 기반 인터프리터를 사용하는 경우 Python 응용 프로그램을 프로파일링할 수 있습니다. (서로 다른 버전의 Visual Studio에 대해 이 기능을 사용할 수 있는지 여부는 [기능 매트릭스 - 프로파일링](overview-of-python-tools-for-visual-studio.md#matrix-profiling)을 참조하십시오.)

프로파일링은 **분석 > Python 프로파일링 시작** 메뉴 명령을 통해 시작하여 구성 대화 상자를 열 수 있습니다.

![프로파일링 구성 대화 상자](media/profiling-start.png)

**확인**을 선택하면 프로파일러가 실행되고 응용 프로그램에서 소요된 시간을 탐색할 수 있는 성능 보고서를 엽니다.

![프로파일링 성능 보고서](media/profiling-results.png)

|   |   |
|---|---|
| ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기") | Python 프로파일링 데모 [비디오(Microsoft Virtual Academy)를 시청](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Profiling-Python-s6FoC6LWE_1005918567)하세요(3분 00초).|

## <a name="profiling-for-ironpython"></a>IronPython에 대한 프로파일링

IronPython이 CPython 기반 인터프리터가 아니기 때문에 위의 프로파일링 기능이 작동하지 않습니다.

대신, `ipy.exe`을 직접 대상 응용 프로그램으로 시작하여 Visual Studio .NET 프로파일러를 사용하고 시작 스크립트를 시작하기 위해 적절한 인수를 사용합니다. 명령줄에 `-X:Debug`를 포함하면 모든 Python 코드를 디버그하고 프로파일링할 수 있습니다. 이 인수는 IronPython 런타임 및 사용자 코드 모두에 소요된 시간을 포함하는 성능 보고서를 생성합니다. 코드는 변환된 이름을 사용하여 식별됩니다.

또는 IronPython에 고유한 기본 제공 프로파일링의 일부가 포함되지만 현재 이를 위한 시각화 도우미가 마땅하지 않습니다. 제공되는 기능은 [IronPython 프로파일러](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx)(MSDN 블로그)를 참조하세요.