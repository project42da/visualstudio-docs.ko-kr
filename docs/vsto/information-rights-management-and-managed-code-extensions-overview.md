---
title: "정보 권한 관리 및 관리 코드 확장 개요"
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
  - "문서[Visual Studio에서 Office 개발], 제한된 권한"
  - "정보 권한 관리[Visual Studio에서 Office 개발]"
  - "IRM[Visual Studio에서 Office 개발]"
  - "Office 문서[Visual Studio에서 Office 개발], 제한된 권한"
  - "권한 관리[Visual Studio에서 Office 개발]"
  - "통합 문서[Visual Studio에서 Office 개발], 제한된 권한"
ms.assetid: 9728f5fe-9122-48e7-b0a3-9f5e0a16164f
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# 정보 권한 관리 및 관리 코드 확장 개요
  Microsoft Office Word 및 Microsoft Office Excel에는 권한이 없는 사용자가 중요한 정보를 보거나 변경하지 못하도록 하기 위한 IRM\(정보 권한 관리\)이라는 기능이 포함되어 있습니다.  정보 권한 관리 기능의 작동 방식에 대한 자세한 내용은 개별 Office 응용 프로그램의 도움말을 참조하십시오.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## 제한된 권한이 부여된 문서의 숨겨진 코드 실행  
 IRM을 사용하는 문서 또는 통합 문서가 솔루션에 들어 있으면 Word 및 Excel은 코드 실행을 허용하지 않습니다.  문서 작성자이거나 모든 권한 액세스가 부여된 경우 기본 설정을 변경하여 솔루션이 작동하도록 할 수 있습니다.  자세한 내용은 [방법: 제한된 권한이 부여된 문서의 숨겨진 코드 실행 허용](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)을 참조하십시오.  
  
 IRM을 사용하면 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument>를 사용하여 문서에 캐시된 데이터를 검색하거나 조작할 수 없습니다.  
  
## 관리 코드 확장을 사용하는 문서에 대한 권한을 제한하는 최종 사용자  
 솔루션의 문서 또는 통합 문서에 대한 모든 권한 액세스가 부여된 사용자는 IRM을 사용하여 권한을 제한할 수 있습니다.  예를 들어, 회계 부서의 최종 사용자가 데이터베이스의 데이터를 사용하여 워크시트를 자동으로 입력하는 솔루션을 사용하는 경우 해당 사용자는 자신의 부서에 속한 직원들에게만 변경 액세스 권한을 부여하고 다른 사용자들에게는 읽기 액세스 권한만 부여하려 할 수 있습니다.  이 사용자가 제한된 권한을 추가하면 기본적으로 워크시트의 숨겨진 코드가 실행되지 않으므로 워크시트에 데이터가 입력되지 않습니다.  
  
 이 문제를 해결하려면 문서 또는 통합 문서에 대한 모든 권한 액세스가 부여된 사용자가 기본 권한 설정을 변경하여 개체 모델에 프로그래밍 방식으로 액세스할 수 있도록 해야 합니다.  자세한 내용은 [방법: 제한된 권한이 부여된 문서의 숨겨진 코드 실행 허용](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)을 참조하십시오.  
  
## 참고 항목  
 [문서 수준 솔루션의 문서 보호](../vsto/document-protection-in-document-level-solutions.md)   
 [Office 문서의 암호 보호](../vsto/password-protection-on-office-documents.md)   
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)  
  
  