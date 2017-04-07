---
title: "Visual Studio용 Python 도구로 혼합 모드 디버깅을 위한 기호 | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be5fdf2f-b55f-488a-9772-58adfe07a7ab
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
ms.openlocfilehash: 9f7ba91262875344ded1e09277883abff292f359
ms.lasthandoff: 03/07/2017

---

# <a name="installing-debugging-symbols-for-python-interpreters"></a>Python 인터프리터에 대한 디버깅 기호 설치

완전한 디버깅 환경을 제공하기 위해, PTVS(Visual Studio용 Python 도구)의 [혼합 모드 디버거](debugging-mixed-mode.md)는 사용되는 Python 인터프리터 내에서 수많은 내부 데이터 구조를 구문 분석해야 합니다. 이렇게 하려면 인터프리터 자체에 대한 디버그 기호가 필요합니다. 예를 들어 python27.dll에 해당하는 기호 파일은 python27.pdb입니다.

PTVS에서 기호가 필요하다고 감지하면 기호 파일이 포함된 폴더를 가리키거나 다운로드할 것인지 묻는 메시지가 표시됩니다.

![혼합 모드 디버깅 시 기호 프롬프트](media/mixed-mode-debugging-symbols-required.png) 

아래에서 설명한 대로 [공식 배포](#official-distribution) 또는 [Enthought Canopy](#enthought-canopy)에서 기호 파일을 다운로드할 수 있습니다. ActiveState Python과 같은 타사 Python 배포를 사용하는 경우 해당 배포 작성자에게 문의하여 기호를 제공하도록 요청해야 합니다. (그러나 WinPython은 표준 Python 인터프리터를 변경하지 않고 통합하므로 해당 버전 번호에 대한 공식 배포의 기호를 사용합니다.)

인터프리터에 대한 .pdb 파일을 가져왔으면 디버깅 세션이 시작될 때 자동으로 로드되도록 PTVS에서 다음과 같이 이러한 파일을 인식하도록 합니다.

1. **도구 > 옵션** 메뉴 명령을 선택하고 **디버깅 > 기호**로 이동합니다.

![혼합 모드 디버거 기호 옵션](media/mixed-mode-debugging-symbols.png)

1. 도구 모음에서 [추가](위에 표시된 맨 왼쪽 단추인 ! 아이콘의 오른쪽) 단추를 선택하고, .pdb 파일이 있는 폴더로 이동한 다음 **확인**을 선택합니다.


## <a name="official-distribution"></a>공식 배포

Python 3.5 이상에서는 설치 관리자(새로 설치 또는 기존 설치 수정)를 통해 디버그 기호를 포함할 수 있습니다. **사용자 지정 설치**를 선택하고 **다음**을 선택하여 **고급 옵션**으로 이동한 다음 "디버깅 기호 다운로드**및**디버그 버전의 이진 파일 다운로드** 상자를 선택합니다.

![디버그 기호를 포함한 Python 3.x 설치 관리자](media/mixed-mode-debugging-symbols-installer35.png)

Python 3.4.x 및 이전 버전에서는 기호를 다운로드 가능한 .zip 파일로 사용할 수 있습니다. 다운로드한 후에 해당 파일을 폴더로 추출하고 이전 섹션의 지침에 따라 PTVS에 등록합니다.

| Python 버전 | 다운로드 | 
| --- | --- | 
| 3.4.4 | [32비트](https://www.python.org/ftp/python/3.4.4/python-3.4.4-pdb.zip) - [64비트](https://www.python.org/ftp/python/3.4.4/python-3.4.4.amd64-pdb.zip) |
| 3.4.3 | [32비트](https://www.python.org/ftp/python/3.4.3/python-3.4.3-pdb.zip) - [64비트](https://www.python.org/ftp/python/3.4.3/python-3.4.3.amd64-pdb.zip) |
| 3.4.2 | [32비트](https://www.python.org/ftp/python/3.4.2/python-3.4.2-pdb.zip) - [64비트](https://www.python.org/ftp/python/3.4.2/python-3.4.2.amd64-pdb.zip) |
| 3.4.1 | [32비트](https://www.python.org/ftp/python/3.4.1/python-3.4.1-pdb.zip) - [64비트](https://www.python.org/ftp/python/3.4.1/python-3.4.1.amd64-pdb.zip) |
| 3.4.0 | [32비트](https://www.python.org/ftp/python/3.4.0/python-3.4.0-pdb.zip) - [64비트](https://www.python.org/ftp/python/3.4.0/python-3.4.0.amd64-pdb.zip) |
| 3.3.5 | [32비트](http://www.python.org/ftp/python/3.3.5/python-3.3.5-pdb.zip) - [64비트](http://www.python.org/ftp/python/3.3.5/python-3.3.5.amd64-pdb.zip) |
| 3.3.4 | [32비트](http://python.org/ftp/python/3.3.4/python-3.3.4-pdb.zip) - [64비트](http://python.org/ftp/python/3.3.4/python-3.3.4.amd64-pdb.zip) |
| 3.3.3 | [32비트](http://python.org/ftp/python/3.3.3/python-3.3.3-pdb.zip) - [64비트](http://python.org/ftp/python/3.3.3/python-3.3.3.amd64-pdb.zip) |
| 3.3.2 | [32비트](http://python.org/ftp/python/3.3.2/python-3.3.2-pdb.zip) - [64비트](http://python.org/ftp/python/3.3.2/python-3.3.2.amd64-pdb.zip) |
| 3.3.1 | [32비트](http://python.org/ftp/python/3.3.1/python-3.3.1-pdb.zip) - [64비트](http://python.org/ftp/python/3.3.1/python-3.3.1.amd64-pdb.zip) |
| 3.3.0 | [32비트](http://python.org/ftp/python/3.3.0/python-3.3.0-pdb.zip) - [64비트](http://python.org/ftp/python/3.3.0/python-3.3.0.amd64-pdb.zip) |
| 2.7.11 | [32비트](https://www.python.org/ftp/python/2.7.11/python-2.7.11-pdb.zip) - [64비트](https://www.python.org/ftp/python/2.7.11/python-2.7.11.amd64-pdb.zip) |
| 2.7.10 | [32비트](https://www.python.org/ftp/python/2.7.10/python-2.7.10-pdb.zip) - [64비트](https://www.python.org/ftp/python/2.7.10/python-2.7.10.amd64-pdb.zip) |
| 2.7.9 | [32비트](https://www.python.org/ftp/python/2.7.9/python-2.7.9-pdb.zip) - [64비트](https://www.python.org/ftp/python/2.7.9/python-2.7.9.amd64-pdb.zip) |
| 2.7.8 | [32비트](https://www.python.org/ftp/python/2.7.8/python-2.7.8-pdb.zip) - [64비트](https://www.python.org/ftp/python/2.7.8/python-2.7.8.amd64-pdb.zip) |
| 2.7.7 | [32비트](https://www.python.org/ftp/python/2.7.7/python-2.7.7-pdb.zip) - [64비트](https://www.python.org/ftp/python/2.7.7/python-2.7.7.amd64-pdb.zip) |
| 2.7.6 | [32비트](http://python.org/ftp/python/2.7.6/python-2.7.6-pdb.zip) - [64비트](http://python.org/ftp/python/2.7.6/python-2.7.6.amd64-pdb.zip) |
| 2.7.5 | [32비트](http://python.org/ftp/python/2.7.5/python-2.7.5-pdb.zip) - [64비트](http://python.org/ftp/python/2.7.5/python-2.7.5.amd64-pdb.zip) |
| 2.7.4 | [32비트](http://python.org/ftp/python/2.7.4/python-2.7.4-pdb.zip) - [64비트](http://python.org/ftp/python/2.7.4/python-2.7.4.amd64-pdb.zip) |
| 2.7.3 | [32비트](http://python.org/ftp/python/2.7.3/python-2.7.3-pdb.zip) - [64비트](http://python.org/ftp/python/2.7.3/python-2.7.3.amd64-pdb.zip) |
| 2.7.2 | [32비트](http://python.org/ftp/python/2.7.2/python-2.7.2-pdb.zip) - [64비트](http://python.org/ftp/python/2.7.2/python-2.7.2.amd64-pdb.zip) |
| 2.7.1 | [32비트](http://python.org/ftp/python/2.7.1/python-2.7.1-pdb.zip) - [64비트](http://python.org/ftp/python/2.7.1/python-2.7.1.amd64-pdb.zip) |


## <a name="enthought-canopy"></a>Enthought Canopy

Enthought Canopy는 버전 1.2 버전에서 시작하는 이진 파일에 대한 기호를 제공합니다. 배포와 함께 자동으로 설치되지만, 앞에서 설명한 대로 여전히 기호가 포함된 폴더를 기호 경로에 수동으로 추가해야 합니다. 일반적인 사용자별 Canopy 설치의 경우 기호는 64비트 버전의 경우 `%UserProfile%\AppData\Local\Enthought\Canopy\User\Scripts`에, 32비트 버전의 경우 `%UserProfile%\AppData\Local\Enthought\Canopy32\User\Scripts`에 있습니다.

Enthought Canopy 1.1 및 이전 버전과 EPD(Enthought Python Distribution)는 인터프리터 기호를 제공하지 않으므로 혼합 모드 디버깅과 호환되지 않습니다.
