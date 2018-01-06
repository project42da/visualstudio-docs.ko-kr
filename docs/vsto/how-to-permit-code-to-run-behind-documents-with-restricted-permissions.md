---
title: "방법: 코드 실행 권한이 제한 된 문서 뒤 허용 | Microsoft Docs"
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
- permissions [Office development in Visual Studio]
- IRM [Office development in Visual Studio]
- code [Office development in Visual Studio], running behind restricted documents
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
ms.assetid: d037eae5-cf83-4be0-85ba-05e9f7d570e1
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2f3ff7f7bb76962e22705fc5c0d42fdf7568ff97
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>방법: 제한된 권한이 부여된 문서의 숨겨진 코드 실행 허용
  문서 또는 통합 문서에 사용 권한을 제한 하도록 Microsoft Office의 IRM 정보 권한 관리 () 기능을 사용할 수 있습니다. 코드 숨김 제한 된 Microsoft Office Word 문서 또는 Microsoft Office Excel 통합 문서는 기본적으로 실행 되도록 허용 되지 않습니다. 해당 솔루션은 작동 하 고 관리 코드 확장명 개체 모델에 액세스할 수 있도록 기본값을 변경할 수 있습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 문서 또는 통합 문서를 만든 사람 이거나 사용 권한 설정을 변경할 수에 대 한 모든 권한이 있어야 합니다.  
  
### <a name="to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>문서 뒤에서 제한 된 권한으로 실행 하는 코드를 허용 하려면  
  
1.  Word 또는 Excel에서 문서 또는 통합 문서를 엽니다.  
  
2.  클릭는 **파일** 탭, 가리킨 **준비**, 가리킨 **권한 제한**, 클릭 하 고 **제한 된 액세스**합니다.  
  
    > [!NOTE]  
    >  처음 사용할 때 Windows Rights Management 클라이언트를 설치 하 라는 메시지가 표시 됩니다. 클라이언트를 설치한 후 단계를 반복 해야 합니다.  
  
3.  에 **권한** 대화 상자에서 **이 문서에 대 한 사용 권한을 제한**, 클릭 하 고 **기타 옵션**합니다.  
  
4.  아래 **사용자에 대 한 추가 사용 권한을**선택, **콘텐츠를 프로그래밍 방식으로 액세스**합니다.  
  
 Word 또는 Excel 개체 모델에 대 한 프로그래밍 방식의 액세스를 허용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [정보 권한 관리 및 관리 코드 확장 개요](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [문서 수준 솔루션의 문서 보호](../vsto/document-protection-in-document-level-solutions.md)   
 [Office 문서의 암호 보호](../vsto/password-protection-on-office-documents.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
  