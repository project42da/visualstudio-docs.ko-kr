---
title: "C#에서 메서드 추출 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.extractmethod
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: 805d215eb5d885d8ab38aa288ef2c8fd3e7e90cf
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2018
---
# <a name="extract-a-method-in-c"></a>C#에서 메서드 추출 #

**대상:** 코드 조각을 고유한 메서드로 변환할 수 있습니다.

**시기:** 다른 메서드에서 호출해야 하는 일부 메서드에 기존 코드 조각이 있습니다.

**이유:** 해당 코드를 복사하여 붙여넣을 수 있지만 중복이 발생합니다.  더 나은 솔루션은 다른 메서드에서 자유롭게 호출할 수 있는 고유한 메서드로 해당 조각을 리팩터링하는 것입니다.

**방법:**

1. 추출할 코드를 강조 표시합니다.

   ![강조 표시된 코드](media/extractmethod-highlight-cs.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+R**을 누른 다음 **Ctrl+M**을 누릅니다.  바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 **메서드 추출**을 선택합니다.
   * **마우스**
     * **편집 > 리팩터링 > 메서드 추출**을 선택합니다.
     * 코드를 마우스 오른쪽 단추로 클릭하고 **리팩터링 > 추출 > 메서드 추출**을 선택합니다.
     * 코드를 마우스 오른쪽 단추로 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 **메서드 추출**을 선택합니다.

   메서드가 즉시 만들어집니다.  이제 여기에서 새 이름을 입력하여 간단히 메서드 이름을 바꿀 수 있습니다.

   > [!TIP]
   > 또한 이 새 이름을 사용하도록 주석과 기타 문자열을 업데이트하고, IDE의 오른쪽 위에 표시되는 **이름 바꾸기** 상자의 확인란을 사용하여 저장하기 전에 [변경 내용을 미리 볼](../../ide/preview-changes.md) 수 있습니다.

   ![메서드 이름 바꾸기](media/extractmethod-rename-cs.png)

1. 변경 내용에 만족할 경우 **적용** 단추를 클릭하거나 **Enter** 키를 누르면 변경 내용이 커밋됩니다.

## <a name="see-also"></a>참고 항목

[리팩터링](../refactoring-in-visual-studio.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)