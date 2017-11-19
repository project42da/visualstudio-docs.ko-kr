---
title: "메서드-리팩터링 (Visual Basic) 추출 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: VB
ms.assetid: 8ad16c15-432b-4b8c-86fd-5f31ad652d24
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.extractmethod
dev_langs: VB
ms.openlocfilehash: 56e83e6410093467349e4a45a01042133cc53555
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="extract-a-method-in-visual-basic"></a>Visual Basic에서 메서드 추출
**:** 자체 메서드로 코드의 일부를 회전할 수 있습니다.

**경우:** 기존 코드의 일부 다른 메서드를 호출 하는 메서드가 있다고 있는 합니다.  

**이유:** 있습니다 수 복사/붙여넣기 해당 코드 하지만 중복을 초래 합니다.  다른 방법으로 든 자유롭게 호출할 수 있는 자체 메서드로 해당 조각을 리팩터링 하는 것이 좋습니다.

**방법:**

1. 압축을 풀 코드를 강조 표시 합니다.

   ![강조 표시 된 코드](media/extractmethod_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl + R**, 다음 **Ctrl + M**합니다.  바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **메서드 추출** 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 선택 **편집 > 리팩터링 > 메서드 추출**합니다.
     * 코드를 마우스 오른쪽 단추로 클릭 하 고 선택 **리팩터링 > 추출 > 메서드 추출**합니다.
     * 코드를 마우스 오른쪽 단추로 클릭, 선택는 **빠른 작업 및 리팩터링** 메뉴와 선택 **메서드 추출** 미리 보기 창 팝업에서 합니다.

   메서드를 즉시 생성 됩니다.  여기에서 새 이름을 입력 하 여 이제 메서드를 바꿀 수 있습니다.

   > [!TIP]
   > 주석 및이 새 이름을 사용 하 여 다른 문자열을 업데이트할 수도 있습니다으로 [변경 내용 미리 보기](../../ide/preview-changes.md) 전에 저장, 확인란은 **이름 바꾸기** 위쪽에 나타나는 상자 IDE의 오른쪽입니다.

   ![메서드 이름 바꾸기](media/extractmethod_rename.png)

1. 변경 하 여 만족 했으면 클릭는 **적용** 단추를 클릭 하거나 눌러 **Enter** 변경 내용이 커밋됩니다.

## <a name="see-also"></a>참고 항목  
[리팩터링(Visual Basic)](../refactoring-vb.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)