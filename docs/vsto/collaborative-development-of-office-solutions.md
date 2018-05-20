---
title: Office 솔루션 공동 개발
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], collaborative development
- Office development in Visual Studio, collaboration
- source control [Office development in Visual Studio]
- collaborative development [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9bf85dd1ba39df35e337f1b6b80099e3d5bcd774
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="collaborative-development-of-office-solutions"></a>Office 솔루션 공동 개발
  여러 개발자가 다른 Visual Studio 프로젝트에서 공동으로 작업 하는 동일한 방식으로 Office 프로젝트를 작업할 수 있습니다. Visual Studio 서로 다른 위치에 Office가 설치 된 경우에 각 컴퓨터에 Microsoft Office 설치를 제대로 찾습니다. 그러나 알아두어야 할 몇 가지 중요 한 고려 사항이 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="debug-properties-are-not-shared"></a>디버그 속성 공유 되지 않습니다.  
 디버그 속성은 소스 제어에서 여러 사용자 간에 공유되지 않습니다. Visual Basic 및 Visual C# 프로젝트 디버깅 속성을 사용자별 파일에 저장 (*p r o j*. vbproj.user 또는 *ProjectName*. csproj.user),이 파일은 소스 제어에서 및 합니다. 둘 이상의 사용자를 디버깅하는 경우 각 사용자가 디버그 속성을 수동으로 입력해야 합니다.  
  
 프로젝트 소스 제어 아닌 네트워크 공유에 보관 됩니다, 솔루션을 열고는 어셈블리를 테스트 하는 공동 개발자가 사용할 수 있도록 몇 가지 추가 단계가 기울여야 합니다.  
  
## <a name="source-control-requires-checking-out-all-files"></a>소스 컨트롤을 사용 하려면 모든 파일을 체크 아웃  
 프로젝트에 대 한 소스 제어를 사용 하는 경우 체크 아웃 해야에서 코드 파일에서 파일을 모두 **솔루션 탐색기** (예:는 *ThisDocument*, *ThisWorkbook*, 또는 *ThisAddIn* 코드 파일) 코드 파일을 변경 될 때마다 기본적으로 숨겨져 있는 파일에도 합니다. 을 체크 아웃 최상위 코드 파일에만 변경 내용이 손실 될 수 있습니다.  
  
 변경 내용을 변경한 후의 모든 파일을 다시 체크 인 합니다. 프로젝트의 숨김된 코드 파일에 대 한 자세한 내용은 참조 [Visual Studio 환경의 Office 프로젝트](../vsto/office-projects-in-the-visual-studio-environment.md)합니다.  
  
## <a name="security-for-informal-collaboration-on-a-network"></a>네트워크에서 간단한 공동 작업에 대 한 보안  
 네트워크 위치에 있는 모든 문서 수준 솔루션에 대 한 (예: \\ \\ *Servername*\\*Sharename*), 정규화 된 위치에 추가 되어야 합니다 사용 하는 Microsoft Office 응용 프로그램에 신뢰할 수 있는 폴더 목록입니다. 주 폴더 아래에서 하위 디렉터리를 포함 하거나 구체적으로 디버그를 추가 하 고 빌드 신뢰할 수 있는 폴더 목록에 폴더를 선택 합니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 참조 하십시오. [문서에 신뢰 부여](../vsto/granting-trust-to-documents.md)합니다.  
  
 빌드 시간에 자동으로 생성 되는 임시 인증서는 암호로 보호 되지 않습니다. 인증서는 개발자의 로그인 이름 및 기타 개인 정보를 포함 합니다. 임시 인증서로 서명 하는 사용자 지정 배포 하는 경우 다른 사용자에이 정보에 액세스할 수 수 있습니다.  
  
## <a name="see-also"></a>참고자료  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [디자인 하 고 Office 솔루션을 만들려면](../vsto/designing-and-creating-office-solutions.md)   
 [Office 솔루션 빌드](../vsto/building-office-solutions.md)  
  
  