---
title: "RequiredPlatformVersion 요소 (Visual Studio 템플릿) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f0e4986-3157-4bba-aed3-c28413ebe976
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f7eb4ada8378ff9009987f56341a65670a3c412
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="requiredplatformversion-element-visual-studio-templates"></a>RequiredPlatformVersion 요소(Visual Studio 템플릿)
프로젝트 템플릿이 제대로 작동 하는 데 필요한 운영 체제의 최소 버전을 지정 합니다. 이 요소는 만들 프로젝트 템플릿에 대 한 데 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 앱.  
  
 `RequiredPlatformVersion` 값이 버전의 운영 체제와 직접 비교 됩니다. 경우는 `RequiredPlatformVersion` 운영 체제 버전 보다 높은에 해당 템플릿이 표시 되지 않습니다는 **새 프로젝트** 대화 상자. 에 대 한 서식 파일을 지정 하려면 [!INCLUDE[win8](../debugger/includes/win8_md.md)] 높은, 설정 또는 `RequiredPlatformVersion` 6.2.0에 있습니다. 에 대 한 서식 파일을 지정 하려면 [!INCLUDE[win81](../debugger/includes/win81_md.md)] 또는 6.3.0에 RequiredPlatformVersion 이상으로 설정 합니다.  
  
 지정 하는 템플릿 `RequiredPlatformVersion`= 8 이전 고객와 호환 되는 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 템플릿.  
  
 VSTemplate  
TemplateData  
..... TargetPlatformName  
RequiredPlatformVersion  
  
## <a name="syntax"></a>구문  
  
```xml  
<RequiredPlatformVersion> OperatingSystem </RequiredPlatformVersion>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 없음  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[TemplatePlatformName](../extensibility/templatedata-element-visual-studio-templates.md)|프로젝트 템플릿의 대상 플랫폼을 지정합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 필수입니다.  
  
## <a name="remarks"></a>설명  
 이 텍스트는 서식 파일에 필요한 최소 운영 체제 버전을 지정 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 프로젝트 템플릿이 [!INCLUDE[win8](../debugger/includes/win8_md.md)] 이상을 대상으로 하도록 지정합니다.  
  
```xml  
<VSTemplate Type="Project" Version="3.0.0"    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <TargetPlatformName>Windows</TargetPlatformName>  
            <RequiredPlatformVersion>6.3.0</RequiredPlatformVersion>  
  
    </TemplateData>  
    <TemplateContent>  
  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>참고 항목  
 [TargetPlatformName 요소 (Visual Studio 템플릿)](../extensibility/targetplatformname-element-visual-studio-templates.md)   
 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)