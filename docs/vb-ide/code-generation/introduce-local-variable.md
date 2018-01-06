---
title: "코드 생성 (Visual Basic) 지역 변수-소개 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1490d6ac-ed56-4d03-95db-c23f23cba70d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9caafd73703478c75d7d91708ddcf5d14139e7fa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="introduce-a-local-variable-in-visual-basic"></a>Visual Basic의 지역 변수를 소개 합니다.
**:** 즉시 기존 식을 바꿀 지역 변수를 생성할 수 있습니다.

**경우:** 코드가 다시 사용할 수 있습니다 쉽게 나중에 지역 변수에 것입니다.  

**하지만 이유:** 수 복사 및 붙여 코드 여러 번 다양 한 위치에서 사용 하는 것은 한 번에 작업을 수행할 지역 변수에 결과 저장 하 고, 로컬 변수 throughought를 사용 하 여 합니다. 

**방법:**

1. 새 지역 변수에 할당 하려는 식 강조 표시 합니다.

   ![강조 표시 된 코드](media/local_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택  **(의 모든 항목)에 대 한 로컬 '*식*' * * 미리 보기 창 팝업에서 위치 *식* 선택한 코드입니다.
   * **마우스**
     * 마우스 오른쪽 단추로 클릭 하 고 선택 된 **빠른 작업 및 리팩터링** 메뉴와 선택  **(의 모든 항목)에 대 한 로컬 '*식*' * * 미리 보기 창 팝업에서 여기서 *식* 선택한 코드입니다.
     * 클릭 하 고 ![전구](media/bulb.png) 커서가 있는 경우 텍스트 이미 빨간색 물결 기호는 줄에 왼쪽된 여백에 표시 되는 아이콘입니다.

   ![로컬 미리 보기 소개](media/local_preview.png)

   >[!TIP]
   >사용 하 여는 [ **변경 내용 미리 보기가** ](../../ide/preview-changes.md) 모두 선택 하기 전에 적용 될 변경 내용을 보려면 미리 보기 창의 맨 아래에 링크 합니다.

1. 지역 변수 사용법에서 유추 된 형식으로 자동으로 만들어집니다.  입력 하 여 새 지역 변수에 새 이름을 지정 합니다.

   ![로컬 결과 소개 합니다.](media/local_result.png)

   >[!NOTE]
   >사용할 수는 **..의 디스플레이로 발생 하는 중...**  메뉴 옵션을 선택한 발견 식 뿐 아니라 구체적으로 강조 표시 한의 모든 인스턴스를 대체 합니다.

## <a name="see-also"></a>참고 항목  
[코드 생성(Visual Basic)](../code-generation-vb.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md) 