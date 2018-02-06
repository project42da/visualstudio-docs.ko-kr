---
title: "형식을 일치하는 파일로 이동 - 리팩터링(Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 510b984ad2de9476d53e9a5a4bcd667f393d3d4b
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="move-type-to-a-matching-file-in-visual-basic"></a>Visual Basic에서 형식을 일치하는 파일로 이동

**대상:** 선택한 형식을 같은 이름을 가진 별도의 파일로 이동할 수 있습니다.

**시기:** 동일한 파일에 구분하려는 여러 클래스, 구조체, 인터페이스 등이 있습니다.  

**이유:** 같은 파일에 여러 형식을 넣으면 이러한 형식을 찾기 어려울 수 있습니다.  형식을 같은 이름을 가진 파일로 이동하면 코드를 더 쉽게 읽고 탐색할 수 있습니다.

**방법:**

1. 이동할 형식 이름을 강조 표시하거나 형식 이름 내부에 텍스트 커서를 놓습니다.

   ![강조 표시된 코드](media/movetype-highlight-vb.png)

1. 다음 작업 중 하나를 수행합니다.
   * **키보드**
     * **Ctrl+.**를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거하고 [미리 보기] 창 팝업에서 ***TypeName*.vb로 형식 이동**을 선택합니다. 여기서 *TypeName*은 선택한 형식의 이름입니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭하고, **빠른 작업 및 리팩터링** 메뉴를 선택하고, [미리 보기] 창 팝업에서 ***TypeName*.vb로 형식 이동**을 선택합니다. 여기서 *TypeName*은 선택한 형식의 이름입니다.

   형식은 솔루션 내부에서 해당 이름을 가진 새 파일로 바로 이동됩니다.

   ![인라인 결과](media/movetype-result-vb.png)

## <a name="see-also"></a>참고 항목

[리팩터링](../refactoring-in-visual-studio.md)