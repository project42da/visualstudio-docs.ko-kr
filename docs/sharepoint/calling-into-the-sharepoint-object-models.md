---
title: "Calling into the SharePoint Object Models"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "SharePoint development in Visual Studio, client object model"
  - "SharePoint development in Visual Studio, server object model"
  - "SharePoint commands [SharePoint development in Visual Studio]"
  - "SharePoint development in Visual Studio, extensibility features"
ms.assetid: 99934f9e-901e-464e-ac8c-22c6c86440f4
caps.latest.revision: 38
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 37
---
# Calling into the SharePoint Object Models
  Visual Studio SharePoint 도구에 대 한 확장을 만들 때 특정 작업을 수행 하려면 SharePoint Api를 호출 해야 합니다.  예를 들어 SharePoint 프로젝트에 대해 사용자 지정 배포 단계를 만드는 경우 솔루션을 배포하기 위해 SharePoint API를 호출하여 일부 작업을 수행해야 할 수도 있습니다.  
  
 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 및 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]에서는 SharePoint 도구 확장에 사용할 수 있는 두 가지 개체 모델인 서버 개체 모델과 클라이언트 개체 모델을 제공합니다.  SharePoint 도구 확장의 컨텍스트에서 각 개체 모델에 장단점이 있습니다.  
  
 SharePoint 개체 모델의 개요는 [Overview of the Programming Model of SharePoint Tools Extensions](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)를 참조하십시오.  
  
## 확장 프로젝트에서 클라이언트 개체 모델 사용  
 SharePoint 도구용 확장을 개발하는 경우 다른 관리되는 API 집합과 마찬가지로 프로젝트에 클라이언트 개체 모델을 사용할 수 있습니다.  클라이언트 개체 모델의 어셈블리에 대한 참조를 프로젝트에 추가하고 코드에서 직접 클라이언트 개체 모델의 API를 호출할 수 있습니다.  
  
 그러나 SharePoint 도구 확장의 컨텍스트에서 클라이언트 개체 모델에는 두 가지 단점이 있습니다.  
  
-   클라이언트 개체 모델에서는 서버 개체 모델의 하위 집합만 제공합니다.  클라이언트 개체 모델에 표시되지 않는 SharePoint 기능을 사용해야 하는 경우 서버 개체 모델을 사용해야 합니다.  
  
-   SharePoint 도구 확장에서 클라이언트 개체 모델을 사용해도 대부분의 경우 제대로 작동하지만 클라이언트 개체 모델 호출이 예상대로 작동하지 않는 시나리오가 발생할 수도 있습니다.  클라이언트 개체 모델은 클라이언트 응용 프로그램에서 원격 서버나 팜의 SharePoint 사이트를 호출하는 데 사용됩니다.  Visual Studio의 SharePoint 도구는 개발 컴퓨터의 로컬 SharePoint 설치에서만 작동합니다.  따라서 SharePoint 도구 확장에서 클라이언트 개체 모델을 사용하는 경우 로컬 컴퓨터의 로컬 SharePoint 사이트를 호출하는데 이는 클라이언트 개체 모델이 사용되는 방식이 아닙니다.  
  
 SharePoint 도구에서 Visual Studio 확장 클라이언트 개체 모델을 사용 하는 방법을 보여 주는 연습에 대 한 참조 하십시오. [Walkthrough: Calling into the SharePoint Client Object Model in a Server Explorer Extension](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md).  
  
## 확장 프로젝트에서 서버 개체 모델 사용  
 서버 개체 모델은 클라이언트 개체 모델의 상위 집합입니다.  서버 개체 모델을 사용하는 경우 [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] 및 [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)]에 표시되는 모든 기능을 프로그래밍 방식으로 사용할 수 있습니다.  
  
 SharePoint 도구 확장에서는 서버 개체 모델의 API를 사용할 수 있지만 직접 API를 호출할 수는 없습니다.  서버 개체 모델은 .NET Framework 3.5를 대상으로 하는 64비트 프로세스에서만 호출할 수 있습니다.  그러나 SharePoint 도구 확장을 사용하려면 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]가 필요하며 이는 32비트 Visual Studio 프로세스에서 실행됩니다.  이 때문에 SharePoint 도구 확장에서 SharePoint 서버 개체 모델의 어셈블리를 직접 참조할 수는 없습니다.  
  
 SharePoint 도구 확장에서 서버 개체 모델을 사용하려면 API를 호출하는 사용자 지정 *SharePoint 명령*을 만들어야 합니다.  보조 어셈블리에 서버 개체 모델을 직접 호출할 수 있는 SharePoint 명령을 정의합니다.  확장 프로젝트에서 <xref:Microsoft.VisualStudio.SharePoint.ISharePointConnection> 개체의 ExecuteCommand 메서드를 사용하여 SharePoint 명령을 직접 호출합니다.  
  
 SharePoint 명령을 만들고 사용하는 방법에 대한 자세한 내용은 [How to: Create a SharePoint Command](../sharepoint/how-to-create-a-sharepoint-command.md) 및 [How to: Execute a SharePoint Command](../sharepoint/how-to-execute-a-sharepoint-command.md)을 참조하십시오.  SharePoint 명령을 배포하는 방법에 대한 자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  
  
 SharePoint 명령을 만들고 사용하는 방법을 보여 주는 연습은 [Walkthrough: Creating a Custom Deployment Step for SharePoint Projects](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md) 및 [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)를 참조하십시오.  
  
### SharePoint 명령의 실행 방식 이해  
 SharePoint 명령을 정의하는 어셈블리는 vssphost4.exe라는 64비트 호스트 프로세스로 로드됩니다.  SharePoint 도구 확장에서 SharePoint 명령을 호출하면 32비트 Visual Studio 프로세스\(devenv.exe\) 대신 vssphost4.exe를 통해 명령이 실행됩니다.  레지스트리에 값을 설정하여 SharePoint 명령이 실행되는 방식의 몇 가지 측면을 제어할 수 있습니다.  자세한 내용은 [Debugging Extensions for the SharePoint Tools in Visual Studio](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md)을 참조하십시오.  
  
## 참고 항목  
 [How to: Create a SharePoint Command](../sharepoint/how-to-create-a-sharepoint-command.md)   
 [How to: Execute a SharePoint Command](../sharepoint/how-to-execute-a-sharepoint-command.md)   
 [Overview of the Programming Model of SharePoint Tools Extensions](../sharepoint/overview-of-the-programming-model-of-sharepoint-tools-extensions.md)  
  
  