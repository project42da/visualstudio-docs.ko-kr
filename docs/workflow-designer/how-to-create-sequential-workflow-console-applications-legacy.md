---
title: "방법: 순차 워크플로 콘솔 응용 프로그램 만들기(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "콘솔 응용 프로그램, 순차 워크플로"
  - "순차 워크플로, 콘솔 응용 프로그램"
  - "워크플로, 콘솔 응용 프로그램"
ms.assetid: 9f7be7fa-551f-42c6-a9bb-f5ae8ab83625
caps.latest.revision: 5
caps.handback.revision: 5
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 방법: 순차 워크플로 콘솔 응용 프로그램 만들기(레거시)
[!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]에서 제공하는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]를 사용하여 순차 워크플로 콘솔 응용 프로그램 프로젝트를 만들려면 다음 단계를 따릅니다.레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.  
  
### 순차 워크플로 콘솔 응용 프로그램을 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  **새 프로젝트** 창의 맨 위에 있는 드롭다운 목록에서 **.NET Framework 3.0** 옵션 또는 **.NET Framework 3.5** 옵션을 선택하여 레거시 디자이너에 액세스합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]의 기본 옵션은 **.NET Framework 4**입니다.이 옵션은 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)]을 대상으로 하는 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 응용 프로그램을 만드는 데 사용합니다.  
  
4.  **프로젝트 형식** 창의 **다른 언어** 아래에서 Visual C\# 프로젝트나 Visual Basic 프로젝트를 선택한 다음 **워크플로**를 선택합니다.  
  
5.  **템플릿** 창에서 **순차 워크플로 콘솔 응용 프로그램**을 선택합니다.  
  
6.  프로젝트를 식별하기 쉽도록 프로젝트를 설명하는 이름을 **이름** 상자에 입력합니다.  
  
7.  **위치** 상자에 프로젝트를 저장할 디렉터리를 입력하거나 **찾아보기**를 클릭하여 해당 디렉터리를 찾습니다.  
  
     Windows Forms 디자이너가 열리며 사용자가 만든 프로젝트의 Form1이 나타납니다.  
  
8.  **확인**을 클릭합니다.  
  
     워크플로 디자이너가 열리며 사용자가 만든 순차 워크플로의 워크플로 디자인 화면이 나타납니다.  
  
9. **도구 상자**에서 디자인 화면의 **활동을 놓을 위치** 지정 영역으로 활동을 끕니다.  
  
## 참고 항목  
 [레거시 워크플로 프로젝트 만들기](../workflow-designer/creating-legacy-workflow-projects.md)   
 [Developing Workflows](http://msdn.microsoft.com/ko-kr/557bcb1f-a7ab-49f6-8df7-2706b7001301)