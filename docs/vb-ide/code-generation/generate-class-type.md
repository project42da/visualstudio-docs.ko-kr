---
title: "클래스 또는 형식-코드 생성 (Visual Basic)를 생성 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: VB
ms.assetid: ebc361fe-d9b1-4c7a-ae28-5e71b5775460
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vsl.GenerateFromUsage
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: a0a900b912c1a15c61dc17164571c1284743581c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="generate-a-class-or-type-in-visual-basic"></a>Visual Basic의 클래스 또는 형식 생성
**:** 즉시 클래스 또는 형식에 대 한 코드를 생성할 수 있습니다. 

**경우:** 새 클래스 또는 형식을 소개 하 고 제대로,를 자동으로 선언 하려고 합니다.  

**이유:** 이 기능 클래스를 생성 하거나 자동으로 입력 됩니다 있지만 사용 하기 전에 클래스 또는 형식에 선언할 수 있습니다. 

**방법:**

1. 줄에 커서를 놓고 아직 존재 하지 않는 클래스를 사용한 나타내는 빨간색 물결 기호는 합니다.

   ![강조 표시 된 코드](media/class_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 미리 보기 창 팝업에서 옵션 중 하나를 선택 합니다.
   * **마우스**
     * 마우스 오른쪽 단추로 클릭 하 고 선택 된 **빠른 작업 및 리팩터링** 메뉴와 미리 보기 창 팝업에서 옵션 중 하나를 선택 합니다.
     * 빨간색 물결 기호 위로 마우스를 클릭 하 고 ![전구](media/bulb.png) 표시 되는 아이콘입니다.
     * 클릭 하 고 ![전구](media/bulb.png) 커서가 있는 경우 텍스트 이미 빨간색 물결 기호는 줄에 왼쪽된 여백에 표시 되는 아이콘입니다.

   ![클래스의 미리 보기를 생성 합니다.](media/class_preview.png)

   선택 | 설명
   --- | ---
   클래스의 생성*TypeName*' 새 파일에 | 라는 클래스를 만들고 *TypeName* 라는 파일에 *TypeName*.cs/.vb
   클래스의 생성*TypeName*' | 라는 클래스를 만들고 *TypeName* 현재 파일에 있습니다.
   중첩 된 클래스를 생성*TypeName*' | 라는 클래스를 만들고 *TypeName* 현재 클래스 안에 중첩 합니다.
   새 형식을 생성 합니다... | 지정 하는 속성의 모든 새 클래스 또는 구조체를 만듭니다.

   >[!TIP]
   >사용 하 여는 [ **변경 내용 미리 보기가** ](../../ide/preview-changes.md) 모두 선택 하기 전에 적용 될 변경 내용을 보려면 미리 보기 창의 맨 아래에 링크 합니다.

1. 선택 하는 경우는 **새 형식 생성 중...**  항목 대화 상자 팝업 됩니다 몇 가지 추가 작업을 수행할 수 있도록 합니다.

   ![형식 생성](media/class_newtype.png)

   선택 | 설명
   --- | ---
   액세스 | 한 유형을 설정 *기본*, *내부* 또는 *공용* 액세스 합니다.
   종류 | 으로 설정할 수 있습니다 *클래스* 또는 *구조체*합니다.
   name | 이 변경할 수 없습니다 및 이미 입력 한 이름이 됩니다.
   프로젝트 | 솔루션에 여러 프로젝트가 있는 경우 라이브 클래스/구조체 원하는 위치를 선택할 수 있습니다.
   파일 이름 | 새 파일을 만들거나 기존 파일에 형식을 추가할 수 있습니다.

1. 클래스/구조체의 사용법에서 유추 하는 생성자로 자동으로 만들어집니다.

   ![클래스의 결과 생성 합니다.](media/class_result.png)

## <a name="see-also"></a>참고 항목  
[코드 생성(Visual Basic)](../code-generation-vb.md)  
[변경 내용 미리 보기](../../ide/preview-changes.md)