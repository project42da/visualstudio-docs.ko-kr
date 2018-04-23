---
title: '방법: 활성화 및 편집을 사용 하지 않도록 설정 하 고, (C#, VB, + +)를 계속 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: 9070913d1106eb5e2ca04160ad95c6a6fd46f752
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-enable-and-disable-edit-and-continue-c-vb-c"></a>방법: 활성화 및 편집을 사용 하지 않도록 설정 하 고, (C#, VB, + +)를 계속 합니다.
편집 하며 계속 하기에서 사용 하거나 사용 하지 않도록 설정할 수는 **옵션** 디자인 타임에 대화 상자. 디버깅 중에는 이 설정을 변경할 수 없습니다.  
  
편집하며 계속하기는 디버그 빌드에서만 작동합니다. 네이티브 C++의 경우 편집하며 계속하기를 실행하려면 /INCREMENTAL 옵션을 사용해야 합니다. 이 c + +의 기능 요구 사항에 대 한 자세한 내용은 참조 [블로그 게시물](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/) 및 [편집 하며 계속 하기 (Visual c + +)](../debugger/edit-and-continue-visual-cpp.md)합니다.
  
#### <a name="to-enabledisable-edit-and-continue"></a>편집하며 계속하기를 사용하거나 사용하지 않도록 설정하려면  
  
1.  디버깅 세션에 있는 경우 디버깅을 중지 (**Shift + f 5를 눌러**).

2.  디버깅 옵션 페이지 열기 (**도구 > 옵션 > 디버깅**).
  
3.  선택 **일반**까지 아래로 스크롤하여 **편집 하며 계속 하기** 범주 (오른쪽 창).  
  
4.  를 사용 하려면 선택은 **사용 편집 하며 계속 하기** 확인란 합니다. 이 기능을 사용하지 않도록 설정하려면 이 확인란의 선택을 취소합니다.  
  
    > [!NOTE]
    >  IntelliTrace를 사용하도록 설정되어 있고 IntelliTrace 이벤트 및 호출 정보를 모두 수집하는 경우 편집하며 계속하기를 사용하지 않도록 설정됩니다. 자세한 내용은 참조 [IntelliTrace](../debugger/intellitrace.md)합니다.

5. (C + +) 를 사용 하려면 선택 **네이티브 편집 하며 계속 하기**합니다. 이 기능을 사용하지 않도록 설정하려면 이 확인란의 선택을 취소합니다.

6. (C + +) 네이티브 코드에 대 한 추가 옵션을 설정 합니다.

    - **변경 내용을 적용 (네이티브 전용)을 계속할 때**  
        Visual Studio에서는 중단 상태에서 프로세스를 계속하면 진행 중인 코드 변경 내용을 자동으로 컴파일하여 적용합니다. 을 선택 하지 디버그 메뉴에서 "코드 변경 내용 적용" 항목을 사용 하 여 변경 내용을 적용할 수 있습니다.  
  
    - **부실 코드 (네이티브 전용) 경으십시오**  
        부실 코드 경고를 가져옵니다. 
  
7.  **확인**을 클릭합니다.    
  
## <a name="see-also"></a>참고 항목  
 [편집하며 계속하기](../debugger/edit-and-continue.md)