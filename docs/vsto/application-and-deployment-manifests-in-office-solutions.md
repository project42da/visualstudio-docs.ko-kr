---
title: Office 솔루션에서 응용 프로그램 및 배포 매니페스트 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- manifests [Office development in Visual Studio]
- deployment manifests [Office development in Visual Studio]
- application manifests [Office development in Visual Studio]
- assemblies [Office development in Visual Studio], updating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7c828a4ff5b4b54836f67b208dd0188db765fd71
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="application-and-deployment-manifests-in-office-solutions"></a>Office 솔루션의 응용 프로그램 및 배포 매니페스트
  응용 프로그램 매니페스트는 Office 솔루션에서 어셈블리를 찾고 업데이트하는 데 사용되는 정보를 제공하는 XML 파일입니다. 응용 프로그램 매니페스트는 배포 매니페스트와 함께 사용할 수 있습니다. 배포 매니페스트는 서버에 저장된 XML 파일로, 최신 버전의 응용 프로그램 매니페스트 및 어셈블리를 찾는 데 필요한 정보를 제공합니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="manifest-structure-for-office-solutions"></a>Office 솔루션의 매니페스트 구조  
 Visual Studio에서 Office 개발 도구를 사용하여 만든 Microsoft Office 솔루션의 경우 모든 매니페스트는 표준 ClickOnce 스키마를 기반으로 합니다. Office 솔루션을 배포할 때 문서 수준 및 VSTO 추가 기능 프로젝트의 응용 프로그램 매니페스트는 ClickOnce 캐시에 있습니다. 배포 매니페스트는 클라이언트 컴퓨터에 복사되지 않습니다.  
  
 Office 프로젝트에 대한 배포 매니페스트 및 응용 프로그램의 내용에 대한 자세한 내용은 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md) 및 [Deployment Manifests for Office Solutions](../vsto/deployment-manifests-for-office-solutions.md)를 참조하세요.  
  
## <a name="creating-application-and-deployment-manifests"></a>응용 프로그램 및 배포 매니페스트 만들기  
 응용 프로그램 매니페스트는 빌드 프로세스의 일부로 자동으로 생성됩니다. 문서 수준 프로젝트를 빌드할 때마다 배포 매니페스트의 위치가 사용자 지정 문서 속성으로 문서에 포함됩니다. VSTO 추가 기능의 경우 배포 매니페스트의 위치는 레지스트리에 저장됩니다.  
  
 에 대 한 자세한 내용은 **게시 마법사**, 참조 [ClickOnce를 사용 하 여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)합니다.  
  
 방법에 대 한 자세한 내용은 매니페스트가 Office 솔루션과 작동 하는, 참조 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)   
 [VSTO 추가 기능 아키텍처](../vsto/architecture-of-vsto-add-ins.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 솔루션에 대 한 배포 매니페스트](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest)   
 [ClickOnce 배포 매니페스트](/visualstudio/deployment/clickonce-deployment-manifest)  
  
  