---
title: "메서드 생성 - 코드 생성(C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 683790b4-b68b-42d7-8dc4-a68eca05aa01
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: e4caf80bec38305613111f290b80eafb74547598
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="generate-a-method-in-c"></a>C#에서 메서드 생성 #
**대상:** 클래스에 메서드를 즉시 추가할 수 있습니다. 

**시기:** 새 메서드를 소개하고 자동으로 메서드를 제대로 선언하려고 합니다.  

**이유:** 이 기능을 사용하기 전에 메서드 및 매개 변수를 선언할 수 있지만 이 기능은 선언을 자동으로 생성합니다. 

**방법:**

1. 존재하지 않는 메서드를 사용했음을 나타내는 빨간색 구부러진 곡선이 있는 줄에 커서를 놓습니다.

   ![강조 표시된 코드](media/method-highlight-cs.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 **메서드 생성**을 선택합니다.
   * **마우스**
     * 마우스 오른쪽 단추를 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 **메서드 생성**을 선택합니다.
     * 빨간색 구부러진 곡선 위로 마우스를 이동하고 표시되는 ![전구](media/bulb-cs.png) 아이콘을 클릭합니다.
     * 텍스트 커서가 이미 구부러진 빨간 곡선이 있는 줄 위에 있으면 왼쪽 여백에 나타나는 ![전구](media/bulb-cs.png) 아이콘을 클릭합니다.

   ![메서드 생성 미리 보기](media/method-preview-cs.png)

   >[!TIP]
   >미리 보기 창 맨 아래에 있는 [**변경 내용 미리 보기**](../../ide/preview-changes.md) 링크를 사용하여 선택하기 전에 적용될 모든 변경 내용을 확인합니다.

1. 메서드는 해당 사용에서 추론된 매개 변수를 사용하여 자동으로 만들어집니다.

   ![메서드 생성 결과](media/method-result-cs.png)

## <a name="see-also"></a>참고 항목

[코드 생성](../code-generation-in-visual-studio.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)
