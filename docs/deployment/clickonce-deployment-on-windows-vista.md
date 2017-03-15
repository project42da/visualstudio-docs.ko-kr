---
title: "Windows Vista의 ClickOnce 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, Windows"
  - "매니페스트 생성"
  - "UAC 매니페스트 생성"
  - "Windows, ClickOnce 배포"
ms.assetid: b21a0ebc-0ff6-4f49-8993-7d1ad3f8cac2
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Vista의 ClickOnce 배포
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio에서 Windows Vista의 UAC\(사용자 계정 컨트롤\)용으로 응용 프로그램을 빌드하면 일반적으로 응용 프로그램 실행 파일에 이진 XML 데이터로 인코딩되는 포함된 매니페스트가 생성됩니다.  ClickOnce 응용 프로그램과 등록이 필요 없는 COM 응용 프로그램에는 외부 매니페스트가 필요하므로 Visual Studio에서는 이러한 형식의 프로젝트에 대해 포함된 매니페스트 대신 UAC 데이터가 들어 있는 파일을 만듭니다.  기본적으로 Visual Studio에서는 app.manifest라는 파일의 정보를 사용하여 외부 UAC 매니페스트 정보를 생성하거나\(ClickOnce 배포와 등록이 필요 없는 COM 배포의 경우\) 응용 프로그램의 실행 파일에 해당 정보를 포함합니다\(그 밖의 모든 경우\).  Visual Studio에서는 매니페스트를 생성하기 위한 다음과 같은 옵션을 제공합니다.  
  
-   포함된 매니페스트를 사용합니다.  응용 프로그램의 실행 파일에 UAC 데이터를 포함하고 일반 사용자로 실행합니다.  
  
     ClickOnce를 사용하지 않는 경우 이것이 기본 설정입니다.  이 설정은 Visual Studio가 Windows Vista에서 작동하는 일반적인 방식, 즉 `AsInvoker`를 사용하여 내부 매니페스트와 외부 매니페스트를 생성하는 방식을 지원합니다.  
  
-   외부 매니페스트를 사용합니다.  app.manifest를 사용하여 외부 매니페스트를 생성합니다.  
  
     이렇게 하면 app.manifest의 정보를 사용하여 외부 매니페스트만 생성됩니다.  ClickOnce나 등록이 필요 없는 COM을 사용하여 응용 프로그램을 게시하면 Visual Studio에서는 프로젝트에 app.manifest를 추가하고 이 옵션을 추가합니다.  
  
-   매니페스트를 사용하지 않습니다.  매니페스트 없이 응용 프로그램을 만듭니다.  
  
     이 방법을 *가상화*라고도 합니다.  이전 버전의 Visual Studio에서 만들어진 기존 응용 프로그램과 호환되도록 하려면 이 옵션을 사용합니다.  
  
 새 속성은 프로젝트 디자이너의 **응용 프로그램** 페이지에서\(Visual C\# 프로젝트 경우만 해당\) 및 MSBuild 프로젝트 파일 형식에서 사용할 수 있습니다.  
  
 Visual Studio IDE에서 UAC 매니페스트 생성을 구성하는 방법은 프로젝트 형식\(Visual C\# 및 Visual Basic\)에 따라 달라집니다.  
  
 매니페스트 생성을 위한 Visual C\# 프로젝트 구성에 대한 자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지\(C\#\)](../ide/reference/application-page-project-designer-csharp.md)를 참조하십시오.  
  
 매니페스트 생성을 위한 Visual Basic 프로젝트 구성에 대한 자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](../ide/reference/application-page-project-designer-visual-basic.md)를 참조하십시오.  
  
## 참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [User Permissions and Visual Studio](http://msdn.microsoft.com/ko-kr/d5c55084-1e7b-4b61-b478-137db01c0fc0)   
 [프로젝트 디자이너, 응용 프로그램 페이지\(C\#\)](../ide/reference/application-page-project-designer-csharp.md)   
 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](../ide/reference/application-page-project-designer-visual-basic.md)