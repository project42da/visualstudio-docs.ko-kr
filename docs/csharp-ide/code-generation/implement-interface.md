---
title: "-코드 생성 (C#) 인터페이스를 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bebff2ad-25b6-4adc-8762-60d23bdd639a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: e0b8df77e82ada8197b89fcdf451e4234a43669f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="implement-an-interface-in-c"></a>C#에서 인터페이스를 구현 합니다. #
**:** 즉시 인터페이스를 구현 하는 데 필요한 코드를 생성할 수 있습니다. 

**경우:** 인터페이스에서 상속 하려는 경우.  

**이유:** 이 기능에서 모든 메서드 시그니처를 자동으로 생성 되지만 하나씩 하 여 모든 인터페이스를 수동으로 구현할 수 있습니다. 

**방법:**

1. 줄에 커서를 놓고 인터페이스를 참조 한 있지만 모든 필수 멤버를 구현 하지 나타내는 빨간색 물결 기호는 합니다.

   ![강조 표시 된 코드](media/interface_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **인터페이스를 명시적으로 구현** 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 마우스 오른쪽 단추로 클릭 하 고 선택 된 **빠른 작업 및 리팩터링** 메뉴와 선택 **인터페이스를 명시적으로 구현** 미리 보기 창 팝업에서 합니다.
     * 빨간색 물결 기호 위로 마우스를 클릭 하 고 ![전구](media/bulb.png) 표시 되는 아이콘입니다.
     * 클릭 하 고 ![전구](media/bulb.png) 커서가 있는 경우 텍스트 이미 빨간색 물결 기호는 줄에 왼쪽된 여백에 표시 되는 아이콘입니다.

   ![구현 클래스 미리 보기](media/interface_preview.png)

   >[!TIP]
   >사용 하 여는 [ **변경 내용 미리 보기가** ](../../ide/preview-changes.md) 모두 선택 하기 전에 적용 될 변경 내용을 보려면 미리 보기 창의 맨 아래에 링크 합니다.
   >
   >또한 사용할 수는 **문서**, **프로젝트**, 및 **솔루션** 여러 간의 적절 한 메서드 서명을 위해 미리 보기 창의 맨 아래에 링크 인터페이스를 구현 하는 클래스입니다.

1. 인터페이스의 메서드 서명에 자동으로 생성 된, 구현할 준비가 됩니다.

   ![클래스의 결과 구현 합니다.](media/interface_result.png)

   >[!TIP]
   >사용 하 여는 **인터페이스를 명시적으로 구현** 옵션을 앞에 각 이름 충돌을 피하기 위해 인터페이스 이름 사용 하 여 메서드를 생성 합니다.
   >
   >![인터페이스 구현 명시적으로 발생 합니다.](media/interface_explicitresult.png); 

## <a name="see-also"></a>참고 항목  
[코드 생성(C#)](../code-generation-csharp.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)  
