---
title: "사용자 지정 문서 속성 개요 | Microsoft Docs"
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
- documents [Office development in Visual Studio], custom properties
- custom document properties
- document-level customizations [Office development in Visual Studio], custom properties
- Office documents [Office development in Visual Studio], custom properties
- _AssemblyLocation property
- _AssemblyName property
ms.assetid: 9a215904-b760-4a49-93e8-a1a708ce0526
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ee19d6fd6bd84f344a205b0e508abbede63cdebb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="custom-document-properties-overview"></a>Custom Document Properties Overview
  문서 수준 프로젝트를 빌드할 때 Visual Studio 프로젝트의 문서에 추가 두 개의 사용자 지정 속성: _AssemblyLocation 및 _AssemblyName 합니다. 사용자가 문서를 Microsoft Office 응용 프로그램 이러한 사용자 지정 문서 속성을 확인 합니다. 문서에 있는 경우 로드 하 고는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], 시작 되는 사용자 지정 합니다. 자세한 내용은 참조 [Visual Studio 아키텍처의 Office 솔루션](../vsto/architecture-of-office-solutions-in-visual-studio.md)합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="assemblyname"></a>_AssemblyName  
 이 속성의 Office 솔루션 로더 구성 요소에서 인터페이스의 CLSID가 포함 된 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다. CLSID 기간은 4E3C66D5-58 D 4-491E-A7D4-64AF99AF6E8B입니다. 이 값을 변경해 서는 안 됩니다.  
  
## <a name="assemblylocation"></a>_AssemblyLocation  
 이 속성에 대 한 사용자 지정 배포 매니페스트에 대 한 세부 정보를 제공 하는 문자열을 포함 합니다. 매니페스트에 대 한 자세한 내용은 참조 하십시오. [응용 프로그램 및 Office 솔루션의 배포 매니페스트](../vsto/application-and-deployment-manifests-in-office-solutions.md)합니다.  
  
 The_AssemblyLocation 속성 값에는 솔루션은 배포 하는 방법에 따라 서로 다른 형식으로 가질 수 있습니다.  
  
-   솔루션에 웹 사이트, UNC 경로 또는 CD 또는 USB 드라이브에서 설치 게시 _AssemblyLocation 속성의 형식이 *DeploymentManifestPath*|*SolutionID*합니다. 다음 문자열은 예입니다.  
  
     file://deployserver/MyShare/ExcelWorkbook1.vsto | 74744e4b-e4d6-41eb-84f7-ad20346fe2d9  
  
-   실행 하거나 Visual Studio에서 솔루션을 디버깅 하는 _AssemblyLocation 속성의 형식이 *DeploymentManifestName*|*SolutionID*| vstolocal 합니다. 다음 문자열은 예입니다.  
  
     ExcelWorkbook1.vsto|74744e4b-e4d6-41eb-84f7-ad20346fe2d9 | vstolocal  
  
 *SolutionID* 는 guid는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 사용 하 여 솔루션을 식별 합니다. *SolutionID* 프로젝트를 빌드할 때 자동으로 생성 됩니다. **vstolocal** 에 알립니다는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 문서와 동일한 폴더의 어셈블리가 로드 되어 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 Office 솔루션의 아키텍처](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)   
 [응용 프로그램 및 Office 솔루션의 배포 매니페스트](../vsto/application-and-deployment-manifests-in-office-solutions.md)   
 [방법: ClickOnce를 사용 하 여 Office 솔루션 게시](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)   
 [방법: 사용자 지정 문서 속성 만들기 및 수정](../vsto/how-to-create-and-modify-custom-document-properties.md)  
  
  