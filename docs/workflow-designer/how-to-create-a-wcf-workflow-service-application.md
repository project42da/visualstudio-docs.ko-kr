---
title: "방법: WCF 워크플로 서비스 응용 프로그램 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
caps.latest.revision: 14
caps.handback.revision: 14
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 방법: WCF 워크플로 서비스 응용 프로그램 만들기
[!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] 워크플로 서비스 응용 프로그램은 프로세스 경계를 넘어 클라이언트와 메시지를 주고 받는 분산 통신 서비스입니다.서비스 측의 서비스 계약 구현은 .NET Framework 3.5의 레거시 워크플로 서비스와 비슷한 방식으로 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)]에서 워크플로 활동을 통해 선언적으로 이루어집니다.  
  
### WCF 워크플로 서비스 응용 프로그램을 만들려면  
  
1.  [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]을 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트...**를 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  **설치된 템플릿** 창에서 선택한 언어에 따라 **Visual C\#** 또는 **Visual Basic** 그룹의 **WCF** 또는 **워크플로**를 선택합니다.  
  
4.  중간 창에서 **WCF 워크플로 서비스 응용 프로그램**을 선택합니다.  
  
5.  프로젝트를 식별하기 쉽도록 프로젝트를 설명하는 이름을 **이름** 상자에 입력합니다.  
  
6.  **위치** 상자에 프로젝트를 저장할 디렉터리를 입력하거나 **찾아보기**를 클릭하여 해당 디렉터리를 찾습니다.  
  
7.  **솔루션** 상자에서 새 솔루션을 만든 다음 **확인**을 클릭합니다.  
  
    > [!NOTE]
    >  기존 솔루션에 워크플로 콘솔 응용 프로그램을 추가하려면 [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]에서 해당 솔루션을 열고 **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭한 다음 **추가**, **새 프로젝트...**를 차례로 선택하여 **새 프로젝트** 대화 상자를 엽니다.그런 다음 이 절차의 윗부분에 설명된 대로 진행합니다.  
  
8.  프로젝트 템플릿이 서비스 정의를 XAML로 만듭니다.<xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 활동 집합을 포함하는 <xref:System.Activities.Statements.Sequence> 활동이 표시된 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]의 디자인 뷰가 열립니다.  
  
## 참고 항목  
 [방법: 활동 만들기](../Topic/How%20to:%20Create%20an%20Activity.md)   
 [워크플로 프로젝트 만들기](../workflow-designer/creating-a-workflow-project.md)