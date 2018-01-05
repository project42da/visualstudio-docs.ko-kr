---
title: "연결할 수 없는 코드-리팩터링 (C#)를 제거 | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
author: kuhlenh
ms.author: kaseyu
manager: ghogen
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: e57db74ea431d9090df1dc34fd3cff3cf03dd475
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="remove-unreachable-code-in-c"></a>C#에서 연결할 수 없는 코드를 제거 합니다. #
**:** 실행 되지 않는 코드를 제거 합니다.

**경우:** 프로그램에 해당 코드 조각을 불필요 한 만드는 코드 조각 사용 하는 경로가 없습니다.

**이유:** 는 불필요 하는 코드를 제거 하 여 가독성 및 유지 관리 용이성을 개선 하 고 실행할 수 없습니다.

**방법:**

1. 연결할 수 없는 페이드 아웃 코드에 아무 곳 이나 커서를 배치 합니다.

![페이드 접근할 수 없는 코드](media/unreachablecode_faded.png)  

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **연결할 수 없는 코드를 제거** 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭을 선택는 **빠른 작업 및 리팩터링** 메뉴와 선택 **연결할 수 없는 코드를 제거** 미리 보기 창 팝업에서 합니다.

1. 키를 눌러를 변경 하 여 만족 했으면 **Enter** 또는 메뉴의 수정을 클릭 하 고 변경 내용이 커밋됩니다.

예제:
```csharp
// Before
private void Method()
{
    throw new Exception(nameof(Method));
    Console.WriteLine($"Exception for method {nameof(Method)}");
}

// Remove unreachable code

// After
private void Method()
{
    throw new Exception(nameof(Method));
}
```

## <a name="see-also"></a>참고 항목  
[리팩터링(C#)](../refactoring-csharp.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)