---
title: '방법: BDC 기능에 사용자 지정 어셈블리 포함 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.BDC.Add_Assemblies_Dialog
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], add reference
- Business Data Connectivity service [SharePoint development in Visual Studio], custom assembly
- BDC [SharePoint development in Visual Studio], custom assembly
- BDC [SharePoint development in Visual Studio], add reference
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ab104ee31246a524e2c34c513a66a5f5143d5f55
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-include-a-custom-assembly-in-a-bdc-feature"></a>방법: BDC 기능에 사용자 지정 어셈블리 포함
  프로젝트가 동일한 솔루션의 다른 프로젝트에서 어셈블리를 참조할 수 있습니다. 그러나 사용 하 여 프로젝트의 기능 파일에 이러한 어셈블리를 추가 해야 합니다는는 **할당 참조 어셈블리를 Lobsystem** 대화 상자.  
  
### <a name="to-include-a-custom-assembly-in-a-business-data-connectivity-bdc-feature"></a>BDC 비즈니스 데이터 연결 () 기능에 사용자 지정 어셈블리를 포함 하려면  
  
1.  **솔루션 탐색기**를 BDC 모델이 포함 된 폴더를 선택 합니다.  
  
2.  **보기** 메뉴에서 **속성 창**을 클릭합니다.  
  
3.  에 **속성** 창, 선택는 **어셈블리** 속성, 한 다음 줄임표 단추 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")).  
  
     **할당 참조 어셈블리를 Lobsystem** 대화 상자가 나타납니다.  
  
4.  에 **어셈블리 선택** 목록에서 사용자 지정 어셈블리를 선택 합니다.  
  
    > [!NOTE]  
    >  어셈블리에만 표시는 **할당 참조 어셈블리를 Lobsystem** 어셈블리를 포함 하는 프로젝트에 대 한 참조를 추가한 경우 대화 상자. 자세한 내용은 참조 [하는 방법: 참조 추가 또는 제거 참조 추가 대화 상자를 사용 하 여](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)합니다.  
  
5.  에 **참조 속성** 그룹,이 대해 표시 되 고 목록을 연는 **LobSystem 범위** 속성을 사용자 지정 어셈블리를 사용 하 고 다음을 선택 하는 메서드의 LOB 시스템에서 **확인**  단추입니다.  
  
    > [!NOTE]  
    >  사용자 지정 어셈블리에 코드를 디버깅 하려면 솔루션 패키지에 어셈블리를 추가 해야 합니다. 자세한 내용은 참조 [하는 방법: 추가 어셈블리 추가 및 제거](../sharepoint/how-to-add-and-remove-additional-assemblies.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 리소스 파일을 사용 하 여 지역화 된 이름, 속성 및 사용 권한을 지정 합니다.](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [방법: SharePoint 프로젝트에 기존 BDC 모델 파일 추가](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  