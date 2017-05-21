---
title: "패키지 캐시를 사용하지 않도록 설정 또는 이동 | Microsoft Docs"
description: "Visual Studio 배포에 대해 패키지 캐시를 사용하지 않도록 설정하거나, 사용하도록 설정하거나, 이동합니다."
ms.date: 04/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cache
- nocache
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 2429993A-3F0E-41C5-9562-FEA6AE994440
author: heaths
ms.author: heaths
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
ms.openlocfilehash: e07f1c04d9695e092db7aa29e641ce9bd36250f9
ms.contentlocale: ko-kr
ms.lasthandoff: 05/09/2017

---
# <a name="disable-or-move-the-package-cache"></a>패키지 캐시를 사용하지 않도록 설정 또는 이동

패키지 캐시는 인터넷 연결 없이 Visual Studio 또는 기타 관련 제품을 복구해야 할 경우 설치된 패키지의 소스를 제공합니다. 일부 드라이브 또는 시스템 설정에서는 일부 패키지를 유지하지 않으려고 할 수 있습니다.
설치 관리자에서는 필요한 경우 패키지를 다운로드하므로 디스크 공간을 절약하거나 복구하려면 패키지 캐시를 사용하지 않도록 설정하거나 이동하면 됩니다.

## <a name="disable-the-package-cache"></a>패키지 캐시를 사용하지 않도록 설정

새로운 설치 관리자를 사용하여 Visual Studio 또는 기타 제품을 설치, 수정 또는 복구하기 전에 설치 관리자에 대한 `--nocache` 스위치를 사용하여 설치 관리자를 시작할 수 있습니다.

```
"%ProgramFiles(x86)%\Microsoft Visual Studio\Installer\vs_installer.exe" --nocache
```

제품에서 작업을 수행하면 해당 제품에 대한 모든 기존 패키지가 제거되고 패키지가 설치된 후 해당 패키지가 저장되지 않습니다. Visual Studio를 수정하거나 복구할 때 패키지가 필요하면 패키지가 자동으로 다운로드되고 해당 패키지는 설치된 후 제거됩니다.

캐시를 다시 사용하도록 설정하려면 `--cache`를 전달합니다. 필요한 패키지만 캐시되므로 모든 패키지를 복원해야 할 경우에는 네트워크 연결을 끊기 전에 Visual Studio를 복구해야 합니다.

```
"%ProgramFiles(x86)%\Microsoft Visual Studio\Installer\vs_installer.exe" repair --passive --norestart --cache
```

Visual Studio를 설치, 수정 또는 복구하기 전에 캐시가 사용되지 않도록 `KeepDownloadedPayloads` [레지스트리 정책](set-defaults-for-enterprise-deployments.md)을 설정할 수도 있습니다.

## <a name="move-the-package-cache"></a>패키지 캐시 이동

일반적인 시스템 구성은 소스 코드, 프로그램 이진 파일 등의 개발 요구 사항에 맞게 더 큰 하드 디스크가 포함된 SSD에 Windows를 설치하는 것입니다. 오프라인에서 작업하려는 경우 패키지 캐시를 이동할 수 있습니다.

현재는 Visual Studio를 설치, 수정 또는 복구하기 전에 `CachePath` [레지스트리 정책](set-defaults-for-enterprise-deployments.md)을 설정하는 경우에만 이 작업을 할 수 있습니다.

## <a name="see-also"></a>참고 항목

 * [Visual Studio 설치](install-visual-studio.md)
 * [엔터프라이즈 배포에 대한 기본값 설정](set-defaults-for-enterprise-deployments.md)
 * [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
 * [Visual Studio의 문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md)

