---
title: "이름 바꾸기-리팩터링 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: 60e2a623-b56d-4591-93dc-e51429e4e1ba
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.rename
dev_langs: CSharp
ms.openlocfilehash: c89aae8e6e0f43ee2083bba46f2bbeeadd488535
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="rename-a-code-symbol-in-c"></a>C# 코드 기호 이름 바꾸기 #
**:** 필드, 지역 변수, 메서드, 네임 스페이스, 속성 및 형식 등의 코드 기호에 대 한 식별자의 이름을 바꿀 수 있습니다.

**경우:** 안전 하 게 모든 인스턴스 및 새 이름 복사/붙여넣기를 필요 없이 이름을 바꿀 하는 것입니다.  

**이유:** 복사 및 프로젝트 전체에 대해 새 이름을 붙여 넣는 것 오류가 발생 합니다.  이 리팩터링 도구 이름 바꾸기 작업을 수행할 정확 하 게 됩니다.

**방법:**

1. 강조 표시 하거나 이름을 바꿀 항목 내 텍스트 커서를 놓습니다.

   ![강조 표시 된 코드](media/rename_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl + R**, 다음 **Ctrl + R**합니다.  바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
   * **마우스**
     * 선택 **편집 > 리팩터링 > 이름 바꾸기**합니다.
     * 코드를 마우스 오른쪽 단추로 클릭 하 고 선택 **이름 바꾸기**합니다.

1. 새 이름을 입력 하 여 항목을 이름을 바꿉니다.

   ![애니메이션 이름 바꾸기](media/rename_animated.gif)

   > [!TIP]
   > 주석 및이 새 이름을 사용 하 여 다른 문자열을 업데이트할 수도 있습니다으로 [변경 내용 미리 보기](../../ide/preview-changes.md) 전에 저장, 확인란은 **이름 바꾸기** 위쪽에 나타나는 상자 IDE의 오른쪽입니다.

1. 변경 하 여 만족 했으면 클릭는 **적용** 단추를 클릭 하거나 눌러 **Enter** 변경 내용이 커밋됩니다.

> [!NOTE]
> 충돌이 발생 하는 이미 존재 하는 이름을 사용 하는 경우는 **이름 바꾸기** 상자 IDE에 경고 메시지가 표시 됩니다.
>
> ![이름 변경 충돌](media/rename_conflict.png)

## <a name="see-also"></a>참고 항목  
[리팩터링(C#)](../refactoring-csharp.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)
