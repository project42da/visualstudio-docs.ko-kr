---
title: "인라인 임시 변수-리팩터링 (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a63d6407-5acb-4d5f-8c0e-ecedddc07177
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3607e646f5f1ccc6121e5ee8a5b71772008f1ce8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="inline-a-temporary-variable-in-visual-basic"></a>인라인 Visual Basic의 임시 변수
**:** 하면 임시 변수의 사용을 제거 하 고 대신 실제 코드로 대체 합니다.

**경우:** 임시 변수를 사용 하면 코드 이해 하기 어렵습니다.  

**이유:** 임시 변수를 제거 좀 더 쉽게 코드는 특정 상황에서 읽기

**방법:**

1. 강조 표시 하거나 인라인 될 임시 변수 내 텍스트 커서를 놓습니다.

   ![강조 표시 된 코드](media/inline_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **인라인 임시 변수** 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭을 선택는 **빠른 작업 및 리팩터링** 메뉴와 선택 **인라인 임시 변수** 미리 보기 창 팝업에서 합니다.

   변수 제거 되 고 해당 용도 즉시 변수의 값으로 대체 합니다.

   ![Inline 결과](media/inline_result.png)

## <a name="see-also"></a>참고 항목
[리팩터링(Visual Basic)](../refactoring-vb.md)