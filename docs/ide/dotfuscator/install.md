---
title: "Dotfuscator CE(Community Edition) 설치 | Microsoft 문서"
ms.date: 2017-06-22
ms.prod: visual-studio-dev15
ms.devlang: dotnet
ms.technology:
- dotfuscator
ms.topic: article
keywords: "Dotfuscator, Dotfuscator CE, PreEmptive, PreEmptive Solutions, PreEmptive Protection, 보호, community edition, obfuscation, .NET, 무료, Visual Studio 2017, 설치"
helpviewer_keywords:
- PreEmptive Protection - Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
- Dotfuscator installer
- Dotfuscator setup
- install Dotfuscator
- installing Dotfuscator
- set up Dotfuscator
description: "Visual Studio 2017에 포함된 무료 Dotfuscator Community Edition을 설치하는 방법을 알아봅니다."
ms.assetid: f2146651-e24a-4e24-ade8-8ddee8ff4e43
author: Joe-Sewell-PreEmptive
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
ms.sourcegitcommit: 8ce85525f6af336682f6f8547c2f6c13dde73c8c
ms.openlocfilehash: fb5356632ecf8183945b1d50ba940ed05abcf96f
ms.contentlocale: ko-kr
ms.lasthandoff: 06/23/2017

---

# <a name="install-dotfuscator-community-edition-ce"></a>Dotfuscator CE(Community Edition) 설치

Visual Studio 2017에서는 새로운 영향 최소화 설치 환경을 소개합니다.
따라서 Dotfuscator CE(Dotfuscator Community Edition)는 기본적으로 설치되지 않습니다.
그러나 이미 Visual Studio를 설치한 경우에도 Dotfuscator CE를 쉽게 설치할 수 있습니다.

> [!NOTE]
> Visual Studio 릴리스와 함께 제공된 Dotfuscator CE 버전 외에도 PreEmptive Solutions에서는 웹 사이트에서 정기적으로 업데이트된 버전을 제공합니다.
> Visual Studio에서 설치하는 대신 직접 **최신 버전**을 다운로드하려면 **[여기를 클릭하여 Dotfuscator 다운로드 페이지로 이동][download]**합니다.

## <a name="within-visual-studio"></a>Visual Studio 내에서

Visual Studio IDE에서 Dotfuscator CE를 설치할 수 있습니다.

1. **빠른 실행**(Ctrl+Q) 검색 창에서 `dotfuscator`를 입력합니다. <br/> <br/> ![](~/ide/dotfuscator/media/install_from_vs_12.png) <br/> <br/>
2. 표시된 빠른 실행 결과 중 *설치* 제목 아래에서 **PreEmptive Protection - Dotfuscator(개별 구성 요소)**를 선택합니다.
  * *메뉴* 제목 아래에서 **도구 - PreEmptive Protection - Dotfuscator**를 확인하면 Dotfuscator CE가 이미 설치되어 있습니다. 사용법에 대한 자세한 내용은 [전체 Dotfuscator CE 사용자 가이드의 시작 페이지][get-started]를 참조하세요.
3. [Visual Studio 설치 관리자] 창이 시작되고 Dotfuscator CE를 설치하도록 미리 구성되어 있습니다.
  * 계속하려면 관리자 자격 증명을 제공해야 할 수 있습니다.
4. Visual Studio IDE의 모든 인스턴스를 닫습니다. <br/> <br/> ![](~/ide/dotfuscator/media/install_from_vs_345.png) <br/> <br/>
5. [Visual Studio 설치 관리자] 창에서 *설치*를 클릭합니다.

설치가 완료되면 Dotfuscator CE 사용을 시작할 수 있습니다. 자세한 내용은 [전체 Dotfuscator CE 사용자 가이드의 시작 페이지][get-started]를 참조하세요.

## <a name="during-visual-studio-installation"></a>Visual Studio를 설치하는 동안

Visual Studio 2017을 아직 설치하지 않은 경우 [Visual Studio 웹 사이트][2017-install]에서 설치 관리자를 다운로드할 수 있습니다.
설치 관리자를 실행하면 선택된 Visual Studio 버전에 대한 설치 옵션이 표시됩니다.

![](~/ide/dotfuscator/media/install_ui.png)

Dotfuscator CE를 Visual Studio 2017의 개별 구성 요소로 설치할 수 있습니다.

1. **개별 구성 요소** 탭을 선택합니다.
2. *코드 도구*에서 *PreEmptive Protection - Dotfuscator* 항목을 선택합니다.<br/> <br/> ![](~/ide/dotfuscator/media/install_individually_12.png) <br/> <br/>
3. *요약* 패널에서 *개별 구성 요소* 섹션 아래에 *PreEmptive Protection - Dotfuscator*가 표시됩니다. <br/> <br/> ![](~/ide/dotfuscator/media/install_individually_3.png) <br/> <br/>
4. 환경에 맞게 추가 설치 설정을 구성합니다.
5. Visual Studio를 설치할 준비가 되면 *설치* 단추를 클릭합니다.

설치가 완료되면 Dotfuscator CE 사용을 시작할 수 있습니다. 자세한 내용은 [전체 Dotfuscator CE 사용자 가이드의 시작 페이지][get-started]를 참조하세요.

## <a name="see-also"></a>참고 항목

[전체 Dotfuscator CE 사용자 가이드의 이 항목][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[2017-install]: https://www.visualstudio.com/downloads/#vs-2017
[get-started]: https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html

[download]: https://www.preemptive.com/products/dotfuscator/downloads

[full]: https://www.preemptive.com/dotfuscator/ce/docs/help/intro_install.html

