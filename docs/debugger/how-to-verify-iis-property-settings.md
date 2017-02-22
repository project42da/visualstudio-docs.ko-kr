---
title: "방법: IIS 속성 설정 확인 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
helpviewer_keywords: 
  - "웹 응용 프로그램 디버깅, 문제 해결"
  - "IIS 관리 도구"
  - "인터넷 정보 서비스, 속성 설정"
  - "속성[디버거], IIS 관리 도구를 사용하여 설정"
  - "웹 응용 프로그램, 속성 설정"
ms.assetid: 9efc50bf-02fb-4750-9b3e-f03c38f10d8b
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: IIS 속성 설정 확인
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

IIS 관리 도구를 사용하여 웹 응용 프로그램의 속성을 설정할 수 있습니다.  이러한 속성이 제대로 설정되어 있어야 응용 프로그램이 실행되므로 일반적으로 문제를 해결하는 데는 이러한 설정을 확인하는 단계가 필요합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 웹 응용 프로그램에 대한 IIS 설정을 확인하려면  
  
1.  **시작** 메뉴에서 **프로그램**을 가리킨 다음 **관리 도구**를 클릭하여 **관리 도구** 창을 엽니다.  **관리 도구**가 **프로그램** 메뉴에 없으면 **제어판**에서 찾습니다.  
  
    -   Windows 2000에서는 **인터넷 서비스 관리자**를 선택합니다.  
  
    -   Windows XP에서는 **인터넷 정보 서비스**를 선택합니다.  
  
    -   Windows Server 2003에서는 **사용자 서버 관리**를 두 번 클릭합니다.  
  
         **사용자 서버 관리** 창이 열립니다.  **응용 프로그램 서버**에서 **이 응용 프로그램 서버 관리**를 클릭합니다.  
  
         **응용 프로그램 서버** 창이 열립니다.  왼쪽 창에서 **인터넷 정보 서비스\(IIS\) 관리자** 노드를 엽니다.  
  
2.  대화 상자에서 현재 컴퓨터의 트리 컨트롤 노드를 클릭합니다.  **웹 사이트** 노드를 클릭하고 웹 응용 프로그램의 노드를 선택합니다.  이 노드는 웹 사이트 노드\(**기본 웹 사이트** 노드의 형제 노드\)이거나 기존 웹 사이트 노드 아래에 있는 가상 디렉터리 노드일 수 있습니다.  
  
3.  웹 응용 프로그램을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **속성**을 클릭합니다.  
  
4.  웹 응용 프로그램에 대한 보안 설정을 확인합니다.  
  
    1.  웹 응용 프로그램의 **속성** 창에서 **디렉터리 보안** 탭을 클릭하고 **편집**을 클릭합니다.  
  
    2.  **인증 방법** 대화 상자에서 **익명 액세스 가능** 및 **Windows 통합 인증**이 선택되어 있지 않으면 이를 선택합니다.  
  
    3.  **확인**을 클릭하여 **인증 방법** 대화 상자를 닫습니다.  
  
5.  ATL 서버 응용 프로그램의 경우 DEBUG 동사가 ISAPI 확장과 관련이 있는지 여부를 확인합니다.  자세한 내용은 [How to: Associate DEBUG Verb with Extension](http://msdn.microsoft.com/ko-kr/50d261d3-4bd4-41c0-b44e-3591086f121e)을 참조하십시오.  
  
6.  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램의 경우, 해당 응용 프로그램의 가상 폴더에 **인터넷 정보 서비스\(IIS\) 관리자**, **인터넷 서비스 관리자** 또는 **인터넷 정보 서비스**에 설정된 응용 프로그램 이름이 있는지 확인합니다.  
  
    1.  웹 응용 프로그램 **속성** 창에서, 응용 프로그램이 가상 디렉터리에 있는 경우에는 **디렉터리** 탭을 선택하고 응용 프로그램이 웹 사이트에 있는 경우에는 **홈 디렉터리** 탭을 선택합니다.  
  
    2.  **로컬 경로**의 이름이 응용 프로그램이 실제로 배포된 디렉터리의 이름과 일치하는지 확인합니다.  
  
    3.  **응용 프로그램 설정**에서 응용 프로그램이 들어 있는 루트 디렉터리의 이름을 입력합니다.  
  
    4.  **확인**을 클릭하여 **속성** 대화 상자를 닫습니다.  
  
7.  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램의 경우, **ASP.NET** 탭을 클릭하여 올바른 버전의 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]이 지정되어 있는지 확인합니다.  
  
8.  **확인**을 클릭하여 **속성** 대화 상자를 닫습니다.  
  
9. **확인**을 클릭하여 **인터넷 정보 서비스\(IIS\) 관리자**, **인터넷 서비스 관리자** 또는 **인터넷 정보 서비스** 대화 상자를 닫습니다.  
  
## 참고 항목  
 [문제 해결](../debugger/debugging-web-applications-troubleshooting.md)