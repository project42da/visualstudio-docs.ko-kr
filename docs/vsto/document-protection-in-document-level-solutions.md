---
title: "문서 수준 솔루션의 문서 보호 | Microsoft Docs"
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
  - "Office 문서[Visual Studio에서 Office 개발], 제한된 권한"
  - "권한[Visual Studio에서 Office 개발]"
  - "제한된 권한[Visual Studio에서 Office 개발]"
  - "통합 문서[Visual Studio에서 Office 개발], 제한된 권한"
ms.assetid: a25472ad-03f0-4804-9d19-e5ff71340d49
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 35
---
# 문서 수준 솔루션의 문서 보호
  문서 수준 프로젝트에서 Microsoft Office Word 및 Microsoft Office Excel의 보호 기능을 사용할 수 있습니다.  이러한 기능은 권한 없는 사용자가 문서의 보호된 부분을 변경할 수 없도록 합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Excel을 사용할 경우에는 디자이너에 통합 문서가 열려 있는 동안 보호 기능을 설정 및 해제할 수 있으며  Word를 사용할 경우에는 디자이너 밖에서만 보호 기능을 설정할 수 있습니다.  런타임에는 Word와 Excel 모두 프로그래밍 방식으로 보호 기능을 설정 또는 해제할 수 있습니다.  
  
 디자이너에 열려 있는 문서에 대해 문서 보호 기능을 설정한 경우 모든 컨트롤이 **도구 상자**에서 제거되거나 사용할 수 없게 되며 **데이터 소스** 창의 항목을 문서에 끌어 올 수 없습니다.  
  
## ServerDocument 및 보호된 문서  
 문서가 보호되면 문서 외부에서 데이터 캐시에 액세스할 수 없습니다.  <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스를 사용하여 보호된 문서에 캐시된 데이터를 검색 또는 조작하거나 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument> 클래스의 다른 함수를 사용할 수 없습니다.  
  
## 디자이너에서 Word 문서 보호  
 Visual Studio에 Word 문서나 서식 파일이 열려 있는 동안 여기에 보호 기능을 추가하면 디자이너에서 보호 기능 적용을 시작할 수 없습니다.  Visual Studio에서 열려 있는 문서는 디자인 모드이므로 보호 기능 적용을 시작하려면 먼저 실행 모드로 전환해야 합니다.  
  
 그러나 보호 기능이 설정된 기존의 Word 문서를 사용하는 프로젝트를 만들 경우에는 디자이너에 열려 있는 동안 문서가 보호됩니다.  문서의 보호된 부분을 편집할 수는 없지만 코드 편집기에서 코드를 작성하여 문서를 자동화할 수는 있습니다.  또한 Visual Studio에 문서가 열려 있을 때 보호 기능을 설정하면 프로젝트를 빌드할 수 없습니다.  
  
 문서가 디자이너에 열려 있는 동안에는 문서를 편집하고 프로젝트를 빌드할 수 있도록 보호 기능을 해제할 수 있습니다.  디버깅 중에는 디자이너에서 복사본의 보호 기능을 해제할 수 없습니다. 디버깅하는 동안 열리는 문서는 디자이너에 열린 문서와는 다른 별개의 복사본입니다. 출력 복사본은 Visual Basic의 경우 \\bin 디렉터리에 저장되고 C\#의 경우 \\bin\\debug 디렉터리에 저장됩니다.  
  
 Visual Studio에서 프로젝트를 닫고 프로젝트 디렉터리에 있는 문서의 복사본을 연 다음 보호 기능을 설정하면 디자이너에 열린 문서의 복사본에 대해 보호 기능을 설정할 수 있습니다.  
  
## 빌드 시 Word 문서 보호 기능 적용  
 Visual Studio를 사용하면 빌드 프로세스에서 Word 문서와 서식 파일에 보호 기능이 적용되기 시작하여 디버깅을 위해 문서가 열릴 때 보호 기능이 설정되며,  문서는 빈 암호로 보호됩니다.  
  
 예외를 발생시키거나 응용 프로그램 동작을 변경시킬 수 있는 문서의 <xref:Microsoft.Office.Tools.Word.Document.Startup> 이벤트에 코드가 있을 경우 빌드하는 동안 보호 기능이 설정되어 이 코드가 올바르게 디버깅될 수 있도록 합니다.  문서가 열린 후에 보호 기능을 설정하면 초기화 코드를 디버깅하거나 테스트할 수 없습니다.  
  
## 암호 설정  
 Visual Studio에서는 보호 기능을 자동으로 설정하지만 기본적으로 암호는 제공하지 않습니다.  암호를 사용하여 문서를 보호하려면 솔루션을 배포하기 전에 암호를 추가해야 합니다.  암호 설정을 추가하면 권한 있는 사용자가 문서에서 보호 기능을 제거할 수 있습니다. 암호가 없을 경우 보호 기능을 쉽게 제거할 수 없습니다.  암호 설정에 대한 자세한 내용은 특정 Office 응용 프로그램의 도움말을 참조하십시오.  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서 및 문서의 일부 보호](../vsto/how-to-programmatically-protect-documents-and-parts-of-documents.md)   
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)   
 [정보 권한 관리 및 관리 코드 확장 개요](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Office 문서의 암호 보호](../vsto/password-protection-on-office-documents.md)   
 [방법: 제한된 권한이 부여된 문서의 숨겨진 코드 실행 허용](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)  
  
  