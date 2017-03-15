---
title: "프로젝트 디자이너, 디버그 페이지 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ProjectPropertiesDebug"
helpviewer_keywords: 
  - "프로젝트 디자이너, 디버그 페이지"
  - "프로젝트 디자이너의 디버그 페이지"
ms.assetid: ef11eae9-df96-4e20-aabd-2678ba317140
caps.latest.revision: 32
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 32
---
# 프로젝트 디자이너, 디버그 페이지
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!WARNING]
>  이 항목에서는 저장소 Windows 응용 프로그램에 적용 되지 않습니다.  참조 [디버그 세션 시작\(VB, C\#, C\+\+ 및 XAML\)](../../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md) Windows 개발 센터에서.  
  
 사용의  **디버그** 의 페이지는  **프로젝트 디자이너** 동작 Visual Basic 또는 C\# 프로젝트의 디버깅 속성을 설정할 수.  
  
 액세스 하는  **디버깅** 페이지에서 프로젝트 노드를 선택 합니다.  **솔루션 탐색기**.  에  **프로젝트** 메뉴를 선택  *ProjectName***속성**.   경우는  **프로젝트 디자이너** 나타나면 클릭은  **디버깅** 탭.  
  
## 구성 및 플랫폼  
 다음 옵션을 사용하여 표시하거나 수정할 구성과 플랫폼을 선택할 수 있습니다.  
  
 **구성**  
 표시하거나 수정할 구성 설정을 지정합니다.  설정 될 수 있습니다  **디버깅** \(기본\)  **릴리스**, 또는  **모든 구성**.  자세한 내용은 [Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e)을 참조하십시오.  
  
 **플랫폼**  
 표시하거나 수정할 플랫폼 설정을 지정합니다.  선택 항목을 포함할 수 있습니다  **Any CPU** \(기본\)  **x 64**, 및  **x86**.  자세한 내용은 [Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e)을 참조하십시오.  
  
## 시작 작업  
 **시작 작업**은 응용 프로그램을 디버깅할 때 시작되는 항목인 프로젝트, 사용자 지정 프로그램, URL 또는 없음을 나타냅니다.  기본적으로이 옵션 설정  **프로젝트 시작**.  **시작 작업** 설정의  **디버깅** 페이지의 값을 결정의 `StartAction` 속성.  
  
 **시작 프로젝트**  
 응용 프로그램을 디버깅할 때 실행 파일 \(Windows 응용 프로그램 및 콘솔 응용 프로그램 프로젝트의 경우\)을 시작할 수를 지정 하려면이 옵션을 선택 합니다.  이 옵션은 기본적으로 선택되어 있습니다.  
  
 **시작 외부 프로그램**  
 응용 프로그램을 디버깅할 때 특정 프로그램을 시작 하도록 지정 하려면이 옵션을 선택 합니다.  
  
 **다음 URL로 브라우저 시작**  
 응용 프로그램을 디버깅할 때 특정 URL에 액세스할 수를 지정 하려면이 옵션을 선택 합니다.  
  
## 시작 옵션  
 **명령줄 인수**  
 이 텍스트 상자에 디버깅에 사용할 명령줄 인수를 입력합니다.  
  
 **작업 디렉터리**  
 이 텍스트 상자에서 프로젝트를 시작할 디렉터리를 입력합니다.  또는 찾아보기 단추를 클릭 \(**...**\) 디렉터리를 선택 합니다.  
  
 **원격 컴퓨터 사용**  
 원격 컴퓨터에서 응용 프로그램을 디버깅 하려면이 확인란을 선택 하 고 텍스트 상자에 원격 컴퓨터의 경로 입력 합니다.  
  
## 디버거 활성화  
 **비관리 코드 디버깅 사용**  
 이 옵션은 네이티브 코드의 디버깅이 지원되는지 여부를 지정합니다.  COM 개체를 호출 하는 경우 또는 프로젝트를 호출 하는 네이티브 코드로 작성 된 사용자 지정 프로그램을 시작 하 고이 네이티브 코드를 디버깅 해야 하는 경우이 확인란을 선택 합니다.  비관리 코드의 디버깅을 비활성화하려면 이 확인란의 선택을 취소합니다.  이 확인란은 기본적으로 선택되어 있지 않습니다.  
  
 **SQL Server 디버깅 사용**  
 선택 하거나 사용 또는 SQL 프로시저에서 Visual Basic 응용 프로그램의 디버깅을 비활성화 하려면이 확인란의 선택을 취소 합니다.  이 확인란은 기본적으로 선택되어 있지 않습니다.  
  
 **Visual Studio 호스팅 프로세스 사용**  
 Visual Studio 호스팅 프로세스를 사용하려면 이 확인란을 선택합니다.  이 확인란은 기본적으로 선택되어 있습니다.  자세한 내용은 [호스팅 프로세스\(vshost.exe\)](../../ide/hosting-process-vshost-exe.md)을 참조하십시오.  
  
 보안 영역에서 디버깅 하려면이 옵션을 사용 하 고  **선택한 권한 집합으로이 응용 프로그램 디버깅** 에 [고급 보안 설정 대화 상자](../../ide/reference/advanced-security-settings-dialog-box.md).  
  
## 참고 항목  
 [Visual Studio의 디버깅](../../debugger/debugging-in-visual-studio.md)   
 [C\# 디버그 구성에 대한 프로젝트 설정](../../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Visual Basic 디버그 구성에 대한 프로젝트 설정](../../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Managing Debugging Properties](http://msdn.microsoft.com/ko-kr/92474d16-e7fe-4fac-9287-6bd6b3a7eb68)   
 [방법: 제한된 권한으로 ClickOnce 응용 프로그램 디버깅](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [방법: 구성 만들기 및 편집](../../ide/how-to-create-and-edit-configurations.md)