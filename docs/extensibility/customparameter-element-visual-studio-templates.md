---
title: "CustomParameter 요소 (Visual Studio 템플릿) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameter
helpviewer_keywords: CustomParameters element [Visual Studio project templates]
ms.assetid: 743c4489-74ac-403a-bbaa-eed7d785a3ac
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8b2380a585b1c428516e1578587c64b93d5b1d4e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="customparameter-element-visual-studio-templates"></a>CustomParameter 요소(Visual Studio 템플릿)
사용자 지정 매개 변수 이름과 템플릿에서 프로젝트 또는 항목이 만들어질 때 사용할 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<CustomParameter Name="name" Value="value">  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`Name`|필수. 매개 변수의 이름입니다. 매개 변수의 형식은 $*이름*$입니다.|  
|`Value`|필수. 매개 변수에 대해 대체 값을 지정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[CustomParameters](../extensibility/customparameters-element-visual-studio-templates.md)|사용자 지정 매개 변수 마법사 매개 변수 대체를 사용 하면 템플릿 마법사 전달 되는 그룹화 합니다.|  
  
## <a name="remarks"></a>설명  
 서식 파일에 포함 되어 있으면 `CustomParameter` 요소, 모든 인스턴스는 `Name` 특성으로 대체 됩니다는 `Value` 만들어진된 프로젝트 또는 항목 파일에는 특성입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 서식 파일에 여러 사용자 지정 매개 변수를 사용 하는 방법을 보여 줍니다. 프로젝트 또는 항목이 만들어질 때 다음 사용자 지정 매개 변수의 모든 인스턴스를 사용 하 여 템플릿에서 `$color1$` 및 `$color2$` 서식 파일에서 파일을 대체할 `Red` 및 `Blue`각각.  
  
```  
<CustomParameters>  
    <CustomParameter Name="$color1$" Value="Red"/>  
    <CustomParameter Name="$color2$" Value="Blue "/>  
</CustomParameters>  
```  
  
## <a name="see-also"></a>참고 항목  
 [CustomParameters 요소 (Visual Studio 템플릿)](../extensibility/customparameters-element-visual-studio-templates.md)   
 [템플릿 매개 변수](../ide/template-parameters.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)