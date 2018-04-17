---
title: 솔루션의 파일을 포함 하려면 모듈을 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deployment modules
- SharePoint development in Visual Studio, modules
- modules [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9c11dd4ebd17b1ebef91c3d7752df7c15dd50da4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="using-modules-to-include-files-in-the-solution"></a>모듈을 사용하여 솔루션에 파일 포함
  파일을 새 마스터 페이지 등의 파일 형식에 관계 없이 SharePoint 서버에 배포 하려는 경우가 있을 수 있습니다. 이 위해 사용할 수 있습니다 *모듈* (으로 다름 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 코드 모듈). 모듈은 파일을 SharePoint 솔루션에 대 한 컨테이너입니다. 솔루션을 배포할 때 모듈에 있는 파일에는 SharePoint 서버에 지정 된 폴더에 복사 됩니다.  
  
## <a name="module-items-and-elements"></a>모듈 항목과 요소  
 모듈을 만들려면 프로젝트에 추가 된에서 선택 하 여는 **새 항목 추가** 대화 상자. 그런 다음 해당 Elements.xml 파일 시스템에 위치 하 고 SharePoint 서버에 복사 해야 배포 하려는 파일의 이름을 포함 하도록 수정 합니다.  
  
 모듈에 대 한 Elements.xml 파일의 예는 다음과 같습니다.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Elements xmlns="http://schemas.microsoft.com/sharepoint/">  
    <Module Name="Module1">  
        <File Path="Module1\Sample.txt" Url="Module1/Sample.txt" />  
    </Module>  
</Elements>  
  
```  
  
 새로 만든 모듈에는 다음과 같은 기본 파일 포함:  
  
|파일 이름|설명|  
|---------------|-----------------|  
|Elements.xml|모듈에 대 한 정의 파일입니다.|  
|Sample.txt|모듈에 있는 파일의 예제로 사용 되는 자리 표시자 파일입니다.|  
  
 Elements.xml 파일에는 다음과 같은 요소가 포함 되어 있습니다.  
  
|요소 이름|설명|  
|------------------|-----------------|  
|요소|모든 모듈에 정의 된 요소를 포함 합니다.|  
|Module|모듈 요소는 단일 특성을 *이름*, 형식에서 모듈의 이름을 지정 하는 `<Module Name="Module1">`합니다.<br /><br /> 모듈의 이름을 변경 하는 경우 (또는 해당 *폴더 이름* 속성), 모듈 요소에 이름을 수동으로 업데이트 해야 합니다.<br /><br /> 모듈 요소에는 파일에 대 한 하위 디렉터리를 지정 하는 경우 [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] (WSS)에서 해당 작업에 대 한 일치 하는 디렉터리 구조를 자동으로 만듭니다.|  
|파일|파일 요소에 두 개의 매개 변수가 *경로* 및 *Url*합니다.<br /><br /> -경로: 이름 및 위치는 SharePoint 솔루션에 있는 파일의 합니다. 형식이 되 면 `Path="Module1\Sample.txt"`합니다.<br /><br /> -Url: 파일이 SharePoint 서버에 배포 될 위치입니다. 형식이 되 면 `Url="Module1/Sample.txt"`합니다.<br /><br /> -형식: 하는 선택적 특성에는 두 가지 설정이: *GhostableInLibrary* 및 *Ghostable*합니다. 형식이 되 면 `Type="GhostableInLibrary"`합니다. 지정 *GhostableInLibrary* 의미 파일을 라이브러리에 추가 될 때 파일에는 목록 항목과 함께 SharePoint의 문서 라이브러리에 추가 됩니다. 지정 *Ghostable* 하면 해당 파일이 외부 문서 라이브러리 SharePoint에 추가할 수 있습니다.|  
  
 배포 하려는 각 파일에는 별도 필요한 `<File>` Elements.xml 요소 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 모듈을 사용 하 여 파일 포함](../sharepoint/how-to-include-files-by-using-a-module.md)   
 [방법: 파일을 프로 비전](http://go.microsoft.com/fwlink/?LinkID=144271)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)   
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  