---
title: "정보 권한 관리 및 관리 코드 확장 개요 | Microsoft Docs"
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
- Information Rights Management [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- IRM [Office development in Visual Studio]
- documents [Office development in Visual Studio], restricted permissions
- rights management [Office development in Visual Studio]
- Office documents [Office development in Visual Studio, restricted permissions
ms.assetid: 9728f5fe-9122-48e7-b0a3-9f5e0a16164f
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 21431cd16407d61db6f981aad68d52906c2de1f1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="information-rights-management-and-managed-code-extensions-overview"></a>정보 권한 관리 및 관리 코드 확장명 개요
  Microsoft Office Word 및 Microsoft Office Excel를 보거나 중요 한 정보를 변경할 권한이 없는 사용자가을 방지 하는 기능 정보 권한 관리 (IRM)를 제공 합니다. 정보 권한 관리 작동 하는 방법에 대 한 자세한 내용은 특정 Office 응용 프로그램에서 도움말을 참조 합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="running-code-behind-documents-with-restricted-permissions"></a>사용 권한이 제한 된 문서의 숨겨진 코드 실행  
 솔루션에는 문서 또는 기본적으로는 IRM을 사용 하는 통합 있으면 Word 및 Excel 코드 실행 허용 하지 않습니다. 문서 작성자는 하거나 모든 권한을 갖습니다 솔루션 작동 되도록 기본값을 변경할 수 있습니다. 자세한 내용은 참조 [하는 방법: 제한 된 권한으로 실행 뒤에 있는 문서에 대 한 코드 허용](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)합니다.  
  
 IRM 사용을 금지 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument> 검색 또는 문서에서 캐시 된 데이터를 조작 합니다.  
  
## <a name="end-users-restricting-permissions-to-documents-that-use-managed-code-extensions"></a>최종 사용자가 관리 코드 확장을 사용 하는 문서에 대 한 사용 권한 제한  
 IRM 사용 솔루션의 문서 또는 통합 문서에 대 한 모든 권한이 있는 사용자 라면 누구나 사용 권한을 제한 수 있습니다. 예를 들어 회계 부서에서 최종 사용자는 데이터베이스의 데이터로 워크시트를 자동으로 채우려고 하는 솔루션을 사용할 경우 해당 사용자가 자신의 부서에는 사용자 에게만 액세스를 변경 하 고 다른 사용자에 대 한 읽기 액세스를 허용 할 수 있습니다. 사용자가 제한 된 권한을 추가할 때 기본적으로 워크시트의 숨김 코드를 실행할 수 없는 및 데이터로 워크시트 채워지지 않습니다.  
  
 문제를 해결 하려면 문서 또는 통합 문서에 대 한 모든 권한이 있는 사용자 개체 모델에 대 한 프로그래밍 방식의 액세스를 허용 하도록 기본 사용 권한 설정을 변경 해야 합니다. 자세한 내용은 참조 [하는 방법: 제한 된 권한으로 실행 뒤에 있는 문서에 대 한 코드 허용](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 수준 솔루션의 문서 보호](../vsto/document-protection-in-document-level-solutions.md)   
 [Office 문서의 암호 보호](../vsto/password-protection-on-office-documents.md)   
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)  
  
  