---
title: "C++ 프로젝트의 IntelliSense 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".ncb 파일"
  - "IntelliSense, C++ 프로젝트의 실패 문제 해결"
  - "ncb 파일"
  - "IntelliSense 문제 해결"
  - "Visual C++ 문제 해결, IntelliSense"
ms.assetid: 72e4eb39-66d3-403d-8da7-00ed288a1899
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# C++ 프로젝트의 IntelliSense 문제 해결
IntelliSense는 특정 조건에서 작동이 중지될 수 있습니다.  다음 단계를 사용하여 C\+\+ 프로젝트에 대해 IntelliSense가 작동하지 않는 이유를 판단할 수 있습니다.  
  
### C\+\+ 프로젝트의 IntelliSense 오류를 조사하려면  
  
1.  Visual C\+\+ 프로젝트에 컴파일 오류가 없는지 확인합니다.  
  
    1.  프로젝트가 메이크파일 프로젝트인 경우 [방법: 메이크파일 프로젝트에 IntelliSense 사용](../Topic/How%20to:%20Enable%20IntelliSense%20for%20Makefile%20Projects.md)을 참조하십시오.  
  
2.  포함 경로에 stdafx.h가 있는지 확인합니다.  Visual C\+\+ 프로젝트의 포함 경로에 대한 자세한 내용은 [\#include 지시문](/visual-cpp/preprocessor/hash-include-directive-c-cpp) 및 [\/I\(추가 포함 디렉터리\)](/visual-cpp/build/reference/i-additional-include-directories)를 참조하십시오.  
  
## IntelliSense 제한 사항  
 다음 상황에서는 IntelliSense가 C\+\+ 프로젝트에 대해 작동하지 않습니다.  
  
-   커서가 코드 주석 안에 있습니다.  
  
-   문자열 리터럴을 작성하고 있습니다.  
  
-   커서 위에 구문 오류가 나타납니다.  
  
-   솔루션은 관리 C\+\+용 구문 또는 이전의 Managed Extensions for C\+\+ 구문으로 구성됩니다.  
  
-   `#include` 지시문을 사용하여 헤더 파일을 여러 번 참조하고 `#define` 지시문을 통해 정의된 여러 가지 매크로 상태로 인해 해당 헤더 파일의 의미가 변경된 경우 IntelliSense가 완전히 지원되지 않습니다.  즉, 헤더 파일을 여러 번 포함하고 다양한 매크로 상태에 따라 헤더 사용법이 달라지는 경우 IntelliSense가 항상 작동하지는 않습니다.  
  
## 참고 항목  
 [Troubleshooting IntelliSense](http://msdn.microsoft.com/ko-kr/c1b3adb9-0d48-4770-a51e-392ed818c484)   
 [방법: 빌드할 프로젝트 출력 파일 구성](../Topic/How%20to:%20Organize%20Project%20Output%20Files%20for%20Builds.md)