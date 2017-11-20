---
title: "일치 하는 파일-리팩터링 (C#)으로 형식을 이동 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40f58c34-c50f-4297-91b2-2e243380dcc9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9fa5a15f9c8e688c973594309efbfa6cb5d10e8b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="move-a-type-to-a-matching-file-in-c"></a>C#에서 일치 하는 파일 형식을 이동합니다 #
**:** 선택한 유형에 이름이 같은 별도 파일로 이동할 수 있습니다.

**경우:** 분리 하려는 있는 동일한 파일에 있는 여러 클래스, 구조체, 인터페이스, 등입니다.  

**이유:** 여러 형식이 동일한 파일에 넣지 어려울 수 있습니다 이러한 형식을 찾으려고 합니다.  코드 형식 이름이 같은 파일을 이동 하 여 더 쉽게 읽고 탐색 하기 쉽게 향상 됩니다.

**방법:**

1. 강조 표시 하거나 이동 하는 형식의 이름 내부 텍스트 커서를 놓습니다.

   ![강조 표시 된 코드](media/movetype_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴를 선택 **종류를 이동 *TypeName*.cs** 미리 보기 창 팝업에서 위치 *TypeName* 선택한 형식의 이름입니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭을 선택는 **빠른 작업 및 리팩터링** 메뉴와 선택 **종류를 이동 *TypeName*.cs** 미리 보기 창 팝업에서 위치  *TypeName* 선택한 형식의 이름입니다.

   형식 내부 솔루션에서 해당 이름 가진 새 파일을 즉시 이동 합니다.

   ![Inline 결과](media/movetype_result.png)

## <a name="see-also"></a>참고 항목  
[리팩터링(C#)](../refactoring-csharp.md)