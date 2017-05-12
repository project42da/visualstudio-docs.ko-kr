---
title: "방법: 코드를 실행하지 않고 Office 솔루션 열기"
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
  - "어셈블리[Visual Studio에서 Office 개발], 건너뛰기"
  - "어셈블리 건너뛰기"
  - "문서[Visual Studio에서 Office 개발], 코드를 실행하지 않고 열기"
  - "Office 문서[Visual Studio에서 Office 개발], 코드를 실행하지 않고 열기"
  - "Office 솔루션[Visual Studio에서 Office 개발], 열기"
  - "Office 솔루션 열기"
  - "솔루션[Visual Studio에서 Office 개발], 열기"
ms.assetid: a853d91c-9fd6-421a-b3a2-956b6b494b96
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 23
---
# 방법: 코드를 실행하지 않고 Office 솔루션 열기
  관리 코드 확장을 통해 만든 Microsoft Office 솔루션은 최종 사용자의 Office 응용 프로그램 보안 설정이 높게 지정되어 있는 경우에도 실행됩니다.  이는 Microsoft Office가 아닌 Microsoft .NET Framework에서 .NET 어셈블리 코드 보안을 관리하기 때문입니다.  
  
 그러나 코드를 실행하지 않고 문서를 열어야 하는 경우가 있습니다.  예를 들어 문서가 열릴 때 실행되는 코드를 통해 문서 내용이 변경되지만 그 전에 문서 내용을 업데이트하고 싶은 경우가 있습니다.  또는 특정 정보가 포함된 문서를 다른 사람에게 보내려고 할 때 코드가 실행되어 문서 내용을 변경하는 일을 방지하고 싶은 경우가 있습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 어셈블리 코드를 실행하지 않고 관리 코드 확장이 포함된 문서 또는 통합 문서를 여는 방법은 몇 가지가 있습니다.  
  
### Shift 키를 사용하여 어셈블리를 무시하려면  
  
-   Shift 키를 누르면서 **파일** 메뉴에서 문서 및 통합 문서를 열면 문서가 열리는 동안 Word 및 Excel에서 초기화 이벤트가 발생하지 않습니다.  
  
    > [!NOTE]  
    >  **시작** 작업창에서는 Shift 키를 누르면서 문서 또는 통합 문서를 열더라도 코드가 무시되지 않습니다.  문서가 열린 후에는 Shift 키를 누르고 있어도 이벤트가 발생합니다.  
  
     이 방법은 코드 실행으로 인해 문서가 변경되는 것을 막으면서 문서를 열어 변경하려는 경우에 유용합니다.  
  
### 어셈블리 이름을 변경하거나 어셈블리를 제거하여 어셈블리를 무시하려면  
  
-   문서 또는 통합 문서에서 어셈블리를 찾지 못하도록 어셈블리 이름을 변경하거나 어셈블리를 제거합니다. 이 방법을 사용하려면 어셈블리가 저장되어 있는 컴퓨터에 대해 적절한 권한이 있어야 합니다.  이렇게 하면 Office 문서를 열 때마다 오류가 발생합니다.  
  
     여러 사람이 사용하는 솔루션에 이 방법을 사용하면 아무도 이 솔루션을 실행할 수 없습니다.  이 방법은 코드 또는 참조된 서버에 문제가 있어 모든 사용자가 실행하지 못하도록 하려는 경우에 유용합니다.  
  
## 참고 항목  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Office 솔루션의 응용 프로그램 및 배포 매니페스트](../vsto/application-and-deployment-manifests-in-office-solutions.md)  
  
  