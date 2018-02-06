---
title: "C#에서 Get 메서드를 속성으로 변환 및 속성을 Get 메서드로 변환 | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
ms.devlang: csharp
author: kuhlenh
ms.author: kaseyu
manager: ghogen
f1_keywords: vs.csharp.refactoring.convertmethodtoproperty
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: a23af31c5099908ed0b6fed07404216a57975f75
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="convert-get-method-to-property--convert-property-to-get-method"></a>Get 메서드를 속성으로 변환/속성을 Get 메서드로 변환

## <a name="convert-get-method-to-property"></a>Get 메서드를 속성으로 변환

**대상:** Get 메서드를 속성(및 선택적으로 Set 메서드)으로 변환하고 그 반대로도 변환할 수 있습니다.

**시기:** 논리를 포함하지 않는 Get 메서드가 있습니다.

**방법:**

1. Get 메서드 이름에 커서를 놓습니다.

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 **메서드를 속성으로 대체**를 선택합니다. Set 메서드가 있는 경우 **Get 메서드 및 Set 메서드를 속성으로 대체**를 선택하여 이때 Set 메서드를 변환할 수도 있습니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 **메서드를 속성으로 대체**를 선택합니다. Set 메서드가 있는 경우 **Get 메서드 및 Set 메서드를 속성으로 대체**를 선택하여 이때 Set 메서드를 변환할 수도 있습니다.

1. 코드 미리 보기의 변경 내용에 만족할 경우 **Enter** 키를 누르거나 메뉴에서 수정을 클릭하면 변경 내용이 커밋됩니다.

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

## <a name="convert-property-to-get-method"></a>속성을 Get 메서드로 변환

**대상:** 속성을 Get 메서드로 변환할 수 있습니다.

**시기:** 값을 즉시 설정하고 가져오는 것 이외에 관련된 속성이 있습니다. 

**방법:**

1. Get 메서드 이름에 커서를 놓습니다.

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 **속성을 메서드로 대체**를 선택합니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 **속성을 메서드로 대체**를 선택합니다.

1. 코드 미리 보기의 변경 내용에 만족할 경우 **Enter** 키를 누르거나 메뉴에서 수정을 클릭하면 변경 내용이 커밋됩니다.

## <a name="see-also"></a>참고 항목

[리팩터링](../refactoring-in-visual-studio.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)