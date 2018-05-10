---
title: 기수 설정 명령
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.setradix
helpviewer_keywords:
- Set Radix command
- Debug.SetRadix command
ms.assetid: 6ffd1554-7530-4da4-b5f5-e276a5034f3b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c18d825ae61dd80ab7b72e1e14c7dc3412582317
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="set-radix-command"></a>기수 설정 명령
정수 값을 표시하는 데 사용할 숫자 기준을 설정하거나 반환합니다.

## <a name="syntax"></a>구문

```cmd
Debug.SetRadix [10 | 16 | hex | dec]
```

## <a name="arguments"></a>인수
 `10`, `16`, `hex` 또는 `dec`

 선택 사항입니다. 10진수(10 또는 dec) 또는 16진수(16 또는 hex)를 나타냅니다. 인수를 생략하면 현재 기수 값이 반환됩니다.

## <a name="example"></a>예
 이 예제에서는 16진수 형식의 정수 값을 표시하도록 환경을 설정합니다.

```cmd
>Debug.SetRadix hex
```

## <a name="see-also"></a>참고 항목

- [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)
- [명령 창](../../ide/reference/command-window.md)
- [찾기/명령 상자](../../ide/find-command-box.md)
- [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)