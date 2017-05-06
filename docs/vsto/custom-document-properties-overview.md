---
title: "사용자 지정 문서 속성 개요"
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
  - "_AssemblyLocation 속성"
  - "_AssemblyName 속성"
  - "사용자 지정 문서 속성"
  - "문서 수준 사용자 지정[Visual Studio에서 Office 개발], 사용자 지정 속성"
  - "문서[Visual Studio에서 Office 개발], 사용자 지정 속성"
  - "Office 문서[Visual Studio에서 Office 개발], 사용자 지정 속성"
ms.assetid: 9a215904-b760-4a49-93e8-a1a708ce0526
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 35
---
# 사용자 지정 문서 속성 개요
  문서 수준 프로젝트를 빌드하면 프로젝트의 문서에 \_AssemblyLocation 및 \_AssemblyName이라는 두 가지 속성이 추가됩니다.  사용자가 문서를 열면 Microsoft Office 응용 프로그램에서는 이러한 사용자 지정 문서 속성을 확인합니다.  해당 속성이 문서에 있으면 응용 프로그램에서는 사용자 지정을 시작하는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]을 로드합니다.  자세한 내용은 [Visual Studio의 Office 솔루션 아키텍처](../vsto/architecture-of-office-solutions-in-visual-studio.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## \_AssemblyName  
 이 속성에는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]의 Office 솔루션 로더 구성 요소에 있는 인터페이스의 CLSID가 포함되어 있습니다.  CLSID 값은 4E3C66D5\-58D4\-491E\-A7D4\-64AF99AF6E8B이며  이 값은 변경하지 말아야 합니다.  
  
## \_AssemblyLocation  
 이 속성에는 사용자 지정의 배포 매니페스트에 대한 세부 정보를 제공하는 문자열이 들어 있습니다.  매니페스트에 대한 자세한 내용은 [Office 솔루션의 응용 프로그램 및 배포 매니페스트](../vsto/application-and-deployment-manifests-in-office-solutions.md)를 참조하십시오.  
  
 \_AssemblyLocation 속성 값의 형식은 솔루션이 배포되는 방식에 따라 달라집니다.  
  
-   솔루션이 웹 사이트, UNC 경로, CD 또는 USB 드라이브를 통해 설치되도록 게시된 경우 \_AssemblyLocation 속성의 형식은 *DeploymentManifestPath*|*SolutionID*입니다.  예를 들면 다음 문자열과 같습니다.  
  
     file:\/\/deployserver\/MyShare\/ExcelWorkbook1.vsto|74744e4b\-e4d6\-41eb\-84f7\-ad20346fe2d9  
  
-   Visual Studio에서 솔루션을 실행하거나 디버깅하는 경우 \_AssemblyLocation 속성의 형식은 *DeploymentManifestName*|*SolutionID*|vstolocal입니다.  예를 들면 다음 문자열과 같습니다.  
  
     ExcelWorkbook1.vsto|74744e4b\-e4d6\-41eb\-84f7\-ad20346fe2d9|vstolocal  
  
 *SolutionID*는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서 솔루션을 식별하는 데 사용하는 GUID입니다.  *SolutionID* 프로젝트를 빌드할 때 자동으로 생성 됩니다. **vstolocal** 알립니다의 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 어셈블리 문서와 같은 폴더에서 로드 되어야 함을.  
  
## 참고 항목  
 [Visual Studio의 Office 솔루션 아키텍처](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)   
 [Office 솔루션의 응용 프로그램 및 배포 매니페스트](../vsto/application-and-deployment-manifests-in-office-solutions.md)   
 [방법: ClickOnce를 사용하여 Office 솔루션 게시](http://msdn.microsoft.com/ko-kr/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)   
 [방법: 사용자 지정 문서 속성 만들기 및 수정](../vsto/how-to-create-and-modify-custom-document-properties.md)  
  
  