---
title: "Visual C++에서 디버그 기능 활성화(/D_DEBUG) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "/D_DEBUG 컴파일러 옵션[C++]"
  - "_DEBUG 매크로"
  - "어설션, 디버그 기능 활성화"
  - "D_DEBUG 컴파일러 옵션"
  - "디버그 빌드, MFC"
  - "디버깅[C++], 디버그 기능 활성화"
  - "디버깅[MFC], 디버그 기능 활성화"
  - "MFC 라이브러리, 디버그 버전"
ms.assetid: 276e2254-7274-435e-ba4d-67fcef4f33bc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Visual C++에서 디버그 기능 활성화(/D_DEBUG)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)]에서 **\_DEBUG** 기호를 정의하고 프로그램을 컴파일하면 어설션과 같은 디버깅 기능을 사용할 수 있습니다.  **\_DEBUG**는 다음 두 가지 방법 중 하나를 사용하여 정의할 수 있습니다.  
  
-   소스 코드에서 **\#define \_DEBUG**를 지정합니다.  
  
-   **\/D\_DEBUG** 컴파일러 옵션을 지정합니다. Visual Studio에서 마법사를 사용하여 프로젝트를 만드는 경우 **\/D\_DEBUG**는 디버그 구성에 자동으로 정의됩니다.  
  
 **\_DEBUG**가 정의되면 컴파일러가 **\#ifdef \_DEBUG** 기호와 `#endif` 기호 사이의 코드 섹션을 컴파일합니다.  
  
 MFC 프로그램의 디버그 구성은 MFC 라이브러리의 디버그 버전과 링크해야 합니다.  **\_DEBUG** 및 **\_UNICODE**와 같이 정의한 기호에 따라 MFC 헤더 파일에서 링크할 MFC 라이브러리 버전이 결정됩니다.  자세한 내용은 [MFC 라이브러리 버전](/visual-cpp/mfc/mfc-library-versions)을 참조하십시오.  
  
## 참고 항목  
 [네이티브 코드 디버깅](../debugger/debugging-native-code.md)   
 [C\+\+ 디버그 구성에 대한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)