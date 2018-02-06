---
title: "지역 변수 소개 - 코드 생성(C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 6ba9478c09e55df54f94ed93c7a694f798ae76b4
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="introduce-a-local-variable-in-c"></a>C#에서 지역 변수 소개 #

**대상:** 기존 식을 대체할 지역 변수를 즉시 생성할 수 있습니다.

**시기:** 지역 변수에 있는 경우 나중에 쉽게 다시 사용할 수 있는 코드가 있습니다.

**이유:** 코드를 여러 번 복사하여 붙여넣으면 다양한 위치에서 사용할 수 있지만, 작업을 한 번 수행하고 지역 변수에 결과를 저장하고 전체적으로 지역 변수를 사용하는 것이 좋습니다.

**방법:**

1. 새 지역 변수에 할당할 식을 강조 표시합니다.

   ![강조 표시된 코드](media/local-highlight-cs.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 **‘*expression*’의 모든 항목에 대한 로컬 지정**을 선택합니다. 여기서 *expression*은 강조 표시한 코드입니다.
   * **마우스**
     * 마우스 오른쪽 단추를 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 **‘*expression*’의 모든 항목에 대한 로컬 지정**을 선택합니다. 여기서 *expression*은 강조 표시한 코드입니다.
     * 텍스트 커서가 이미 구부러진 빨간 곡선이 있는 줄 위에 있으면 왼쪽 여백에 나타나는 ![전구](media/bulb-cs.png) 아이콘을 클릭합니다.

   ![로컬 미리 보기 소개](media/local-preview-cs.png)

   > [!TIP]
   > 미리 보기 창 맨 아래에 있는 [**변경 내용 미리 보기**](../../ide/preview-changes.md) 링크를 사용하여 선택하기 전에 적용될 모든 변경 내용을 확인합니다.

1. 지역 변수는 해당 사용에서 추론된 형식을 사용하여 자동으로 만들어집니다.  새 이름을 입력하여 새 지역 변수에 새 이름을 지정합니다.

   ![로컬 결과 소개](media/local-result-cs.png)

   > [!NOTE]
   > **...모든 항목...** 메뉴 옵션을 사용하면 특별히 강조 표시한 항목만이 아니라 발견된 선택한 식의 모든 인스턴스를 대체할 수 있습니다.

## <a name="see-also"></a>참고 항목

[코드 생성](../code-generation-in-visual-studio.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)
