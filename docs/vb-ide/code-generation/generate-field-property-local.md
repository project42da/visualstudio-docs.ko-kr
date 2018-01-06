---
title: "필드, 속성 또는 로컬-코드 생성 (Visual Basic)를 생성 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c11888e0-31b1-44cc-9037-98d3f8b3623b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8e23dfa2b482a16d70ef71614ba35f9b20523aeb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="generate-a-field-property-or-local-in-visual-basic"></a>Visual Basic의 필드, 속성 또는 로컬 생성
**:** 즉시 이전에 선언 되지 않은 필드, 속성 또는 로컬에 대 한 코드를 생성할 수 있습니다. 

**경우:** 입력 하는 동안 새 필드, 속성 또는 로컬을 소개 하 고 제대로,를 자동으로 선언 하려고 합니다.  

**이유:** 있지만이 기능은 선언을 생성 하 고 자동으로 입력 됩니다 사용 하기 전에 필드, 속성 또는 로컬을 선언할 수 있습니다. 

**방법:**

1. 줄에 커서를 놓고 로컬 필드를 사용한 적이 있다면 나타내는 빨간색 물결 기호 또는 아직 존재 하지 않는 속성이 있는 경우.

   ![강조 표시 된 코드](media/field_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택  **생성 변수 '*이름*' > 필드/속성을 생성/로컬 * * 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 마우스 오른쪽 단추로 클릭 하 고 선택 된 **빠른 작업 및 리팩터링** 메뉴와 선택  **생성 변수 '*이름*' > 필드/속성을 생성/로컬 * * 미리 보기에서 팝업 창입니다.
     * 빨간색 물결 기호 위로 마우스를 클릭 하 고 ![전구](media/bulb.png) 표시 되는 아이콘입니다.
     * 클릭 하 고 ![전구](media/bulb.png) 커서가 있는 경우 텍스트 이미 빨간색 물결 기호는 줄에 왼쪽된 여백에 표시 되는 아이콘입니다.

   ![필드/속성/로컬 미리 보기를 생성 합니다.](media/field_preview.png)

   >[!TIP]
   >사용 하 여는 [ **변경 내용 미리 보기가** ](../../ide/preview-changes.md) 모두 선택 하기 전에 적용 될 변경 내용을 보려면 미리 보기 창의 맨 아래에 링크 합니다.

1. 필드, 속성 또는 로컬 사용법에서 유추 된 형식으로 자동으로 생성 됩니다.

   ![필드/속성/로컬 결과 생성 합니다.](media/field_result.png)

## <a name="see-also"></a>참고 항목  
[코드 생성(Visual Basic)](../code-generation-vb.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)