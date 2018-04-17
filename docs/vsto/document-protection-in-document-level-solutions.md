---
title: 문서 보호에서 문서 수준 솔루션 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- restricted permissions [Office development in Visual Studio]
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio], restricted permissions
- documents [Office development in Visual Studio], restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 546a74179b8bdf52541d771809426b5e4aec3e45
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="document-protection-in-document-level-solutions"></a>문서 수준 솔루션의 문서 보호
  문서 수준 프로젝트에서 Microsoft Office Word 및 Microsoft Office Excel의 보호 기능을 사용할 수 있습니다. 이러한 기능 권한이 없는 사용자가 문서 보호 된 부분을 변경 하지 못하도록 차단 합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Excel을 사용 하 여 설정할 수 있습니다 보호 켜기 및 끄기 통합 문서를 디자이너에에서 열려 있는 동안. Word를 사용 하 여 보호 디자이너 외에 설정할 수 있습니다. 런타임에 Word 및 Excel 모두에 대해 프로그래밍 방식으로 보호를 사용 하지 않도록 설정 하거나 설정할 수 있습니다.  
  
 문서 보호 디자이너에서 열려 있는 문서에서 활성화 된 모든 컨트롤에서 제거 됩니다는 **도구 상자** 없게 되며 또는에서 모든 항목을 끌 수 없습니다는 **데이터 소스** 문서 창입니다.  
  
## <a name="serverdocument-and-protected-documents"></a>ServerDocument 및 보호 된 문서  
 문서 보호 되는 경우 문서 외부에서 데이터 캐시에 액세스할 수 없습니다. 사용할 수 없습니다는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 나 다른 메서드를 사용 하는 검색 또는 보호 된 문서에 캐시 된 데이터를 조작 클래스는 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument> 클래스입니다.  
  
## <a name="word-document-protection-in-the-designer"></a>디자이너에서 Word 문서 보호  
 보호 기능 Word 문서 또는 서식 파일에 추가 하면 Visual Studio에서 열려 있는 동안 디자이너에서 보호 기능이 적용을 시작할 수 없습니다. Visual Studio에서 열려는 동안에 실행 해야 모드 문서 보호를 적용 하기 전에 디자인 모드 문서가입니다.  
  
 그러나 보호가 설정 된 기존 Word 문서를 사용 하는 프로젝트를 만들면 문서 디자이너에 열려 있는 동안 보호 됩니다. 문서의 보호 된 부분을 편집할 수는 없지만 있습니다 코드 작성할 수는 코드 편집기에 문서를 자동화 하 합니다. 또한 문서가 Visual Studio에서 열려 있는 동안 보호가 설정 된 경우 프로젝트를 빌드할 수 없습니다.  
  
 문서를 편집 하 고 프로젝트를 빌드할 수 있도록 문서가 디자이너에에서 열려 있는 동안 보호를 해제할 수 있습니다. 디버깅 하는; 디자이너에서 복사에 대 한 보호 해제할 수 없습니다. 디버깅 하는 동안 열려 있는 문서에는 하나는 디자이너에에서 열려 (출력 복사본 \bin 디렉터리에 Visual basic 및 C#의 \bin\debug 디렉터리에 저장 됨)에서 별도 복사본입니다.  
  
 Visual Studio에서 프로젝트를 닫으면 프로젝트 디렉터리에 있는 문서 복사본 연 보호를 설정 하 여 디자이너에서 열려 있는 문서 복사본에 대해 보호를 사용할 수 있습니다.  
  
## <a name="enforcing-word-document-protection-on-build"></a>빌드에 적용 하면 Word 문서 보호  
 Visual Studio는 디버깅에 대 한 문서를 열 때 보호를 사용할 수 있도록 Word 문서 및 서식 파일에 대 한 빌드 프로세스 보호 기능이 적용을 시작 합니다. 문서는 빈 암호로 보호 됩니다.  
  
 보호 작업을 빌드하는 동안 하므로 하는 경우에 사용할 수 문서에 코드가 있으면 <xref:Microsoft.Office.Tools.Word.Document.Startup> 예외가 발생 하거나 응용 프로그램의 동작을 변경할 수 있는 이벤트를이 코드 올바르게 디버깅 될 수 있습니다. 문서를 연 후 보호를 사용 하면 초기화 코드를 디버깅 또는 테스트할 수 없습니다.  
  
## <a name="setting-the-password"></a>암호 설정  
 Visual Studio는 자동으로 보호를 사용 하도록 설정 되지만 암호를 사용 하지는 기본적으로 제공 합니다. 암호를 가진 문서 보호 하려는 경우 솔루션을 배포 하기 전에 추가 해야 합니다. 암호를 추가 하면 권한 있는 사용자가 문서;에서 보호를 제거할 수 있습니다. 암호 없이 보호 쉽게 제거할 수 없습니다. 암호를 설정 하는 방법에 대 한 세부 정보를 특정 Office 응용 프로그램에서 도움말을 참조 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 문서 및 문서의 일부 보호](../vsto/how-to-programmatically-protect-documents-and-parts-of-documents.md)   
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)   
 [정보 권한 관리 및 관리 코드 확장 개요](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Office 문서의 암호 보호](../vsto/password-protection-on-office-documents.md)   
 [방법: 코드 권한이 제한 된 문서 뒤 실행 허용](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)  
  
  