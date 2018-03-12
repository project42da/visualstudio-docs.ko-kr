---
title: -UseEnv(devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4c48e9f22322cd5ebebeff0d987c32d369f98d03
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2018
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