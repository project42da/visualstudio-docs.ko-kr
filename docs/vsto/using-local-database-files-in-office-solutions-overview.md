---
title: Office 솔루션 개요에서 로컬 데이터베이스 파일을 사용 하 여
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- data [Office development in Visual Studio], local
- local data [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 01e9dc3df93e1f721eba9ce3bcf65d4fb8bb1ca1
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767584"
---
# <a name="use-local-database-files-in-office-solutions-overview"></a>Office 솔루션 개요에서 로컬 데이터베이스 파일을 사용 하 여
  SQL Server Express 등의 데이터베이스 파일을 포함할 수 있습니다 (*.mdf*) 파일 또는 Microsoft Office Access (*.mdb*) Office 솔루션의 파일입니다. 그러면 최종 사용자가에서 중앙 집중식된 데이터베이스 유지 관리에 단일 컴퓨터에만 사용 되는 로컬 재고 관리 솔루션의 예를 들어 필요 없는 경우 로컬 데이터베이스를 유지할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="import-the-database-file-into-a-project"></a>데이터베이스 파일을 프로젝트로 가져옵니다  
 사용 하 여 프로젝트에 데이터베이스 파일을 가져오려면는 **데이터 소스 구성 마법사** 데이터베이스 파일에 따라 데이터 소스를 만듭니다. 마법사는 데이터베이스 파일 및 형식화 된 데이터 집합 프로젝트에 추가합니다.  
  
## <a name="deploy-the-database-file"></a>데이터베이스 파일 배포  
 **데이터 소스 구성 마법사** 상대 경로 사용 하 여 로컬 데이터베이스 파일에 대 한 연결을 만듭니다. 이 파일의 상대 위치를 유지 하는 경우 한 컴퓨터에서 솔루션을 다른 위치로 복사할 수 있습니다.  
  
 서버에 솔루션을 배포 하 고 각 최종 사용자에 게 문서를 배포 하는 경우 수동으로 배포 데이터베이스 파일 하 고 문서를 기준으로 동일한 위치에 설치 합니다. 따라서는 최종 사용자 수 없습니다 이동할 문서를 새 위치로 자신의 컴퓨터에 데이터베이스 파일 이동 타당 하지 않는 한 합니다.  
  
## <a name="local-database-files-and-caching-the-dataset"></a>로컬 데이터베이스 파일 및 데이터 집합 캐싱  
 Microsoft Office Excel 및 Microsoft Office Word 용 문서 수준 솔루션에 특성을 사용 하 여 데이터 집합 인스턴스를 표시 하 여 문서에서 데이터 집합을 캐시할 수 있습니다 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>합니다. 사용 하 여 프로젝트에 데이터베이스 파일을 추가 하는 경우는 **데이터 소스 구성 마법사**, 형식화 된 데이터 집합 프로젝트에 자동으로 추가 됩니다. 적용 하는 것이 자주 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 이이 dataset에는 데이터는 사용자의 컴퓨터에 로컬 이미 있으므로 합니다. 자세한 내용은 참조 [데이터 캐시](../vsto/caching-data.md)합니다.  
  
## <a name="see-also"></a>참고자료  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [방법: 데이터베이스의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [방법: 호스트 컨트롤의 데이터로 데이터 소스를 업데이트 합니다.](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [데이터 캐시](../vsto/caching-data.md)  
  
  