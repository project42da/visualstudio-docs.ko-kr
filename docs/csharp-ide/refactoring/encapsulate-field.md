---
title: "필드 캡슐화-리팩터링 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 12/14/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: 39a9ed11-363f-4dda-af3b-0affe6db1d42
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.encapsulatefield
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: 59b71a0716415dcedeab9954486ef27e0fc438d7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="encapsulate-a-field-in-c"></a>C#에서 필드 캡슐화 #
**:** 필드를 속성으로 설정 하 고 새로 만든된 속성을 사용 하려면 해당 필드의 모든 사용을 업데이트할 수 있습니다.

**경우:** 필드를 속성으로 이동 하 여 해당 필드에 대 한 모든 참조를 업데이트 합니다.  

**이유:** 필드에 다른 클래스 액세스 권한을 부여 하려면 않으려는 있습니다 이러한 클래스를 직접 액세스할 수 있습니다.  속성의 필드를 래핑하여 예를 들어 할당 되는 값을 확인 하는 코드를 작성할 수 있습니다.

**방법:**

1. 강조 표시 하거나 캡슐화 할 필드의 이름 내부 텍스트 커서를 놓습니다.

   ![강조 표시 된 코드](media/encapsulate_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl + R**, 다음 **Ctrl + E**합니다.  바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴 선택 **필드 캡슐화** 미리 보기 창 팝업에서 항목입니다.
   * **마우스**
     * 선택 **편집 > 리팩터링 > 필드 캡슐화**합니다.
     * 코드를 마우스 오른쪽 단추로 클릭, 선택는 **빠른 작업 및 리팩터링** 메뉴 선택 **필드 캡슐화** 미리 보기 창 팝업에서 항목입니다.

   선택 | 설명
   --------- | -----------
   **필드 캡슐화 (그리고 속성을 사용)** | 속성을 사용 하 여 필드를 캡슐화 하 고 생성 된 속성을 사용 하는 필드의 모든 사용 업데이트
   **필드 캡슐화 (그러나 여전히 필드를 사용)** | 속성을 사용 하 여 필드를 캡슐화 하지만 상태 필드의 모든 사용을 그대로 유지

   속성은 즉시 만들어집니다 및 참조 필드를 선택 하는 경우 업데이트할 수 있습니다.

   > [!TIP]
   > 사용 하 여는 [ **변경 내용 미리 보기가** ](../../ide/preview-changes.md) 를 커밋하기 전에 결과 것을 확인 하려면 팝업 창에 링크 합니다.

   ![속성 결과 캡슐화 합니다.](media/encapsulate_result.png)

## <a name="see-also"></a>참고 항목  
[리팩터링(C#)](../refactoring-csharp.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)