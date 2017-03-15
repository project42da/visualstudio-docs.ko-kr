---
title: "디버거 응용 프로그램 활성화 오류 진단 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.app_activation_failure"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 558ddc6d-0952-4617-84b8-0838717febcc
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "susanno"
manager: "douge"
---
# 디버거 응용 프로그램 활성화 오류 진단
Visual Studio 디버거에서 Windows 스토어 응용 프로그램을 시작하려고 하면 다음 오류 중 하나가 나타날 수 있습니다.  
  
 **8061**  
  
```  
Unable to activate Windows Store app 'AppName'. The ProcessName process started, but the activation request failed with error 'ErrorNumber'  
```  
  
 **8062**  
  
```  
Unable to activate Windows Store app 'AppName'. The activation request failed with error 'ErrorNumber'  
```  
  
## 이러한 오류를 진단하려면  
 이러한 오류를 해결하는 확실한 방법은 없습니다.  다음과 같은 방법을 사용하여 문제를 진단할 수 있습니다.  
  
### 이벤트 뷰어 사용  
  
1.  이벤트 뷰어 열기\(Windows 시작 메뉴에서 **이벤트 뷰어** 검색\)  이벤트 뷰어의 트리에서 **응용 프로그램 및 서비스 로그\\Microsoft\\Windows\\응용 프로그램** 폴더로 이동합니다.  
  
2.  이벤트 ID: 5900\-6000으로 뷰를 필터링합니다.  
  
3.  로그를 검사하고 무엇이 발생했는지 확인합니다.  
  
### 네이티브 디버거 사용  
 네이티브 디버거에서 실행되도록 프로젝트를 구성합니다.  
  
 Visual Studio에서 시작 프로젝트의 속성 페이지에 있는 **디버그**\(C\+\+ 및 JavaScript의 경우 **디버깅**\) 페이지에서 **디버거 형식**을 **네이티브 전용**으로 설정합니다.  
  
 출력 창을 확인하여 throw되는 예외를 확인합니다.  이러한 예외가 throw되면 디버거가 중지되도록 구성할 수도 있습니다.  
  
## 앱 라이선스 오류 수정  
 “이 앱은 라이선스 문제로 인해 시작할 수 없습니다.”라는 활성화 오류가 표시될 수 있습니다. 다음과 같은 해결 방법을 시도해 봅니다.  
  
-   **빌드** 메뉴에서 **솔루션 정리**를 선택한 다음 파일 탐색기에서 솔루션 폴더를 열고 **bin** 및 **obj** 폴더를 삭제합니다.  그런 다음 **빌드**, **솔루션 다시 빌드**를 선택합니다.  솔루션을 다시 빌드하면 필요한 폴더가 다시 만들어집니다.  
  
-   시작 화면에서 앱을 선택한 다음 앱 표시줄에서 제거를 선택합니다.  솔루션을 정리하고 다시 빌드합니다.  
  
-   관리자 권한으로 실행된 명령 프롬프트에서 Powershell 명령을 사용하여 개발자 라이선스를 제거하고 다시 설치합니다.  솔루션을 정리하고 다시 빌드합니다.  [명령 프롬프트에서 개발자 라이선스 가져오기](http://msdn.microsoft.com/library/windows/apps/Hh974578.aspx#getting_a_developer_license_at_a_command_prompt)를 참조하세요.