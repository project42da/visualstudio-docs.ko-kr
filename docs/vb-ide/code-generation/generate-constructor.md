---
title: "생성자-코드 생성 (Visual Basic)를 생성 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2280cfa-a9ec-4b56-9d94-c8fd384db980
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 53b1ab5cb202995cb6a5e9eeef76ee4cf38b4ea9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="generate-a-constructor-in-visual-basic"></a>Visual Basic의 생성자를 생성
**:** 즉시 클래스에 새로운 생성자에 대 한 코드를 생성할 수 있습니다. 

**경우:** 새 생성자를 소개 하 고 제대로,를 자동으로 선언 하려고 합니다.  

**이유:** 이 기능에서, 적절 한 매개 변수를 자동으로 생성 되지만 생성자를 사용 하기 전에 선언할 수 있습니다. 

**방법:**

1. 줄에 커서를 놓고 아직 존재 하지 않는 생성자를 사용한 나타내는 빨간색 물결 기호는 합니다.

   ![강조 표시 된 코드](media/constructor_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택  **에 생성자가 생성 '*TypeName*' * * 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 마우스 오른쪽 단추로 클릭 하 고 선택 된 **빠른 작업 및 리팩터링** 메뉴와 선택  **에 생성자가 생성 '*TypeName*' * * 미리 보기 창 팝업에서 합니다.
     * 빨간색 물결 기호 위로 마우스를 클릭 하 고 ![전구](media/bulb.png) 표시 되는 아이콘입니다.
     * 클릭 하 고 ![전구](media/bulb.png) 커서가 있는 경우 텍스트 이미 빨간색 물결 기호는 줄에 왼쪽된 여백에 표시 되는 아이콘입니다.

   ![생성자 미리 보기를 생성 합니다.](media/constructor_preview.png)

   >[!TIP]
   >사용 하 여는 [ **변경 내용 미리 보기가** ](../../ide/preview-changes.md) 모두 선택 하기 전에 적용 될 변경 내용을 보려면 미리 보기 창의 맨 아래에 링크 합니다.

1. 생성자의 사용법에서 유추 된 모든 매개 변수와 함께 자동으로 만들어집니다.

   ![생성자 결과 생성 합니다.](media/constructor_result.png)
  
## <a name="see-also"></a>참고 항목  
[코드 생성(Visual Basic)](../code-generation-vb.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)