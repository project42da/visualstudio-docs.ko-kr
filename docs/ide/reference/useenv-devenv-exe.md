---
title: -UseEnv(devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VC.Project.UseEnvVars.ExcludePath
- VC.Project.UseEnvVars.LibraryPath
- VC.Project.UseEnvVars.SourcePath
- VC.Project.UseEnvVars.Include
- VC.Project.UseEnvVars.Path
- VC.Project.UseEnvVars.ReferencePath
helpviewer_keywords:
- UseEnv switch
- /UseEnv Devenv switch
- Devenv, /UseEnv
ms.assetid: 2dd14603-a61b-42d2-ba31-427a0ee8a799
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5fd76e44b2e503bd7b444e83bb9a64abceeaa561
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="useenv-devenvexe"></a>/UseEnv(devenv.exe)

Visual Studio를 시작하고 환경 변수를 **VC++ 디렉터리** 대화 상자에 로드합니다.

> [!NOTE]
> **C++ 워크로드로 데스크톱 개발**을 사용하여 이 스위치를 설치합니다.

## <a name="syntax"></a>구문

```shell
Devenv /useenv
```

## <a name="example"></a>예

다음 예제에서는 Visual Studio를 시작하고 환경 변수를 **VC++ 디렉터리** 대화 상자에 로드합니다.

```shell
Devenv.exe /useenv
```

## <a name="see-also"></a>참고 항목

* [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)