---
title: "Visual Basic에서 필드를 속성으로 리팩터링 | Microsoft Docs"
ms.custom: 
ms.date: 12/14/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.encapsulatefield
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 010a297745ed6028f7ee127fffc210097d6d26f5
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2018
---
# <a name="encapsulate-a-field-in-visual-basic"></a>Visual Basic에서 필드 캡슐화

**대상:** 필드를 속성으로 변환하고 새로 만들어진 속성을 사용하도록 해당 필드의 모든 사용을 업데이트할 수 있습니다.

**시기:** 필드를 속성으로 이동하고 해당 필드에 대한 모든 참조를 업데이트하려고 합니다.  

**이유**: 다른 클래스에 필드에 대한 액세스 권한을 부여하지만 해당 클래스가 직접 액세스할 수 없게 하려고 합니다.  예를 들어 필드를 속성으로 래핑하면 할당되는 값을 확인하는 코드를 작성할 수 있습니다.

**방법:**

1. 캡슐화할 필드 이름을 강조 표시하거나 필드 이름 내부에 텍스트 커서를 놓습니다.

   ![강조 표시된 코드](media/encapsulate-highlight-vb.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+R**을 누른 다음 **Ctrl+E**를 누릅니다.  바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 **필드 캡슐화** 항목을 선택합니다.
   * **마우스**
     * **편집 > 리팩터링 > 필드 캡슐화**를 선택합니다.
     * 코드를 마우스 오른쪽 단추로 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 **필드 캡슐화** 항목을 선택합니다.

   선택 | 설명
   --------- | -----------
   **필드 캡슐화(및 속성 사용)** | 속성을 사용하여 필드를 캡슐화하고 생성된 속성을 사용하도록 필드의 모든 사용을 업데이트합니다.
   **필드 캡슐화(그러나 필드 계속 사용)** | 속성을 사용하여 필드를 캡슐화하지만 필드의 모든 사용을 그대로 유지합니다.

   선택하면 속성이 즉시 만들어지고 필드에 대한 참조가 업데이트됩니다.

   > [!TIP]
   > 팝업 창의 [**변경 내용 미리 보기**](../../ide/preview-changes.md) 링크를 사용하여 커밋하기 전에 결과를 확인합니다.

   ![속성 캡슐화 결과](media/encapsulate-result-vb.png)

## <a name="see-also"></a>참고 항목

[리팩터링](../refactoring-in-visual-studio.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)