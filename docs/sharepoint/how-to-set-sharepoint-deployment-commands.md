---
title: "방법: SharePoint 배포 명령 설정 | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2f465deaaca406c28aab177434e72de9746fb101
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>방법: SharePoint 배포 명령 설정
  배포 전 / 배포 후 명령이 설정 하 여 배포 프로세스를 사용자 지정할 수 있습니다. 이들이 명령은 Visual Studio에서 SharePoint 솔루션을 디버깅할 때 다른 배포 작업 전후의 실행 합니다.  
  
### <a name="to-add-a-pre-deployment-command"></a>배포 전 명령을 추가 하려면  
  
1.  메뉴 모음에서 **프로젝트**, *ProjectName***속성**을 참조하세요.  
  
2.  선택 된 **SharePoint** 탭 합니다.  
  
3.  에 **배포 전 명령줄** 텍스트 상자에이 단계를 사용자 지정할 MS-DOS 또는 MSBuild 명령을 입력 합니다.  
  
     예를 들어 입력 배포가 완료 되기 전에 디렉터리 내용을 나열할, **dir**합니다.  
  
### <a name="to-add-a-post-deployment-command"></a>배포 후 명령을 추가 하려면  
  
1.  메뉴 모음에서 **프로젝트**, *ProjectName***속성**을 참조하세요.  
  
2.  선택 된 **SharePoint** 탭 합니다.  
  
3.  에 **배포 후 명령줄** 텍스트 상자에이 단계를 사용자 지정할 MS-DOS 또는 MSBuild 명령을 입력 합니다.  
  
     예를 들어 입력 배포가 완료 된 후 디렉터리 내용을 나열할, **dir**합니다. 빌드 디렉터리에서 어셈블리를 복사 하는 MSBuild 변수를 사용 하려면 입력 **$ (targetpath) c:\DeploymentDirectory 복사**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  