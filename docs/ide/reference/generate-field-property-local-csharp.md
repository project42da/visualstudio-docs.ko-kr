---
title: "필드, 속성 또는 로컬 생성 - 코드 생성(C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c11888e0-31b1-44cc-9037-98d3f8b3623b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 7cc27d498cbc082ad76d47d2326d1ee8fb0ebbb0
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2018
---
# <a name="generate-a-field-property-or-local-in-c"></a>C#에서 필드, 속성 또는 로컬 생성 #
**대상:** 이전에 선언되지 않은 필드, 속성 또는 로컬에 대한 코드를 즉시 생성할 수 있습니다. 

**시기:** 새 필드, 속성 또는 로컬을 소개하고 자동으로 해당 항목을 제대로 선언하려고 합니다.  

**이유:** 필드, 속성 또는 로컬을 사용하기 전에 사용자가 해당 항목을 선언할 수 있지만, 이 기능은 선언 및 형식을 자동으로 생성합니다. 

**방법:**

1. 존재하지 않는 필드, 로컬 또는 속성을 사용했음을 나타내는 빨간색 구부러진 곡선이 있는 줄에 커서를 놓습니다.

   ![강조 표시된 코드](media/field-highlight-cs.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 **필드/속성/로컬 생성**을 선택합니다.
   * **마우스**
     * 마우스 오른쪽 단추를 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 **필드/속성/로컬 생성**을 선택합니다.
     * 빨간색 구부러진 곡선 위로 마우스를 이동하고 표시되는 ![전구](media/bulb-cs.png) 아이콘을 클릭합니다.
     * 텍스트 커서가 이미 구부러진 빨간 곡선이 있는 줄 위에 있으면 왼쪽 여백에 나타나는 ![전구](media/bulb-cs.png) 아이콘을 클릭합니다.

   ![필드/속성/로컬 생성 미리 보기](media/field-preview-cs.png)

   >[!TIP]
   >미리 보기 창 맨 아래에 있는 [**변경 내용 미리 보기**](../../ide/preview-changes.md) 링크를 사용하여 선택하기 전에 적용될 모든 변경 내용을 확인합니다.

1. 필드, 속성 또는 로컬은 해당 사용에서 추론된 형식을 사용하여 자동으로 만들어집니다.

   ![필드/속성/로컬 생성 결과](media/field-result-cs.png)

## <a name="see-also"></a>참고 항목

[코드 생성](../code-generation-in-visual-studio.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)
