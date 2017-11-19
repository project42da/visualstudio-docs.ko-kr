---
title: "동기화 형식 및 파일 이름-리팩터링 (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff86d7bd-837b-4664-b0ea-d3ee0c52fe87
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: VB
ms.openlocfilehash: da6f39dd3573d361c1da579eb3d84c2c8ceeb517
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-in-visual-basic"></a>동기화 하는 파일 이름 또는 Visual Basic의 형식에는 파일 이름이 유형

<!-- VERSIONLESS -->
**이 기능은 이상 Visual Studio 2017에 사용할 수 있습니다.  또한이 리팩터링에 대 한.NET 표준 프로젝트가 아직 지원 되지 않습니다.**

**:** 에 파일 이름을 일치 하는 형식의 이름을 바꾸거나 파일 이름을 포함 된 형식과 일치 하도록 이름을 바꿀 수 있습니다.

**경우:** 이름이 바뀐 파일 또는 형식 및 해당 파일 또는 형식 일치 하도록 아직 업데이트 하지 않았습니다. 

**이유:** 형식을 다른 이름 또는 그 반대로 원하는 내용을 찾기 어려운 것 인 파일에 배치 합니다.  코드는 형식이 나 파일 이름을 바꿔서 더 쉽게 읽고 탐색 하기 쉽게 향상 됩니다.

**방법:**

1. 강조 표시 하거나 동기화 하는 형식의 이름 내부 텍스트 커서를 놓습니다.

   ![강조 표시 된 코드](media/synctype_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거로 **빠른 작업 및 리팩터링** 메뉴와 선택 **이름 바꾸기 파일을 *TypeName*.vb** 미리 보기 창 팝업에서 위치 *TypeName* 선택한 형식의 이름입니다.
     * 키를 눌러 **Ctrl +.** 트리거로 **빠른 작업 및 리팩터링** 메뉴를 선택 **형식 이름 바꾸기 _Filename_**  미리 보기 창 팝업에서 위치 *파일이름* 현재 파일의 이름입니다.
   * **마우스**
     * 코드를 마우스 오른쪽 단추로 클릭, 선택는 **빠른 작업 및 리팩터링** 메뉴에서을 선택 **이름 바꾸기 파일을 *TypeName*.vb** 미리 보기 창 팝업에서 위치 *TypeName* 선택한 형식의 이름입니다.
     * 코드를 마우스 오른쪽 단추로 클릭을 선택는 **빠른 작업 및 리팩터링** 메뉴에서을 선택 **를 형식의 이름을 바꾸려면 _Filename_**  미리 보기 창 팝업에서 위치  *Filename* 현재 파일의 이름입니다.

   형식 또는 파일 즉시 바뀝니다.  파일에 다음 예제에서 **Employee.vb** 로 변경 되어 **Person.vb** 형식 이름과 일치 해야 합니다.

   ![Inline 결과](media/synctype_result.png)

## <a name="see-also"></a>참고 항목  
[리팩터링(Visual Basic)](../refactoring-vb.md)
