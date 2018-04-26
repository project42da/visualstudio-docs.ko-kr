---
title: 현재 스레드 설정 명령
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.setcurrentthread
helpviewer_keywords:
- Set Current Thread command
- Debug.SetCurrentThread command
ms.assetid: 9917ed1d-6c30-4d94-b2f0-69acce74f1b2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b02dbc1d22716483acdfd5378316d6297f6b031f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="set-current-thread-command"></a>현재 스레드 설정 명령
지정한 스레드를 현재 스레드로 설정합니다.

## <a name="syntax"></a>구문

```
Debug.SetCurrentThread index
```

## <a name="arguments"></a>인수
 `index`

 필수. 해당 인덱스로 스레드를 선택합니다.

## <a name="example"></a>예

```
>Debug.SetCurrentThread 1
```

## <a name="see-also"></a>참고 항목

- [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)
- [명령 창](../../ide/reference/command-window.md)
- [찾기/명령 상자](../../ide/find-command-box.md)
- [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)