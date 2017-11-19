---
title: "인터페이스-리팩터링 (Visual Basic) 추출 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: VB
ms.assetid: db857fb1-3e22-46e2-b15a-56ef9f329235
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.extractinterface
dev_langs: VB
ms.openlocfilehash: 9616cae1282b992722f75eee091e2c9d271e85f6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="extract-an-interface-in-visual-basic"></a>Visual Basic의 인터페이스 추출
**:** 클래스, 구조체 또는 인터페이스에서 기존 멤버를 사용 하는 인터페이스를 만들 수 있습니다.

**경우:** 있는 여러 클래스, 구조체 또는 공용 이며 다른 클래스, 구조체 또는 인터페이스에서 사용 될 수 있는 메서드를 사용 하는 인터페이스입니다.

**이유:** 인터페이스는 개체 지향 디자인에 대 한 훌륭한 구문입니다.  Eat, 음료, 절전 모드와 같은 일반적인 메서드를 모두 가질 수 있는 다양 한 동물 (Dog, Cat, 새)에 대 한 클래스를 가정 합니다.  IAnimal 같은 인터페이스를 사용 하 여 Dog, Cat, 및 새 공통 이러한 방법에 대 한 "서명"을 하면 있습니다.  

**방법:**

1. 작업을 수행 하는 클래스의 이름을 강조 표시 하거나만 클래스 이름에 텍스트 커서 어딘가에 지정할 합니다.

   ![강조 표시 된 코드](media/extractinterface_highlight.png)

1. 다음으로, 다음 중 하나를 수행 합니다.
   * **키보드**
     * 키를 눌러 **Ctrl + R**, 다음 **Ctrl + I**합니다.  바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
     * 키를 눌러 **Ctrl +.** 트리거에 **빠른 작업 및 리팩터링** 메뉴와 선택 **인터페이스 추출** 미리 보기 창 팝업에서 합니다.
   * **마우스**
     * 선택 **편집 > 리팩터링 > 인터페이스를 추출할**합니다.
     * 선택 된 클래스의 이름을 마우스 오른쪽 단추로 클릭는 **빠른 작업 및 리팩터링** 메뉴와 선택 **인터페이스 추출** 미리 보기 창 팝업에서 합니다.

1. 에 **인터페이스 추출** 요청 정보를 입력 하는 대화 상자를 팝업으로 나타나는: ![인터페이스 추출](media/extractinterface_dialog.png)
   | 필드 | 설명 |
   | --- | --- |
   | **새 인터페이스 이름** | 만들 인터페이스의 이름입니다. 기본 I*ClassName*여기서 *ClassName* 위에서 선택한 클래스의 이름입니다. |
   | **새 파일 이름** | 인터페이스를 포함 될 축적할 수 있는 파일의 이름입니다. 인터페이스 이름의 기본 I 처럼*ClassName*여기서 *ClassName* 위에서 선택한 클래스의 이름입니다. |
   | **인터페이스를 구성할 공용 멤버 선택** | 항목 인터페이스로 추출입니다.  원하는 만큼 선택할 수 있습니다. |

1. **확인**을 클릭합니다.

   지정 된 이름의 파일에는 인터페이스를 즉시 생성 됩니다.  또한 선택한 클래스는 이제 해당 인터페이스를 구현 합니다.

   ![결과 클래스](media/extractinterface_class.png)
   ![결과 인터페이스](media/extractinterface_interface.png)

## <a name="see-also"></a>참고 항목
[리팩터링(Visual Basic)](../refactoring-vb.md)