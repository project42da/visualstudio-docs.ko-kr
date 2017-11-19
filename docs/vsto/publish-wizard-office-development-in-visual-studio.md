---
title: "게시 마법사 (Visual Studio에서 Office 개발) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
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
ms.assetid: 793314b6-b6a6-4509-8f1c-dd9466cf5190
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8eeb0a002e2d62b9066165a99ce474cf7a01a88f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="publish-wizard-office-development-in-visual-studio"></a>게시 마법사(Visual Studio에서는 Office 개발)
  사용 하 여는 **게시 마법사** 솔루션 파일을 지정 된 위치에 복사 하려면 매니페스트 파일을 만들고 설치 프로그램을 만듭니다.  
  
 이 마법사에 액세스 하려면는 **빌드** 메뉴 선택 **게시** *SolutionName*합니다. 에 액세스할 수도 있습니다는 **게시 마법사** 에서 **솔루션 탐색기**합니다. 프로젝트 노드에 대 한 바로 가기 메뉴를 연 다음 선택 **게시**합니다.  
  
 아래의 각 섹션에서는 마법사의 페이지를 설명합니다.  
  
## <a name="where-do-you-want-to-publish-the-application"></a>여기서 응용 프로그램을 게시 하 시겠습니까?  
 **이 응용 프로그램을 게시할 위치를 지정 합니다.**  
 필수 요소. 게시 위치는 디렉터리 위치는 **게시 마법사** 빌드에서 매니페스트, 어셈블리, 임시 인증서 및 기타 파일과 같은 솔루션 파일을 복사 합니다. 이 디렉터리에 쓰기 권한이 있어야 합니다.  
  
 디스크 경로, 파일 공유, FTP 사이트 또는 웹 사이트 URL로 위치를 입력 하거나 클릭 하 고 **찾아보기** 위치를 검색 하는 단추입니다. 이러한 형식의 경로일 수 있습니다.  
  
-   C:\Deploy\MyApplication \MyApplication 등의 표준 Windows 형식의 상대 또는 절대 경로입니다.  
  
-   범용 명명 규칙 (UNC) 경로 같은 \\\ServerName\MyApplication\\합니다.  
  
-   Http://www.microsoft.com/MyApplication 같은 웹 사이트의 URL입니다.  
  
 기본적으로 게시 위치는 IIS를 설치한 경우 *http://localhost/projectname/* 이고, IIS를 설치하지 않은 경우 publish\ 디렉터리입니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce를 사용 하 여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Visual Studio &#41;의 페이지, 프로젝트 디자이너 &#40; Office 개발을 게시](../vsto/publish-page-project-designer-office-development-in-visual-studio.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
  