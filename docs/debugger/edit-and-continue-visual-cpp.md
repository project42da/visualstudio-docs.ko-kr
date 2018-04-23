---
title: 편집 하며 계속 (Visual c + +) | Microsoft Docs
ms.custom: ''
ms.date: 05/31/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C++]
- debugging [C++], Edit and Continue
- C/C++, Edit and Continue
ms.assetid: 1815251e-a877-433e-9e5e-69bd9ba254c7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 5d5195dd92e53a6657747758c03c87ee5463c1d5
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="edit-and-continue-visual-c"></a>Edit and Continue (Visual C++)
Visual C++ 프로젝트에서 편집하며 계속하기를 사용할 수 있습니다. 참조 [지원 코드 변경 내용 (c + +)](../debugger/supported-code-changes-cpp.md) 편집 하며 계속 하기의 제한 사항에 대 한 정보에 대 한 합니다.
  
Visual Studio 2015 업데이트 3 향상 된 기능에 대 한 자세한 내용은 참조 [c + + 편집 하며 계속 하기가 Visual Studio 2015 업데이트 3에서](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/)합니다.  
  
 [/Zo (최적화 된 디버깅 향상)](/cpp/build/reference/zo-enhance-optimized-debugging) Visual Studio 2013 업데이트 3에 도입 된 컴파일러 옵션 없이 컴파일된 이진에 대 한.pdb (기호) 파일에 추가 정보를 추가 [/Od (디버그 비활성화)) ](http://msdn.microsoft.com/library/aafb762y.aspx) 옵션입니다.  
  
 **/Zo** 편집 하며 계속 하기가 비활성화 됩니다. 참조 [하는 방법: 최적화 된 코드 디버깅](../debugger/how-to-debug-optimized-code.md)합니다.  
  
##  <a name="BKMK_Enable_or_disable_automatic_invocation_of_Edit_and_Continue"></a> 편집하며 계속하기 사용 또는 사용 안 함  
 현재 디버깅 세션 중에 적용하지 않으려는 코드 편집 내용이 있는 경우 편집하며 계속하기의 자동 호출을 사용하지 않도록 설정할 수 있습니다. 자동 편집하며 계속하기를 다시 사용하도록 설정할 수도 있습니다.

> [!IMPORTANT]
> 필요한 빌드 설정 및 기능 호환성에 대 한 기타 정보에 대 한 참조 [c + + 편집 하며 계속 하기에서 Visual Studio 2015 업데이트 3] (https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/합니다.
  
1.  디버깅 세션에 있는 경우 디버깅을 중지 (**Shift + f 5를 눌러**).

2. **도구** 메뉴에서 **옵션**을 선택합니다.
  
3.  에 **옵션** 대화 상자에서 **디버깅 > 일반**합니다.

4.  를 사용 하려면 선택 **사용 편집 하며 계속 하기**합니다. 을 사용 하지 않으려면 확인란의 선택을 취소 합니다.
  
5.  **편집하며 계속하기** 그룹에서 **네이티브 편집하며 계속하기 사용** 확인란을 선택하거나 선택 취소합니다.  
  
 이 설정을 변경하면 작업 중인 모든 프로젝트에 영향을 줍니다. 이 설정을 변경한 후 응용 프로그램을 다시 빌드할 필요는 없습니다. 응용 프로그램을 명령줄 이나 메이크파일에 빌드 하지만 Visual Studio 환경에서 디버깅을 사용할 수 있습니다 계속 편집 하며 계속 하기 설정 하는 경우는 **/ZI** 옵션입니다.  
  
##  <a name="BKMK_How_to_apply_code_changes_explicitly"></a> 코드 변경 내용을 명시적으로 적용하는 방법  
 Visual C++에서 편집하며 계속하기는 두 가지 방식으로 코드 변경 내용을 적용할 수 있습니다. 코드 변경 내용은 실행 명령을 선택할 때 암시적으로 적용하거나 **코드 변경 내용 적용** 명령을 사용하여 명시적으로 적용할 수 있습니다.  
  
 코드 변경 내용을 명시적으로 적용 하면 프로그램 상태를 유지 중단 모드-실행 되지 않습니다.  
  
-   코드 변경 내용을 명시적으로 적용하려면 **디버그** 메뉴에서 **코드 변경 내용 적용**을 선택합니다.  
  
##  <a name="BKMK_How_to_stop_code_changes"></a> 코드 변경을 중지하는 방법  
 편집하며 계속하기에서 코드 변경 내용을 적용하는 동안 작업을 중지할 수 있습니다.  
  
 코드 변경 내용의 적용을 중지하려면  
  
-   **디버그** 메뉴에서 **코드 변경 내용 적용 중지**를 선택합니다.  
  
 이 메뉴 항목은 코드 변경 내용을 적용하는 동안에만 표시됩니다.  
  
 이 옵션을 선택하면 코드 변경 내용이 커밋되지 않습니다.  
  
##  <a name="BKMK_How_to_reset_the_point_of_execution"></a> 실행 지점을 다시 설정하는 방법  
 일부 코드를 변경하면 편집하며 계속하기에서 변경 내용을 적용할 때 실행 위치가 새로운 위치로 이동할 수 있습니다. 편집하며 계속하기에서는 실행 위치를 가능한 한 정확하게 지정하지만 결과가 올바르지 않은 경우도 있습니다.  
  
 Visual C++에서는 실행 위치가 변경되면 이를 알리는 대화 상자가 표시됩니다. 디버깅을 계속하기 전에 실행 위치가 올바른지 확인해야 합니다. 실행 위치가 올바르지 않으면 **다음 문 설정** 명령을 사용합니다. 자세한 내용은 [다음에 실행할 문 설정](http://msdn.microsoft.com/library/y740d9d3.aspx#BKMK_Set_the_next_statement_to_execute)을 참조하세요.  
  
##  <a name="BKMK_How_to_work_with_stale_code"></a> 부실 코드 작업 방법  
 편집하며 계속하기로 실행 파일에 코드 변경 내용을 즉시 적용할 수 없는 경우도 있지만 디버깅을 계속할 경우 나중에 코드 변경 내용을 적용할 수 있습니다. 이는 현재 함수를 호출하는 함수를 편집하거나 호출 스택에 있는 함수에 64바이트 이상의 새 변수를 추가할 때 발생합니다.  
  
 이러한 경우 디버거는 변경 내용을 적용할 수 있을 때까지 원본 코드를 계속 실행합니다. 부실 코드는 별도의 소스 창에 `enc25.tmp`같은 제목을 사용하여 임시 소스 파일 창으로 표시됩니다. 편집된 소스는 원본 소스 창에 계속 표시됩니다. 부실 코드를 편집하려고 하면 경고 메시지가 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [지원되는 코드 변경(C++)](../debugger/supported-code-changes-cpp.md)