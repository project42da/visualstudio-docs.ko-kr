---
title: "리팩터링 (C#)-속성에 Get 메서드가 변환 | Microsoft Docs"
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
f1_keywords: vs.csharp.refactoring.convertmethodtoproperty
dev_langs: csharp
ms.openlocfilehash: d034b8835caf0a5e56a9ef32599cf9197f1e3e16
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/29/2017
---
# <a name="convert-get-method-to-property--convert-property-to-get-method"></a>속성에 Get 메서드가 변환/속성 Get 메서드로 변환
## <a name="convert-get-method-to-property"></a>속성에 Get 메서드가 변환
**:** 속성 (및 필요에 따라 Set 메서드), Get 메서드가 변환할 수 있습니다 및 그 반대의 경우도 마찬가지입니다.

**경우:** 는 논리를 포함 하지 않는 Get 메서드가 있는 경우.

**방법:**

1. Get 메서드 이름에 커서를 놓습니다.

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **속성과 메서드를 대체** 미리 보기 창 팝업에서 합니다. Set 메서드가 있는 경우 변환할 수도 있습니다 Set 메서드가이 이번에 선택 하 여 **Get 대체 메서드 및 속성과 함께 Set 메서드에**합니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭을 선택는 **빠른 작업 및 리팩터링** 메뉴와 선택 **속성과 메서드를 대체** 미리 보기 창 팝업에서 합니다. Set 메서드가 있는 경우 변환할 수도 있습니다 Set 메서드가이 이번에 선택 하 여 **Get 대체 메서드 및 속성과 함께 Set 메서드에**합니다.

1. 코드 미리 보기의 변경에 만족 하는 키를 눌러 **Enter** 또는 수정이 메뉴를 클릭 하 고 변경 내용이 커밋됩니다.

예제:

```csharp
private int MyValue;

// Before
public int GetMyValue()
{
    return MyValue;
}

// Replace 'GetMyValue' with property

// After
public int MyValue
{
    get { return MyValue; }
}
```

## <a name="convert-property-to-get-method"></a>속성 Get 메서드로 변환
**:** Get 메서드를 속성으로 변환할 수 있습니다

**경우:** 즉시 이상 설정 하 고 값을 가져오는 포함 하는 속성이 있는 경우 

**방법:**

1. Get 메서드 이름에 커서를 놓습니다.

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **속성 메서드로 바꾸기** 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭을 선택는 **빠른 작업 및 리팩터링** 메뉴와 선택 **속성 메서드로 바꾸기** 미리 보기 창 팝업에서 합니다.

1. 코드 미리 보기의 변경에 만족 하는 키를 눌러 **Enter** 또는 수정이 메뉴를 클릭 하 고 변경 내용이 커밋됩니다.

## <a name="see-also"></a>참고 항목  
[리팩터링(C#)](../refactoring-csharp.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)