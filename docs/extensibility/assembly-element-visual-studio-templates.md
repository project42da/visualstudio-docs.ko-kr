---
title: Assembly 요소 (Visual Studio 템플릿) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#Assembly
helpviewer_keywords:
- Assembly element [Visual Studio templates]
- <Assembly> element [Visual Studio templates]
ms.assetid: 9242f76a-1273-4b8a-8f26-6606f91829ef
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 97e6209fdf446d88ed79ef741c3584b2bc4f5602
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="assembly-element-visual-studio-templates"></a>Assembly 요소(Visual Studio 템플릿)
템플릿을 사용 하 여 해당 어셈블리의 참조를 프로젝트에 추가 하는 어셈블리에 대 한 정보를 지정 합니다.  
  
 \<VSTemplate>  
 \<TemplateContent >  
 \<참조 >  
 \<참조 >  
 \<어셈블리 >  
  
## <a name="syntax"></a>구문  
  
```  
<Assembly> AssemblyName </Assembly>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[참조](../extensibility/reference-element-visual-studio-templates.md)|항목이 프로젝트에 추가될 때 추가할 어셈블리 참조를 지정합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 필수입니다.  
  
 이 텍스트는 항목 템플릿이 인스턴스화될 때 프로젝트에 추가할 어셈블리를 지정 합니다. 이 어셈블리 이름은 다음 방법 중 하나로 지정 해야 합니다.  
  
-   전체 어셈블리 이름입니다. 예를 들어:  
  
    ```  
    <Assembly>  
        MyAssembly, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom = null.  
    </Assembly>  
    ```  
  
-   단순한 텍스트 참조 합니다. 예를 들어:  
  
    ```  
    <Assembly> System </Assembly>  
    ```  
  
## <a name="remarks"></a>설명  
 `Assembly`은 `Reference`의 필수 자식 요소입니다.  
  
 `Reference`, `References,` 및 `Assembly` 요소 있는.vstemplate 파일에만 사용할 수 있습니다는 `Type` 특성 값이 `Item`합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `TemplateContent` 항목 템플릿의 요소입니다. 이 XML System.dll 및 System.Data.dll 어셈블리에 대 한 참조를 추가합니다.  
  
```  
<TemplateContent>  
    <References>  
        <Reference>  
            <Assembly>  
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>  
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
    </References>  
    ...  
</TemplateContent>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)