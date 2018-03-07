---
title: "devenv.exe InstallVSTemplates 스위치 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /InstallVSTemplates switch
- /InstallVSTemplates Devenv switch
- InstallVSTemplates switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 529979caa801ace8dd649cf1614f2eeb27ca070b
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="installvstemplates-devenvexe"></a>/InstallVSTemplates(devenv.exe)

/InstallVSTemplates 스위치는 *\<Visual Studio 설치 경로>*\Common7\IDE\ProjectTemplates\ 또는 *\<Visual Studio 설치 경로>*\Common7\IDE\ItemTemplates\에 있는 프로젝트 또는 항목 템플릿을 등록하여 **새 프로젝트** 및 **새 항목 추가** 대화 상자를 통해 액세스할 수 있도록 합니다.

> [!WARNING]
> 이 스위치는 Visual Studio 파트너 개발에서만 지원됩니다. [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) 및 [/InstallVSTemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) 스위치를 사용하려면 관리자 권한으로 devenv를 실행해야 합니다. 자세한 내용은 [사용자 권한](../../ide/user-permissions-and-visual-studio.md)을 참조하세요.

## <a name="syntax"></a>구문

```
devenv.exe /InstallVSTemplates
```

## <a name="see-also"></a>참고 항목

[Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)