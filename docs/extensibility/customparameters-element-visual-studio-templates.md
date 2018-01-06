---
title: "CustomParameters 요소 (Visual Studio 템플릿) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameters
helpviewer_keywords: CustomParameters element [Visual Studio project templates]
ms.assetid: cf3efc91-1532-4022-bbb8-a18658424fee
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1b5fa3543113641666977816fadec49a02bc912a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="customparameters-element-visual-studio-templates"></a>CustomParameters 요소(Visual Studio 템플릿)
사용자 지정 매개 변수 마법사 매개 변수 대체를 사용 하면 템플릿 마법사 전달 되는 그룹화 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<CustomParameters>  
    <CustomParameter/>  
    <CustomParameter/>  
</CustomParameters>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[CustomParameter](../extensibility/customparameter-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 사용자 지정 매개 변수 이름과 템플릿에서 프로젝트 또는 항목이 만들어질 때 사용할 값을 포함 합니다. `CustomParameter` 요소에는 `CustomParameters` 요소가 0개 또는 그 이상 있을 수 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|서식 파일의 내용을 지정합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예  
 다음 예제에서는 서식 파일에 여러 사용자 지정 매개 변수를 사용 하는 방법을 보여 줍니다. 프로젝트 또는 항목이 만들어질 때 다음 사용자 지정 매개 변수의 모든 인스턴스를 사용 하 여 템플릿에서 `$color1$` 및 `$color2$` 서식 파일에서 파일을 대체할 `Red` 및 `Blue`각각.  
  
```  
<CustomParameters>  
    <CustomParameter Name="$color1$" Value="Red"/>  
    <CustomParameter Name="$color2$" Value="Blue "/>  
</CustomParameters>  
```  
  
## <a name="see-also"></a>참고 항목  
 [CustomParameter 요소 (Visual Studio 템플릿)](../extensibility/customparameter-element-visual-studio-templates.md)   
 [템플릿 매개 변수](../ide/template-parameters.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)