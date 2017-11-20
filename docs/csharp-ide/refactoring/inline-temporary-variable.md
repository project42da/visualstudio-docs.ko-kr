---
title: "인라인 임시 변수-리팩터링 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0182179f-f74f-47a2-a1dc-b60c86f9abaf
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e6e9ed28a42aa3d7521a059b668eed8ae1d28b8e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="inline-a-temporary-variable-with-c"></a>C#을 사용 하 여 임시 변수를 인라인으로 #
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
[리팩터링(C#)](../refactoring-csharp.md)