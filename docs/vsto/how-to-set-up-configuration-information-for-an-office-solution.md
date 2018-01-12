---
title: "방법: Office 솔루션에 대 한 구성 정보를 설정 합니다. | Microsoft Docs"
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
- solutions [Office development in Visual Studio], configuration files
- configuration files [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6f604fa40a9816d5e46593bc50fcb91f82d13325
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-set-up-configuration-information-for-an-office-solution"></a>방법: Office 솔루션의 구성 정보 설정
  Office 솔루션에 관련 된 설정을 구성 하려면 구성 파일을 사용할 수 있습니다. 어셈블리 바인딩 정책, 원격 개체, debug 및 추적 설정 등 설정을 지정할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-configuration-file-to-your-office-project"></a>Office 프로젝트에 구성 파일을 추가 하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2.  에 **범주** 창에서 클릭 **일반**합니다.  
  
3.  에 **템플릿** 창 선택 **응용 프로그램 구성 파일**합니다.  
  
4.  에 **이름** 확장명.config 어셈블리와 같은 이름을 입력 합니다. 예를 들어 ExcelWorkbook1.dll 라는 Excel 프로젝트 어셈블리에 대 한 구성 파일 이름이 ExcelWorkbook1.dll.config 합니다.  
  
5.  **추가**를 클릭합니다.  
  
6.  응용 프로그램 구성 파일 스키마에 따라 구성 파일을 만듭니다. 자세한 내용은 참조 [.NET Framework에 대 한 구성 파일 스키마](/dotnet/framework/configure-apps/file-schema/index)합니다.  
  
 구성 파일을 사용 하 여 Office 프로젝트를 사용 하는 것에 대 한 특별 한 고려 사항 없이 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework에 대 한 구성 파일 스키마](/dotnet/framework/configure-apps/file-schema/index)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
  