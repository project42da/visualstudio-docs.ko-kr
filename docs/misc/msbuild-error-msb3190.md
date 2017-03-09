---
title: "MSBuild 오류 MSB3190 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GenerateManifest.InvalidRequestedExecutionLevel"
helpviewer_keywords: 
  - "MSB3190"
ms.assetid: 45b45688-9345-45db-adc8-3e200f1c17eb
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3190
**MSB3190: ClickOnce는 요청 실행 수준 '\<level\>'을\(를\) 지원하지 않습니다.**  
  
 이 오류는 응용 프로그램의 포함된 UAC\(사용자 계정 컨트롤\) 매니페스트가 관리 자격 증명을 사용하여 ClickOnce 응용 프로그램을 실행하도록 지정하는 경우 Windows Vista를 실행하는 컴퓨터에서 발생합니다.  ClickOnce와 등록이 필요 없는 COM에는 현재 사용자로 응용 프로그램을 실행하도록 지정하는 외부 매니페스트가 필요합니다.  
  
 ClickOnce는 실행 수준 `requireAdministrator` 또는 `highestAvailable`을 허용하지 않습니다.  이러한 수준 중 하나를 지정하면 이 오류가 발생합니다.  ClickOnce에는 `asInvoker`가 필요하지만 여기에도 파일\/레지스트리 가상화를 지정하는 `<requestedExecutionLevel>` 노드가 허용되지 않습니다. 즉, 매니페스트가 생성되지 않습니다. 이는 이전 버전과의 호환성을 위한 것입니다.  
  
> [!NOTE]
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 이 오류를 해결하려면  
  
-   현재 사용자로 응용 프로그램을 실행하도록 지정하는 외부 UAC 매니페스트\(app.manifest\)를 생성합니다\(`asInvoker`\).  
  
     Visual C\# 프로젝트에서는 프로젝트 디자이너의 **응용 프로그램** 페이지로 이동하고 **매니페스트** 목록에서 **Properties\\app.manifest**을 클릭합니다.  자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지\(C\#\)](../ide/reference/application-page-project-designer-csharp.md)를 참조하십시오.  
  
     Visual Basic 프로젝트에서는 프로젝트 디자이너의 **응용 프로그램** 페이지로 이동하고 **UAC 설정 보기** 단추를 클릭합니다.  그러면 편집할 수 있도록 app.manifest가 열립니다.  매니페스트에서 다음 태그를 다음과 같이 편집합니다.  
  
    ```  
    <requestedExecutionLevel level="asInvoker" />  
    ```  
  
     자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](../ide/reference/application-page-project-designer-visual-basic.md)를 참조하십시오.  
  
-   UAC 매니페스트를 생성하고 실행 수준을 지정하는 방법에 대한 자세한 내용은 [Windows Vista의 ClickOnce 배포](../deployment/clickonce-deployment-on-windows-vista.md)를 참조하십시오.  
  
## 참고 항목  
 [프로젝트 디자이너, 응용 프로그램 페이지\(C\#\)](../ide/reference/application-page-project-designer-csharp.md)   
 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](../ide/reference/application-page-project-designer-visual-basic.md)   
 [Windows Vista의 ClickOnce 배포](../deployment/clickonce-deployment-on-windows-vista.md)