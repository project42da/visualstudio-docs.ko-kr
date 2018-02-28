---
title: "방법: 편집 하며 계속 하기 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], about Edit and Continue
ms.assetid: 40e136d8-a08c-43bd-b313-fb821c55eb3c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: fe77428d1d9cfb5ff12554e87ec9afe15d6c86b8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-edit-and-continue-c"></a>방법: 편집하며 계속하기 사용(C#)
C#에서 편집하며 계속하기를 사용하면 디버깅하는 동안 중단 모드에서 코드를 변경할 수 있습니다. 디버깅 세션을 중지하고 다시 시작하지 않고도 변경 내용을 적용할 수 있습니다.  
  
 편집 하며 계속 하기는 자동으로 호출 중단 모드에 필요한 내용을 변경한 다음 디버거 실행을 선택할 때와 같은 명령을 **계속**, **단계**, 또는 **다음 문 설정**, 하거나 디버거 창에서 함수입니다.  
  
> [!NOTE]
>  최적화 된 코드, 혼합된 네이티브/관리 코드 또는 SQL Server 공용 언어 런타임 (CLR) 통합 코드를 디버깅할 때는 편집 하며 계속 하기가 지원 되지 않습니다. 기타 지원 되지 않는 시나리오에 대 한 자세한 내용은 참조 [지원 코드 변경 내용 (C# 및 Visual Basic)](../debugger/supported-code-changes-csharp.md)합니다. 않는다는 대화 상자 편집 하며 계속 하기는 지원 되지 않습니다 디버거에 표시 되는 경우 이러한 시나리오 중 하나에서 코드 변경 내용을 적용 하려고 합니다.  
  
### <a name="to-invoke-edit-and-continue-automatically"></a>편집을 호출 하 고 자동으로 계속  
  
1.  중단 모드에서 소스 코드를 변경을 합니다.  
  
2.  **디버그** 메뉴를 클릭 하 여 **계속**, **단계**, 또는 **다음 문 설정** 하거나 디버거 창에서 함수.  
  
     새 코드는 컴파일됩니다 하 고 새 코드와 함께 계속 디버깅 합니다. 일부 변경 내용이 편집 하며 계속 하기에서 지원 되지 않습니다. 자세한 내용은 참조 [지원 코드 변경 내용 (C# 및 Visual Basic)](../debugger/supported-code-changes-csharp.md)합니다.  
  
### <a name="to-enabledisable-edit-and-continue"></a>편집하며 계속하기를 사용하거나 사용하지 않도록 설정하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  에 **옵션** 대화 상자에서 **디버깅** 노드를 선택한 **편집 하며 계속 하기**합니다.  
  
3.  에 **옵션** 대화 상자 **편집 하며 계속 하기** 페이지를 선택 하거나 선택을 취소는 **사용 편집 하며 계속 하기** 확인란 합니다.  
  
     이 설정은 디버깅 세션을 다시 시작할 때 적용이 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [편집 하며 계속 하기 (Visual C#)](../debugger/edit-and-continue-visual-csharp.md)   
 [지원 되는 코드 변경 내용 (C# 및 Visual Basic)](../debugger/supported-code-changes-csharp.md)   