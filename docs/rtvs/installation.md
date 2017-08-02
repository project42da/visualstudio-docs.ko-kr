---
title: "Visual Studio용 R 도구 설치 | Microsoft Docs"
ms.custom: 
ms.date: 4/28/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ff60292-1b88-4ee9-b2b2-edd957f1a519
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 90b2481b0ec4f9387fe3a2c0b733a103e8c03845
ms.openlocfilehash: bc0b1112fe6f3acf2605101a863d831f41bb5f6d
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-install-r-tools-for-visual-studio"></a>Visual Studio용 R 도구를 설치하는 방법

항목 내용:

- [지원되는 Visual Studio 버전](#supported-versions-of-visual-studio)
- [Visual Studio 2017에서 RTVS 설치](#installing-rtvs-in-visual-studio-2017)
- [Visual Studio 2015에서 RTVS 설치](#installing-rtvs-in-visual-studio-2015)
- [오프라인 설치](#offline-installation-of-visual-studio-and-rtvs)

> [!Note]
> R 도구를 설치한 후 [옵션](options.md#data-scientist-layout) 항목의 설명대로 최적화된 데이터 과학자 레이아웃을 사용하도록 Visual Studio를 구성해야 할 수 있습니다.

## <a name="supported-versions-of-visual-studio"></a>지원되는 Visual Studio 버전

RTVS(Visual Studio용 R 도구)는 [Visual Studio 2015 업데이트 3 이상](http://go.microsoft.com/fwlink/?LinkId=691129) 및 [Visual Studio 2017](https://www.visualstudio.com/downloads/)의 Community, Professional 및 Enterprise Edition에서 지원됩니다. 

Visual Studio Test Professional 및 SQL Server Management Studio와 같은 다른 제품과 함께 제공되는 Visual Studio Shell만 있는 경우에는 RTVS가 설치되지 않습니다. 이는 Visual Studio Shell에는 RTVS에 필요한 구성 요소가 없기 때문입니다.


## <a name="installing-rtvs-in-visual-studio-2017"></a>Visual Studio 2017에서 RTVS 설치

> [!Important]
> Windows 7의 Visual Studio 2017에서 RTVS를 설치하는 기능은 [GitHub issue #3561](https://github.com/Microsoft/RTVS/issues/3561)(GitHub 문제 #3561)의 설명대로 현재 차단되어 있습니다. 이 문제는 Visual Studio 2017에 대한 15.3 업데이트에서 해결될 예정입니다.

1. Visual Studio 설치 관리자를 실행합니다.
2. **데이터 과학 및 분석 응용 프로그램** 워크로드를 선택합니다.

    ![VS2017의 데이터 과학 및 분석 응용 프로그램 워크로드](~/rtvs/media/installation-data-science-workload.png)

3. 동일한 워크로드 이름 아래에서 오른쪽의 추가 옵션을 설정합니다. 기본적으로 이 워크로드에는 F# 및 Python 지원이 포함됩니다. R의 경우 최소한 **R 언어 지원**, **R 개발에 대한 런타임 지원** 및 **Microsoft R Client**를 선택해야 합니다.

RTVS는 `%ProgramFiles(x86)%\Microsoft Visual Studio\<version>\<edition>Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio`에 설치됩니다. 여기서 `<version>`은 일반적으로 `2017`이고 `<edition>`은 `Community`, `Professional` 또는 `Enterprise`입니다.

## <a name="installing-rtvs-in-visual-studio-2015"></a>Visual Studio 2015에서 RTVS 설치

Visual Studio 2015에서는 R 인터프리터 및 R 도구를 개별적으로 설치해야 합니다.

### <a name="install-an-r-interpreter"></a>R 인터프리터 설치

RTVS에는 다음 소스 중 하나 이상에서 제공되는 R 버전 3.2.1 이상의 64비트 설치가 필요합니다.

* [Microsoft R Open](https://mran.microsoft.com/download/)
* [Microsoft R Client](https://msdn.microsoft.com/microsoft-r/r-client-get-started)
* [CRAN R](https://cran.r-project.org/bin/windows/base/)

Microsoft R Open 및 CRAN R은 둘 다 여러 개의 동시 버전을 허용합니다. 하지만 Microsoft R Client는 하나의 버전만 지원하고 항상 설치된 최신 버전을 사용합니다.

### <a name="install-the-r-tools"></a>R 도구 설치

[https://aka.ms/rtvs-current](https://aka.ms/rtvs-current)에서 최신 RTVS를 다운로드합니다. RTVS는 적합한 Visual Studio 버전을 확인하고 해당 버전이 아직 없는 경우 R 인터프리터를 설치하도록 지원합니다.

RTVS는 `%ProgramFiles(x86)%\Microsoft Visual Studio 14\Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio`에 설치됩니다.

## <a name="offline-installation-of-visual-studio-and-rtvs"></a>Visual Studio 및 RTVS의 오프라인 설치

오프라인 설치는 인터넷에 연결되지 않은 컴퓨터에 적합합니다.

1. 지침에 따라 다음과 같이 사용 중인 Visual Studio 버전용 오프라인 설치 관리자를 만듭니다. 

    - [Visual Studio 2017](../install/create-an-offline-installation-of-visual-studio.md)
    - [Visual Studio 2015](https://msdn.microsoft.com/library/mt706497.aspx)

1. 오프라인 설치 관리자에서 Visual Studio를 설치합니다.
1. [RTVS를 다운로드](https://aka.ms/rtvs-current)하고 일반적인 방식으로 설치합니다.

## <a name="see-also"></a>참고 항목

- [R 시작](getting-started-with-r.md)
- [R 도구 샘플 프로젝트](getting-started-samples.md)
- [도움말 보기](getting-started-help.md)
- [옵션 설정](options.md)

