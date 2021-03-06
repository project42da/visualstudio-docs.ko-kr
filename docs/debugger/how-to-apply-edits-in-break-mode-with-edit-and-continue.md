---
title: '방법: 편집을 사용 하 여 중단 모드에서 편집 적용 하 고 계속 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [Visual Basic], applying edits in break mode
- break mode, applying code changes
- Edit and Continue, applying edits in break mode
- editing, break mode
- coding, editing in break mode
- code, editing in break mode
ms.assetid: 1eef7498-6a1f-4fba-8146-510adc6375c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f031598e0c8f290907e759bcfceac85c1b063f5f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>방법: 편집하며 계속하기를 사용하여 중단 모드에서 편집 적용
편집하며 계속하기를 사용하면 실행을 중지한 후에 다시 시작하지 않고도 중단 모드에서 코드를 편집한 다음 계속 진행할 수 있습니다.  
  
편집 하며 계속 하기를 사용 하 여 디버깅 하는 동안에 자세한 내용은 [지원 되는 코드 변경 (C# 및 Visual Basic](../debugger/supported-code-changes-csharp.md)]
  
### <a name="to-edit-code-in-break-mode"></a>중단 모드에서 코드를 편집하려면  
  
1.  다음 중 한 가지 방법으로 중단 모드를 시작합니다.  
  
    -   코드에서 중단점을 설정 합니다. 그런 다음 선택 **디버깅 시작** 에서 **디버그** 메뉴와 중단점 응용 프로그램에 대 한 대기입니다.  
  
         -또는-  
  
    -   디버깅을 시작 하 고 다음 선택 **모두 중단** 에서 **디버그** 메뉴.  
  
         -또는-  
  
    -   예외가 발생 하면 선택 **편집 사용** 에**예외 도우미**합니다.  
  
2.  원하는 및 지원 되는 코드 변경 내용을 확인 합니다.  
  
     자세한 내용은 참조 [지원 되는 코드 변경 (C# 및 Visual Basic](../debugger/supported-code-changes-csharp.md)합니다.  
  
    > [!NOTE]
    >  편집하며 계속하기에서 허용되지 않는 코드 변경 작업을 수행하면 자주색 물결선이 편집 내용 아래에 밑줄로 표시되고 해당 작업이 작업 목록에 나타납니다. 잘못된 코드 변경 내용을 취소하지 않으면 코드 실행을 계속 진행할 수 없습니다.  
  
3.  에 **디버그** 메뉴를 클릭 **계속** 실행을 다시 시작 합니다.  
  
     적용한 편집 내용이 프로젝트에 통합된 상태로 코드가 실행됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [지원 되는 코드 변경 내용 (C# 및 Visual Basic](../debugger/supported-code-changes-csharp.md)   
 [편집하며 계속하기(Visual Basic)](../debugger/edit-and-continue-visual-basic.md)