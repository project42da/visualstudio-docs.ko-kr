---
title: "방법: WCF 워크플로 서비스 응용 프로그램 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
caps.latest.revision: "14"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 8730b8f1611694ec7927b52fa4118cf3ca3801b7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-wcf-workflow-service-application"></a>방법: WCF 워크플로 서비스 응용 프로그램 만들기
[!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] 워크플로 서비스 응용 프로그램은 프로세스 경계를 넘어 클라이언트와 메시지를 주고 받는 분산 통신 서비스입니다. 서비스 측의 서비스 계약 구현은 .NET Framework 3.5의 레거시 워크플로 서비스와 비슷한 방식으로 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)]에서 워크플로 활동을 통해 선언적으로 이루어집니다.  
  
### <a name="to-create-a-wcf-workflow-service-application"></a>WCF 워크플로 서비스 응용 프로그램을 만들려면  
  
1.  [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]를 시작합니다.  
  
2.  에 **파일** 메뉴에서 **새로**를 선택한 후 **프로젝트...** .  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  에 **설치 된 템플릿** 창 선택 **WCF** 또는 **워크플로** 중 하 나와 **Visual C#** 또는 **VisualBasic** 선택한 언어에 따라 그룹화 합니다.  
  
4.  가운데 창에서 선택 **WCF 워크플로 서비스 응용 프로그램**합니다.  
  
5.  에 **이름** 상자에 프로젝트를 식별 하기 쉽도록 프로젝트를 설명 하는 이름을 입력 합니다.  
  
6.  에 **위치** 상자에서 프로젝트를 저장 하거나 클릭 하려는 디렉터리를 입력 **찾아보기** 찾습니다.  
  
7.  에 **솔루션** 상자에서 새 솔루션 만들기 또는 클릭 한 다음 선택 **확인**합니다.  
  
    > [!NOTE]
    >  기존 솔루션에 워크플로 콘솔 응용 프로그램을 추가 하려는 경우에서 해당 솔루션을 열고 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], 솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**을 선택 하 고 **추가**, 다음  **새 프로젝트...**  열려는 **새 프로젝트** 대화 상자. 그런 다음 이 절차의 윗부분에 설명된 대로 진행합니다.  
  
8.  프로젝트 템플릿이 서비스 정의를 XAML로 만듭니다. [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] 및 <xref:System.Activities.Statements.Sequence> 활동 집합을 포함하는 <xref:System.ServiceModel.Activities.Receive> 활동이 표시된 <xref:System.ServiceModel.Activities.SendReply>의 디자인 뷰가 열립니다.   
  
## <a name="see-also"></a>참고 항목  
 [방법: 활동 만들기](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)   
 [워크플로 프로젝트 만들기](../workflow-designer/creating-a-workflow-project.md)