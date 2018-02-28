---
title: "Visual c + +에서 디버그 기능 활성화 (-/d_debug) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /D_DEBUG compiler option [C++]
- debugging [C++], enabling debug features
- debugging [MFC], enabling debug features
- assertions, enabling debug features
- D_DEBUG compiler option
- MFC libraries, debug version
- debug builds, MFC
- _DEBUG macro
ms.assetid: 276e2254-7274-435e-ba4d-67fcef4f33bc
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f1067ee5b60b8a8a402c9612357f2d83b6da138
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-debug-features-in-visual-c-ddebug"></a>Visual C++에서 디버그 기능 활성화(/D_DEBUG)
[!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], 어설션을 기호를 사용 하 여 프로그램을 컴파일할 때 사용 하도록 설정 같은 디버깅 기능 **_DEBUG** 정의 합니다. 정의한 **_DEBUG** 두 가지 방법 중 하나에서:  
  
-   지정 **#define _DEBUG** 소스 코드에서 또는  
  
-   지정 된 **/D_DEBUG** 컴파일러 옵션입니다. (마법사를 사용 하 여 Visual Studio에서 프로젝트를 만들면 **/D_DEBUG** 디버그 구성에서 자동으로 정의 됩니다.)  
  
 때 **_DEBUG** 은 정의 컴파일러 컴파일합니다 둘러싸인 코드의 섹션 **#ifdef _DEBUG** 및 `#endif`합니다.  
  
 MFC 프로그램의 디버그 구성은 MFC 라이브러리의 디버그 버전과 링크해야 합니다. MFC 헤더 파일을 정의 하면와 같은 기호에 따라 올바른 버전의 MFC 라이브러리와 링크 하려면 결정 **_DEBUG** 및 **_UNICODE**합니다. 자세한 내용은 참조 [MFC 라이브러리 버전](/cpp/mfc/mfc-library-versions)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)   
 [C++ 디버그 구성에 대한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)