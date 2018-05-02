---
title: 문 실행 명령
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0c2ec882bb2fdc9d0f3b74a0552c85a7b286617c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="evaluate-statement-command"></a>문 실행 명령
지정된 문을 평가 및 표시합니다.

## <a name="syntax"></a>구문

```
Debug.EvaluateStatement text
```

## <a name="arguments"></a>인수
 `text` 필수입니다. 평가할 문입니다.

## <a name="remarks"></a>설명
 **EvaluateStatement** 명령을 입력하는 데 사용되는 창에서는 같음 기호(=)를 비교 연산자 또는 대입 연산자로 해석할지 결정합니다.

 **명령** 창에서 같음 기호(=)는 비교 연산자로 해석됩니다. 따라서 예를 들면 `a` 및 `b` 변수 값이 다른 경우

```
>Debug.EvaluateStatement(a=b)
```

 명령은 `false` 값을 반환합니다.

 이와 달리 **직접 실행** 창에서는 같음 기호(=)가 대입 연산자로 해석됩니다. 따라서 예를 들면

```
>Debug.EvaluateStatement(a=b)
```

 명령은 `a` 변수에 `b` 변수의 값을 할당합니다.

## <a name="example"></a>예

```
>Debug.EvaluateStatement(a+b)
```

## <a name="see-also"></a>참고 항목

- [인쇄 명령](../../ide/reference/print-command.md)
- [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)
- [명령 창](../../ide/reference/command-window.md)
- [찾기/명령 상자](../../ide/find-command-box.md)
- [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)