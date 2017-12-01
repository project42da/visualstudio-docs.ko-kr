---
title: "Equals 및 GetHashCode 메서드 재정의-코드 생성 (C#)를 생성 | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.openlocfilehash: 88ebbeed4af1d0ea79a27ff21f7ae38ec8c252c1
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/29/2017
---
# <a name="generate-equals-and-gethashcode-method-overrides-in-c"></a>Equals를 생성 하 고 C#의 재정의 GetHashCode 메서드 #

**:** 생성할 수 있습니다 **Equals** 및 **GetHashCode** 메서드.

**경우:** 해야 비교 일부 필드에 의해 대신 메모리에 개체 위치에 따라 "value"를 나타내는 형식이 있을 때 이러한 재정의 생성 합니다.

**이유:** 값 형식을 구현 하는 경우 ValueType에 Equals 메서드의 기본 구현을 통해 성능을 향상 시킬된 수를 Equals 메서드 재정의 고려해 야 합니다.

참조 형식이 구현 하는 경우 지점, 문자열, BigNumber, 등의 기본 형식과 같이 프로그램 형식으로 표시 하는 경우 Equals 메서드를 재정의 하는 것이 좋습니다.

해시 테이블에서 제대로 작동 하는 형식을 허용 하도록 GetHashCode 메서드를 재정의 합니다. 에 대 한 자세한 지침은 읽기 [같음 연산자](/dotnet/standard/design-guidelines/equality-operators)합니다.

**방법:**

1. 형식 선언에 커서를 놓습니다.

   ![강조 표시 된 코드](media/overrides_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **생성 Equals(object)** 또는 **생성 Equals 및 GetHashCode** 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 마우스 오른쪽 단추로 클릭 하 고 선택 된 **빠른 작업 및 리팩터링** 메뉴와 선택 **생성 Equals(object)** 또는 **생성 Equals 및 GetHashCode** 미리 보기 창에서 팝업 합니다.
     * 클릭 하 고 ![전구](media/bulb.png) 커서가 있는 경우 텍스트 이미 형식 선언 된 줄에 왼쪽된 여백에 표시 되는 아이콘입니다.

   ![재정의 미리 보기를 생성 합니다.](media/overrides_preview.png)

1. 에 대 한 재정의 메서드를 생성 하려면 멤버 선택:

    ![재정의 대화를 생성 합니다.](media/overrides_dialog.png)

    > [!TIP]
    > 또한 멤버 목록 아래에서 확인란을 사용 하 여이 대화 상자에서 연산자를 생성할 수 있습니다.

1. Equals 및 GetHashCode 재정의 자동 기본 구현으로 생성 됩니다.

   ![메서드 결과 생성 합니다.](media/overrides_result.png)

## <a name="see-also"></a>참고 항목

[코드 생성(C#)](../code-generation-csharp.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)
