---
title: "방법: 네이티브 런타임 검사 기능 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.runtime.errorchecks"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "/O 컴파일러 옵션, /RTC 옵션"
  - "/RTC 컴파일러 옵션[C++], /O 컴파일러 옵션"
  - "배열[Visual Studio], 디버깅"
  - "디버거, 네이티브 런타임 검사"
  - "디버거, 런타임 오류"
  - "배열 디버깅"
  - "네이티브 런타임 검사"
  - "O 컴파일러 옵션, /RTC 옵션"
  - "최적화된 빌드 옵션"
  - "RTC 컴파일러 옵션, /O 컴파일러 옵션"
  - "런타임 검사"
  - "런타임 검사, native"
  - "런타임 오류, 디버깅"
  - "런타임 오류, 오류 검사"
  - "runtime_checks pragma"
  - "스택 포인터"
  - "스택 포인터, 손상"
  - "스택, 포인터 손상"
  - "변수[디버거], 초기화되지 않은 지역 변수에 대한 종속성 catch"
  - "변수[디버거], 데이터 손실"
ms.assetid: dc7b2f1e-5ff6-42e0-89b3-dc9dead83ee1
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 네이티브 런타임 검사 기능 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual C\+\+에서는 네이티브 [runtime\_checks](/visual-cpp/preprocessor/runtime-checks)를 사용하여 다음과 같은 일반적인 런타임 오류를 catch할 수 있습니다.  
  
-   스택 포인터 손상  
  
-   지역 배열의 오버런  
  
-   스택 손상  
  
-   초기화되지 않은 지역 변수에 대한 종속성  
  
-   Short형 변수에 할당한 경우 발생한 데이터 손실  
  
 **\/RTC**를 최적화된 빌드\(**\/O**\)와 함께 사용하면 컴파일러 오류가 발생합니다. 최적화된 빌드에는 `runtime_checks` pragma를 사용해도 적용되지 않습니다.  
  
 런타임 검사가 활성화된 상태에서 프로그램을 디버깅하면 런타임 오류가 발생한 경우 기본적으로 프로그램을 중지하고 디버거를 중단합니다. 모든 런타임 검사의 기본 동작은 변경할 수 있습니다. 자세한 내용은 [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)를 참조하세요.  
  
 다음 절차에서는 디버그 빌드에서 네이티브 런타임 검사 기능을 활성화하는 방법과 네이티브 런타임 검사 동작을 수정하는 방법에 대해 설명합니다.  
  
 이 섹션의 다른 항목에서는 다음 내용에 대해 설명합니다.  
  
-   [C 런타임 라이브러리와 함께 런타임 검사 사용자 지정](../debugger/native-run-time-checks-customization.md)  
  
-   [C 런타임 라이브러리 없이 런타임 검사 사용](../debugger/using-run-time-checks-without-the-c-run-time-library.md)  
  
### 디버그 빌드에 네이티브 런타임 검사 기능을 사용하려면  
  
-   **\/RTC** 옵션을 사용하고 C 런타임 라이브러리의 디버그 버전\(예: \/MDd\)으로 연결합니다.  
  
### 네이티브 런타임 검사 동작을 수정하려면  
  
-   `runtime_checks` pragma를 사용합니다.  
  
## 참고 항목  
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)   
 [runtime\_checks](/visual-cpp/preprocessor/runtime-checks)   
 [런타임 오류 검사](/visual-cpp/c-runtime-library/run-time-error-checking)