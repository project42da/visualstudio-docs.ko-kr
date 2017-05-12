---
title: "방법: 제한된 권한이 부여된 문서의 숨겨진 코드 실행 허용"
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
  - "코드[Visual Studio에서 Office 개발], 제한된 문서의 숨겨진 코드 실행"
  - "문서[Visual Studio에서 Office 개발], 제한된 권한"
  - "정보 권한 관리[Visual Studio에서 Office 개발]"
  - "IRM[Visual Studio에서 Office 개발]"
  - "Office 문서[Visual Studio에서 Office 개발], 제한된 권한"
  - "권한[Visual Studio에서 Office 개발]"
ms.assetid: d037eae5-cf83-4be0-85ba-05e9f7d570e1
caps.latest.revision: 27
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 26
---
# 방법: 제한된 권한이 부여된 문서의 숨겨진 코드 실행 허용
  Microsoft Office의 IRM\(정보 권한 관리\) 기능을 사용하여 문서 또는 통합 문서에 대한 사용 권한을 제한할 수 있습니다.  기본적으로 제한된 Microsoft Office Word 문서나 Microsoft Office Excel 통합 문서에 숨겨진 코드는 실행할 수 없습니다.  관리 코드 확장을 통해 개체 모델에 액세스하고 솔루션이 작동할 수 있도록 기본 설정을 변경할 수 있습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 권한 설정을 변경하려면 문서 또는 통합 문서를 만든 사람이거나 모든 권한 액세스가 부여된 사용자이어야 합니다.  
  
### 사용 권한이 제한된 문서의 숨겨진 코드를 실행할 수 있도록 하려면  
  
1.  Word 또는 Excel에서 문서나 통합 문서를 엽니다.  
  
2.  클릭의  **파일** 탭에서 가리키고  **준비**, 가리킵니다  **권한 제한**를 클릭 하 고 다음을 클릭  **액세스가 제한 된**.  
  
    > [!NOTE]  
    >  처음 사용할 때는 Windows Rights Management 클라이언트를 설치해야 한다는 메시지가 표시됩니다.  이 클라이언트를 설치한 후 앞의 단계를 반복해야 합니다.  
  
3.  **사용 권한** 대화 상자에서 **통합 문서에 대한 사용 권한 제한**을 선택한 다음 **기타 옵션**을 클릭합니다.  
  
4.  **사용자 추가 권한**에서 **프로그래밍 방법으로 내용에 액세스**를 선택합니다.  
  
 Word 또는 Excel에서 프로그래밍 방식으로 개체 모델에 액세스할 수 있습니다.  
  
## 참고 항목  
 [정보 권한 관리 및 관리 코드 확장 개요](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [문서 수준 솔루션의 문서 보호](../vsto/document-protection-in-document-level-solutions.md)   
 [Office 문서의 암호 보호](../vsto/password-protection-on-office-documents.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
  