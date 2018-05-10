---
title: -DebugExe(devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 07dfcbb6064d0f1043c0621534b953a5f5c63e82
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="debugexe-devenvexe"></a>/DebugExe(devenv.exe)
디버깅하도록 지정된 실행 파일을 엽니다.

## <a name="syntax"></a>구문

```cmd
Devenv /debugexe ExecutableFile
```

## <a name="arguments"></a>인수
 `ExecutableFile`

 필수. .exe 파일의 경로 및 파일 이름.

 .exe 파일이 없거나 존재하지 않는 경우 경고 또는 오류가 표시되지 않고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]이(가) 정상적으로 시작됩니다.

## <a name="remarks"></a>설명
 `ExecutableFile` 매개 변수 다음에 나오는 모든 문자열은 해당 파일에 인수로 전달됩니다.

## <a name="example"></a>예
 다음 예제는 디버깅을 위해 `MyApplication.exe` 파일을 엽니다.

```cmd
Devenv.exe /debugexe MyApplication.exe
```

## <a name="see-also"></a>참고 항목

- [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)