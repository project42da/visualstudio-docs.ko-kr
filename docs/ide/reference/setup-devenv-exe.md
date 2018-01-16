---
title: "devenv.exe 설정 스위치 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 93f03de74540d130d66ce123b355691e0828b93e
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="setup-devenvexe"></a>/Setup(devenv.exe)

/Setup 스위치는 Visual Studio가 모든 사용 가능한 VSPackages에서 메뉴, 도구 모음 및 명령 그룹을 설명하는 리소스 메타데이터를 병합하도록 합니다.

## <a name="syntax"></a>구문

```
devenv /setup
```

## <a name="remarks"></a>설명

이 스위치는 인수가 필요 없습니다. `devenv /setup` 명령은 일반적으로 설치 프로세스의 마지막 단계로 표시됩니다. `/setup` 스위치를 사용해도 Visual Studio가 시작되지는 않습니다.

`devenv` 및 [devenv](../../ide/reference/setup-devenv-exe.md) 스위치를 사용하려면 관리자 권한으로 [devenv](../../ide/reference/installvstemplates-devenv-exe.md) 를 실행해야 합니다.

## <a name="example"></a>예

이 예는 VSPackages를 포함하는 Visual Studio 버전 설치의 마지막 단계를 보여 줍니다.

```
devenv /setup
```

## <a name="see-also"></a>참고 항목

[Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)