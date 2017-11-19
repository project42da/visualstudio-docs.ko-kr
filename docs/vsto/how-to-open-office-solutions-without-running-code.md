---
title: "방법: Office 솔루션 코드를 실행 하지 않고 열기 | Microsoft Docs"
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
helpviewer_keywords:
- Office solutions [Office development in Visual Studio], opening
- opening Office solutions
- bypassing assemblies
- solutions [Office development in Visual Studio], opening
- assemblies [Office development in Visual Studio], bypassing
- Office documents [Office development in Visual Studio, opening without running code
- documents [Office development in Visual Studio], opening without running code
ms.assetid: a853d91c-9fd6-421a-b3a2-956b6b494b96
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 74cc162e0323656bea9d48c8458eaf77519fdc14
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-open-office-solutions-without-running-code"></a>방법: 코드를 실행하지 않고 Office 솔루션 열기
  관리 코드 확장을 사용 하 여 만든 Microsoft Office 솔루션에는 최종 사용자의 Office 응용 프로그램에서 보안 설정을 높음으로 설정 되어 있는 경우에 실행 됩니다. Microsoft Office가 아닌 Microsoft.NET Framework에서 관리 하는.NET 어셈블리 코드 보안 때문입니다.  
  
 그러나 코드를 실행 하지 않고 문서를 열려고 할 수 있습니다 때 경우가 있습니다. 예를 들어 문서를 열 때 실행 되는 코드, 콘텐츠를 변경할 수 있지만 것 코드 변경 되기 전에 문서 표시 되는 방식을 업데이트 하려는. 또는 다른 사람에 특정 정보를 사용 하 여 문서를 보낼 하려는 경우도 및 실행 하 고, 콘텐츠를 변경할 수 있는 코드를 원하지 않는 합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 문서 또는 어셈블리 코드를 실행 하지 않고 관리 코드 확장이 있는 통합 문서를 여는 방법은 여러 가지가 있습니다.  
  
### <a name="to-bypass-the-assembly-by-using-the-shift-key"></a>SHIFT 키를 사용 하 여 어셈블리를 무시 하려면  
  
-   문서 및에서 통합 문서를 열면는 **파일** Word 및 Excel 문서를 여는 동안 초기화 이벤트가 발생 하지 않도록 하려면 SHIFT 키를 누른 채 메뉴.  
  
    > [!NOTE]  
    >  문서 또는 통합 문서를 열면는 **시작** shift 작업창 코드가 무시 하지 않습니다. 또한 키를 누른 채 때도 이벤트 문서를 연 후 발생 합니다.  
  
     이 메서드는 먼저 문서를 변경할 때와 실행 코드 없이 변경 하려면 문서를 열려고 할 때 유용 합니다.  
  
### <a name="to-bypass-an-assembly-by-renaming-or-removing-it"></a>어셈블리를 제거 하거나 이름을 변경 하지 않으려면  
  
-   어셈블리가 있는 컴퓨터에 필요한 권한이 있으면 이름을 바꿀 수도 있고 어셈블리를 제거 하는 문서 또는 통합 문서를 찾을 수 없습니다. 이 Office 문서를 열 때마다 발생 하는 오류가 발생 합니다.  
  
     솔루션에 여러 사용자를 사용 하는 경우이 메서드는 솔루션의 모든 작업이 실행 않도록 합니다. 코드 또는 참조 된 서버에서 문제가 발견 되 고이 실행에서 모든 사용자가을 중지할 하려는 경우에 유용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Office 솔루션의 응용 프로그램 및 배포 매니페스트](../vsto/application-and-deployment-manifests-in-office-solutions.md)  
  
  