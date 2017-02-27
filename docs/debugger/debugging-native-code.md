---
title: "네이티브 코드 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "C++"
helpviewer_keywords: 
  - "디버깅[C++], 네이티브 코드"
  - "디버깅[Visual Studio], 네이티브 코드"
  - "네이티브 코드 디버깅"
  - "네이티브 코드, 디버깅"
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
caps.latest.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 21
---
# 네이티브 코드 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 단원에서는 네이티브 응용 프로그램의 몇 가지 일반적인 디버깅 문제와 기술에 대해 설명합니다.  이 단원에서 설명하는 기술은 높은 수준의 기술입니다.  Visual Studio 디버거를 사용하는 방법은 [디버거 로드맵](../debugger/debugger-basics.md)을 참조하십시오.  
  
## 단원 내용  
 [방법: 최적화된 코드 디버깅](../debugger/how-to-debug-optimized-code.md)  
 최적화된 코드를 디버깅하는 방법, 특히, 최적화되지 않은 프로그램 버전을 디버깅해야 하는 이유, 디버그 및 릴리스 구성에 대한 기본 최적화 설정, 최적화된 코드에서만 발생하는 버그를 찾는 방법 등에 대해 설명합니다.  
  
 [DebugBreak 및 \_\_debugbreak](../debugger/debugbreak-and-debugbreak.md)  
 Win32 `DebugBreak` 함수에 대해 설명하고 Platform SDK의 참조 항목에 대한 링크를 제공합니다.  `__debugbreak` 내장 함수도 설명합니다.  
  
 [C\/C\+\+ 어설션](../debugger/c-cpp-assertions.md)  
 어설션 문, 어설션의 작동 방식, 어설션을 사용하여 수행할 수 있는 작업\(논리 오류 검색, 작업 결과 확인, 오류 조건 테스트\), `_DEBUG`와의 상호 작용, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 지원하는 어설션 형식 등에 대해 설명합니다.  
  
 [방법: 인라인 어셈블리 코드 디버깅](../debugger/how-to-debug-inline-assembly-code.md)  
 디스어셈블리 창에서 어셈블리 명령을 보는 방법과 레지스터 창에서 등록 내용을 보는 방법에 대해 간략히 설명하고 이러한 창을 소개하는 항목으로의 링크를 제공합니다.  
  
 [MFC 디버깅 기술](../debugger/mfc-debugging-techniques.md)  
 afxDebugBreak, TRACE 매크로, MFC의 메모리 누수 탐지, MFC 어설션, MFC 디버그 빌드 크기 줄이기 등의 MFC 프로그램에 대한 디버깅 기술을 소개합니다.  
  
 [CRT 디버깅 기술](../debugger/crt-debugging-techniques.md)  
 CRT 디버그 라이브러리 사용, 보고서 매크로 , malloc와 \_malloc\_dbg의 차이, 디버그 후크 함수 작성, CRT 디버그 힙 등의 C 런타임 라이브러리의 디버깅 기술에 대해 설명합니다.  
  
 [네이티브 코드 디버깅 FAQ](../debugger/debugging-native-code-faqs.md)  
 Visual C\+\+ 프로그램의 디버깅에 대한 질문과 대답을 제공합니다.  
  
 [COM 및 ActiveX 디버깅](../debugger/com-and-activex-debugging.md)  
 COM 및 ActiveX 디버깅에 사용할 수 있는 도구와 COM 및 ActiveX 응용 프로그램 디버깅에 대한 정보를 제공합니다.  
  
 [방법: 네이티브 DLL 디버깅](../debugger/how-to-debug-native-dlls.md)  
 네이티브 코드에서 DLL 디버깅 설정 방법에 대해 설명합니다.  
  
 [방법: 삽입한 코드 디버깅](../debugger/how-to-debug-injected-code.md)  
 특성을 사용하는 코드의 디버깅 방법에 대해 설명합니다.  여기에는 소스 주석을 표시하는 방법, 삽입한 코드를 보는 방법, 현재 실행 위치에서 디스어셈블리 코드를 보는 방법 등의 내용이 들어 있습니다.  
  
 [연습: 병렬 응용 프로그램 디버깅](../debugger/walkthrough-debugging-a-parallel-application.md)  
 **병렬 작업** 및 **병렬 스택** 도구 창을 사용하여 병렬 응용 프로그램을 디버깅하는 방법을 설명합니다.  
  
## 관련 단원  
 [Visual C\+\+ 프로젝트 형식](../debugger/debugging-preparation-visual-cpp-project-types.md)  
 Visual C\+\+ 프로젝트 템플릿으로 만든 기본 프로젝트 형식의 디버깅 방법에 대한 링크를 제공합니다.  
  
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)  
 자세한 디버깅 설명서 단원으로 연결되는 링크를 제공합니다.  이러한 정보에는 디버거의 새로운 기능, 설정 및 준비, 중단점, 예외 처리, 편집하며 계속하기, 관리 코드 디버깅, 네이티브 코드 디버깅, SQL 디버깅, 사용자 인터페이스 참조 등이 있습니다.  
  
## 참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [Visual Studio의 디버깅](../debugger/debugging-in-visual-studio.md)