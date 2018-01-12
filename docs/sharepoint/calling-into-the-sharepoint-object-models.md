---
title: "SharePoint 개체 모델 호출 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, client object model
- SharePoint development in Visual Studio, server object model
- SharePoint commands [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, extensibility features
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: cbb1b8f573c6dd28280e30fd5602dff2dc30ae02
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="calling-into-the-sharepoint-object-models"></a>SharePoint 개체 모델 호출
  Visual Studio에서 SharePoint 도구의 확장을 만들 때 특정 작업을 수행 하는 SharePoint Api를 호출 해야 할 수 있습니다. 예를 들어 SharePoint 프로젝트용 사용자 지정 배포 단계를 만드는 경우 SharePoint 솔루션을 배포 하기 위해 작업 중 일부를 수행 하는 Api를 호출 해야 할 수 있습니다.  
  
 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]및 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 제공 SharePoint 도구 확장에서 사용할 수 있는 두 가지 개체 모델인: 서버 개체 모델과 클라이언트 개체 모델입니다. 각 개체 모델 SharePoint 도구 확장의 컨텍스트에서 장점과 단점에 있습니다.  
  
 SharePoint 개체 모델의 개요를 참조 하십시오. [프로그래밍 모델의 SharePoint 도구 확장의 개요](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)합니다.  
  
## <a name="using-the-client-object-model-in-extension-projects"></a>확장 프로젝트에서 클라이언트 개체 모델 사용  
 SharePoint 도구의 확장을 개발 하는 경우 다른 관리 되는 Api 집합이 마찬가지로 프로젝트에는 클라이언트 개체 모델을 사용할 수 있습니다. 프로젝트에 클라이언트 개체 모델에서 어셈블리에 대 한 참조를 추가할 수 있습니다 및 사용자 코드에서 직접 클라이언트 개체 모델 Api를 호출할 수 있습니다.  
  
 그러나 클라이언트 개체 모델에 SharePoint 도구 확장의 컨텍스트에서 두 가지 단점이 있습니다.  
  
-   클라이언트 개체 모델에는 서버 개체 모델의 하위 집합만을 제공합니다. 클라이언트 개체 모델에서 노출 되지 않는 SharePoint 기능을 사용 해야 할 경우 서버 개체 모델을 사용 해야 합니다.  
  
-   하지만 대부분의 경우에서 사용 되는 클라이언트 개체 모델을 사용 하 여 SharePoint 도구 확장에서 클라이언트 개체 모델에 대 한 호출 예상 대로 작동 하지 않는 시나리오가 발생할 수 있습니다. 클라이언트 개체 모델은 SharePoint 사이트에서 원격 서버 또는 팜에를 호출 하기 위한 클라이언트 응용 프로그램에 사용할 하도록 설계 되었습니다. Visual Studio에서 SharePoint 도구는 개발 컴퓨터에서 로컬 SharePoint 설치에만 작동 합니다. 따라서 SharePoint 도구 확장에서 클라이언트 개체 모델을 사용 하면 호출 SharePoint 사이트에 클라이언트 개체 모델에 사용할 설계 된 방식에 있지는 로컬 컴퓨터에 있습니다.  
  
 Visual Studio에서 SharePoint 도구 확장에서 클라이언트 개체 모델을 사용 하는 방법을 보여 주는 연습을 참조 하십시오. [연습: 서버 탐색기 확장의 SharePoint 클라이언트 개체 모델 호출](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)합니다.  
  
## <a name="using-the-server-object-model-in-extension-projects"></a>확장 프로젝트에서 서버 개체 모델 사용  
 서버 개체 모델에는 클라이언트 개체 모델의 상위 집합입니다. 서버 개체 모델을 사용 하는 경우에 모든 기능을 사용할 수 있습니다는 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 및 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] 프로그래밍 방식으로 노출 합니다.  
  
 SharePoint 도구 확장에서 서버 개체 모델 Api를 사용할 수 있지만 Api를 직접 호출할 수 없습니다. 서버 개체 모델은.NET Framework 3.5를 대상으로 하는 64 비트 프로세스를 통해서만 호출할 수 있습니다. 그러나 SharePoint 도구 확장 필요는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 32 비트 Visual Studio 프로세스에서 실행 됩니다. 따라서 SharePoint 도구 확장을에서 SharePoint 서버 개체 모델에서 어셈블리를 직접 참조 수 없습니다.  
  
 사용자 지정 SharePoint 도구 확장에서 서버 개체 모델을 사용 하려는 경우 만들어야 *SharePoint 명령* API를 호출 합니다. SharePoint 명령 서버 개체 모델을 직접 호출할 수 있는 보조 어셈블리를 정의 합니다. 확장 프로젝트에서 직접 호출할 있습니다 하지 SharePoint 명령 ExecuteCommand 메서드를 사용 하 여 프로그램 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> 개체입니다.  
  
 만들기 및 SharePoint 명령을 사용 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: SharePoint 명령 만들기](../sharepoint/how-to-create-a-sharepoint-command.md) 및 [하는 방법: SharePoint 명령 실행](../sharepoint/how-to-execute-a-sharepoint-command.md)합니다. SharePoint 명령을 배포 하는 방법에 대 한 정보를 참조 하십시오. [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
 SharePoint 명령 만들기 및 사용 하는 방법을 보여 주는 연습을 참조 하십시오. [연습: SharePoint 프로젝트용 사용자 지정 배포 단계 만들기](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md) 및 [연습: 디스플레이 웹 서버 탐색기 확장 파트](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)합니다.  
  
### <a name="understanding-how-sharepoint-commands-are-executed"></a>이해 어떻게 SharePoint 명령 실행  
 SharePoint 명령을 정의 하는 어셈블리가 vssphost4.exe 라는 64 비트 호스트 프로세스에서 로드 됩니다. SharePoint 명령은 SharePoint 도구 확장에서를 호출한 후 32 비트 Visual Studio 프로세스 (devenv.exe) 대신 vssphost4.exe 명령이 실행 됩니다. 레지스트리에서 값을 설정 하 여 SharePoint 명령 실행 방법의 일부 측면을 제어할 수 있습니다. 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장 디버깅](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: SharePoint 명령 만들기](../sharepoint/how-to-create-a-sharepoint-command.md)   
 [방법: SharePoint 명령 실행](../sharepoint/how-to-execute-a-sharepoint-command.md)   
 [SharePoint 도구 확장의 프로그래밍 모델 개요](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)  
  
  