---
title: 게시 마법사 (Visual Studio에서 Office 개발)
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.ProjectProperties.PublishWizard
- VST.PublishWizard.Publish.2007System
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], Publish Wizard
- deploying applications [Office development in Visual Studio], Publish Wizard
- Office applications [Office development in Visual Studio], Publish Wizard
- Publish Wizard, Office solutions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2481557d1d75d64b5eb3f52f2755953ca344d323
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692722"
---
# <a name="publish-wizard-office-development-in-visual-studio"></a>게시 마법사 (Visual Studio에서 Office 개발)
  사용 하 여는 **게시 마법사** 솔루션 파일을 지정 된 위치에 복사 하려면 매니페스트 파일을 만들고 설치 프로그램을 만듭니다.  
  
 이 마법사에 액세스 하려면는 **빌드** 메뉴 선택 **게시** *SolutionName*합니다. 에 액세스할 수도 있습니다는 **게시 마법사** 에서 **솔루션 탐색기**합니다. 프로젝트 노드에 대 한 바로 가기 메뉴를 연 다음 선택 **게시**합니다.  
  
 아래의 각 섹션에서는 마법사의 페이지를 설명합니다.  
  
## <a name="where-do-you-want-to-publish-the-application"></a>여기서 응용 프로그램을 게시 하 시겠습니까?  
 **이 응용 프로그램을 게시할 위치를 지정 합니다.**  
 필수. 게시 위치는 디렉터리 위치는 **게시 마법사** 빌드에서 매니페스트, 어셈블리, 임시 인증서 및 기타 파일과 같은 솔루션 파일을 복사 합니다. 이 디렉터리에 쓰기 권한이 있어야 합니다.  
  
 디스크 경로, 파일 공유, FTP 사이트 또는 웹 사이트 URL로 위치를 입력 하거나 클릭 하 고 **찾아보기** 위치를 검색 하는 단추입니다. 이러한 형식의 경로일 수 있습니다.  
  
-   표준에 대 한 상대 또는 절대 경로 포맷할와 같은 *C:\Deploy\MyApplication* 또는 *\MyApplication*합니다.  
  
-   범용 명명 규칙 (UNC) 경로 같은  *\\\ServerName\MyApplication\\*합니다.  
  
-   URL을 웹 사이트와 같은 http://www.microsoft.com/MyApplication합니다.  
  
 기본적으로 게시 위치는 *http://localhost/projectname/* IIS가 설치 되어 있는 경우 또는 작업을 수행한 경우 publish\ 디렉터리 IIS가 설치 되지 합니다.  
  
> [!NOTE]  
>  대상 컴퓨터가 Windows Vista를 실행 중인 경우 자세한 고려 사항이 있습니다. 로컬 게시 옵션을 사용 하려면 Windows Vista 컴퓨터의 관리자 여야 합니다. 또한 기본 위치는 항상는 *게시\\*  IIS가 설치 되어 있는지 여부에 관계 없이 디렉터리입니다.  
  
## <a name="what-is-the-default-installation-path-on-end-user-computers"></a>최종 사용자 컴퓨터에 기본 설치 경로 무엇입니까?  
 설치 경로 선택 사항입니다. 원하는 경우 나중에 설치 경로 설정할 수 있습니다. 자세한 내용은 참조 [하는 방법: Office 솔루션의 설치 경로 변경](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd)합니다.  
  
 설치 경로 최종 사용자가 사용자 지정을 설치 하는 데는 원본 디렉터리입니다. 또한 솔루션에서 업데이트를 확인하는 데 사용하는 경로이기도 합니다. **게시 마법사** 경로에 입력 한 것과 동일한 경우이 위치에는 솔루션을 배포 하지 않습니다는 **이 응용 프로그램을 게시할 위치를 지정** 이전 페이지에서 상자입니다.  
  
 **웹 사이트에서**  
 최종 사용자가 솔루션을 설치 하기 위해 수행 하는 URL을 지정 합니다.  
  
 **UNC 경로 또는 파일 공유에서**  
 최종 사용자가 솔루션을 설치 하기 위해 수행 된 UNC 경로 지정 합니다.  
  
 **CD-ROM 또는 DVD-ROM에서**  
 이 옵션의 설치 경로 필요가 없습니다.  
  
 CD 또는 DVD에는 visual Studio 진행 되지 않습니다. 출력을 CD 또는 DVD에 수동으로 복사 해야 합니다.  
  
## <a name="see-also"></a>참고자료  
 [ClickOnce를 사용 하 여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [프로젝트 디자이너, 게시 페이지 &#40;Visual Studio에서 Office 개발&#41;](../vsto/publish-page-project-designer-office-development-in-visual-studio.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
  