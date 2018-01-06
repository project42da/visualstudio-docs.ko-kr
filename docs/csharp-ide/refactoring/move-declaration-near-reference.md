---
title: "리팩터링 (C#)-참조 근처로 선언 이동 | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: d79d55ae-f6bb-4902-8db2-e7fe01bdb0bf
author: kuhlenh
ms.author: kaseyu
manager: ghogen
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: c274fd758fdae468bee884fcf1686abc16ec1d7e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="move-declaration-near-reference-in-c"></a>C# 참조 근처로 선언 이동 #
**:** 변수 선언에 곧 제공 될 용도를 이동할 수 있습니다.

**경우:** 하면 더 좁은 범위에 저장할 수 있는 변수 선언 해야 합니다.

**이유:** 하지만 정보 숨기기 이나 가독성 문제가 발생할 수 있는 대로 발생할 수 있습니다. 가독성을 높이기 위해 리팩터링할 수 있는 기회입니다.

**방법:**

1. 변수 선언에 커서를 놓습니다.

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **참조 근처로 선언 이동** 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭, 선택는 **빠른 작업 및 리팩터링** 메뉴와 선택 **참조 근처로 선언 이동** 미리 보기 창 팝업에서 합니다.

1. 키를 눌러를 변경 하 여 만족 했으면 **Enter** 또는 메뉴의 수정을 클릭 하 고 변경 내용이 커밋됩니다.

예제:
```csharp
// Before
int x;
if (condition)
{
    x = 1;
    Console.WriteLine(x);
}

// Move declaration near reference

// After
if (condition)
{
    int x = 1;
    Console.WriteLine(x);
}
```

## <a name="see-also"></a>참고 항목  
[리팩터링(C#)](../refactoring-csharp.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)