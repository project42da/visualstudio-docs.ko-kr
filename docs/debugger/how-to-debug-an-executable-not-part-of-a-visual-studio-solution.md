---
title: "방법: Visual Studio 솔루션의 일부가 아닌 실행 파일 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
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
  - "디버깅[Visual Studio], 실행 파일"
  - "실행 파일, 프로젝트 외부에서의 디버깅"
  - "실행 파일, 가져오기"
ms.assetid: 3ea176e8-1ce5-42c4-b7a2-abe3a2765033
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: Visual Studio 솔루션의 일부가 아닌 실행 파일 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

때로는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트에 포함되지 않은 실행 파일을 디버깅해야 하는 경우가 있습니다.  예를 들어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 외부에서 만든 실행 파일이나 다른 사용자로부터 받은 실행 파일이 이러한 경우입니다.  
  
 이러한 문제는 일반적으로 Visual Studio 외부에서 실행 파일을 시작하고 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디버거를 사용하여 이 파일에 연결하는 방법으로 해결합니다.  자세한 내용은[실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)을 참조하십시오.  
  
 응용 프로그램에 연결하려면 몇 가지 단계를 직접 수행해야 하기 때문에 몇 초 정도 걸립니다.  이러한 약간의 시간 지연으로 인해, 시작할 때 발생하는 문제를 디버깅하려는 경우에는 연결 방법을 사용할 수 없습니다.  또한, 사용자가 입력할 때까지 대기하지 않고 바로 종료되는 프로그램을 디버깅하는 경우에는 프로그램에 연결할 시간이 없을 수도 있습니다.  [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)]가 설치되어 있으면 이러한 프로그램에 대한 EXE 프로젝트를 만들 수 있습니다.  
  
### 기존 실행 파일에 대한 EXE 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **열기**를 클릭하고 **프로젝트**를 선택합니다.  
  
2.  **프로젝트 열기** 대화 상자에서 **파일 이름** 상자 옆의 드롭다운 목록을 클릭하고 **모든 프로젝트 파일**을 선택합니다.  
  
3.  실행 파일을 찾은 다음 **확인**을 클릭합니다.  
  
     실행 파일이 포함된 임시 솔루션이 생성됩니다.  
  
### 실행 파일을 Visual Studio 솔루션으로 가져오려면  
  
1.  **파일** 메뉴에서 **프로젝트 추가**를 가리킨 다음 **기존 프로젝트**를 클릭합니다.  
  
2.  **기존 프로젝트 추가** 대화 상자에서 **파일 이름** 상자 옆의 드롭다운 목록을 클릭하고 **모든 프로젝트 파일**을 선택합니다.  
  
3.  실행 파일을 찾아 선택합니다.  
  
4.  **확인**을 클릭합니다.  
  
5.  **디버그** 메뉴에서 **시작**과 같은 실행 명령을 선택하여 실행 파일을 시작합니다.  
  
    > [!NOTE]
    >  모든 프로그래밍 언어가 EXE 프로젝트를 지원하는 것은 아닙니다.  이 기능이 필요하면 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)]를 설치합니다.  
  
     디버깅하는 실행 파일에 대한 소스 코드가 없으면, 실행 중인 실행 파일에 연결하는지 실행 파일을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션에 추가하는지 여부에 상관없이 디버깅 기능이 제한됩니다.  실행 파일이 디버그 정보 없이 호환 형식으로 빌드된 경우에는 더욱 많은 기능이 제한됩니다.  따라서, 소스 코드가 있는 경우에는 소스 코드를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]로 가져온 다음 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 실행 파일의 디버그 빌드를 만드는 것이 좋습니다.  
  
## 참고 항목  
 [디버그 설정 및 준비](../debugger/debugger-settings-and-preparation.md)   
 [디버거 보안](../debugger/debugger-security.md)   
 [DBG Files](http://msdn.microsoft.com/ko-kr/91e449e9-8b65-4123-960f-2107cd1f1cfd)