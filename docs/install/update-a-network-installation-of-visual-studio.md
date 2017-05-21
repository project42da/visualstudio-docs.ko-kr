---
title: "Visual Studio의 네트워크 기반 설치 업데이트 | Microsoft Docs"
description: '{{PLACEHOLDER}}'
ms.date: 05/05/2017
ms.reviewer: tims
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 1AF69C0E-0AC9-451B-845D-AE4EDBCEA65C
author: timsneath
ms.author: tims
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 85576806818a6ed289c2f660f87b5c419016c600
ms.openlocfilehash: 75c65d75ab751058ac435d62f253ead149ccfe42
ms.contentlocale: ko-kr
ms.lasthandoff: 05/09/2017

---
# <a name="update-a-network-based-installation-of-visual-studio"></a>Visual Studio의 네트워크 기반 설치 업데이트

최신 제품 업데이트를 사용하여 Visual Studio의 네트워크 설치 레이아웃을 업데이트할 수 있으므로, 해당 레이아웃을 Visual Studio의 최신 업데이트에 대한 설치 지점으로 사용하거나 이미 클라이언트 워크스테이션에 배포된 설치를 유지 관리하는 데 사용할 수 있습니다.

## <a name="how-to-update-a-network-layout"></a>네트워크 레이아웃을 업데이트하는 방법
최신 업데이트를 포함하도록 네트워크 설치 공유를 새로 고치려면 업데이트된 패키지를 점진적으로 다운로드하기 위해 레이아웃을 처음 만들 때 실행한 것과 같은 `--layout` 명령을 실행합니다.

네트워크 레이아웃을 처음 만들 때 부분 레이아웃을 선택했다면 네트워크 설치 레이아웃을 처음 만들 때 사용한 것과 같은 명령줄 매개 변수(같은 워크로드 및 언어)를 사용해야 합니다. 다른 옵션을 선택하면 두 번째 `--layout` 명령이 두 번째로 지정되지 않은 패키지를 업데이트하지 않습니다.

레이아웃을 파일 공유에서 호스트하려면 레이아웃의 전용 복사본을 업데이트하고(예: `c:\vs2017offline`) 업데이트된 콘텐츠가 모두 다운로드된 후 해당 복사본을 파일 공유로 복사합니다(예: `\\server\products\VS2017`).  이 작업을 하지 않으면 레이아웃이 업데이트되는 동안 설치 프로그램을 실행하는 사용자가 레이아웃에서 일부 콘텐츠를 가져오지 못할 수 있습니다. 이는 레이아웃이 완전히 업데이트되지 않았기 때문입니다.

## <a name="how-to-deploy-an-update-to-client-machines"></a>업데이트를 클라이언트 컴퓨터에 배포하는 방법
네트워크 환경 구성 방법에 따라 엔터프라이즈 관리자가 업데이트를 배포하거나 클라이언트 컴퓨터에서 업데이트를 시작할 수 있습니다. 

- 사용자는 오프라인 설치 폴더에서 설치된 Visual Studio 인스턴스를 업데이트할 수 있습니다.
  - Visual Studio 설치 관리자를 실행합니다.
  - 그다음에 **업데이트**를 클릭합니다.

- 관리자는 다음 두 가지 명령을 각각 사용하여 사용자 조작 없이 Visual Studio의 클라이언트 배포를 업데이트할 수 있습니다.
  - 먼저 Visual Studio 설치 관리자를 업데이트합니다. <br>```vs_enterprise.exe --quiet --update```
  - 그다음에 Visual Studio 응용 프로그램 자체를 업데이트합니다. <br>```vs_enterprise.exe update --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" --quiet --wait --norestart```

> [!NOTE]
> [vswhere.exe 명령](tools-for-managing-visual-studio-instances.md)을 사용하여 클라이언트 컴퓨터에서 기존 Visual Studio 인스턴스의 설치 경로를 확인합니다.

> [!TIP]
> 사용자에게 업데이트 알림이 제공되는 시점을 제어하는 방법에 대한 자세한 내용은 [네트워크 기반 Visual Studio 배포에 대한 업데이트 제어](controlling-updates-to-visual-studio-deployments.md)를 참조하세요.


## <a name="see-also"></a>참고 항목
* [Visual Studio 설치](install-visual-studio.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 인스턴스 검색 및 관리 도구](tools-for-managing-visual-studio-instances.md)
* [네트워크 기반 Visual Studio 배포에 대한 업데이트 제어](controlling-updates-to-visual-studio-deployments.md)

