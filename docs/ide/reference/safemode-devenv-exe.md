---
title: -SafeMode(devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2c678d7304c879cf42c24de9d83704971043676
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="safemode-devenvexe"></a>/SafeMode(devenv.exe)
안전 모드에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]을(를) 시작하고 기본 환경 및 서비스만 로드합니다.

## <a name="syntax"></a>구문

```cmd
devenv /SafeMode
```

## <a name="remarks"></a>설명
 이 스위치는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]이(가) 시작될 때 모든 타사 VSPackages의 로드를 차단하므로 안정적으로 실행되도록 합니다.

## <a name="description"></a>설명
 다음 예제에서는 안전 모드에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]을(를) 시작합니다.

## <a name="code"></a>코드

```cmd
Devenv.exe /SafeMode
```

## <a name="see-also"></a>참고 항목

- [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)