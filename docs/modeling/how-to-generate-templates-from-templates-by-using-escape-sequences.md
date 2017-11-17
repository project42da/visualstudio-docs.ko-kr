---
title: "방법: 이스케이프 시퀀스를 사용 하 여 템플릿에서 템플릿 생성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, generating templates from templates
ms.assetid: 4126156a-7cea-48b8-925e-7790806cfe6c
caps.latest.revision: "35"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 421b8a8bde2bb383889bcb58915fa8a3acb027cf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>방법: 이스케이프 시퀀스를 사용하여 템플릿에서 템플릿 생성
생성 된 텍스트 출력으로 다른 텍스트 템플릿을 작성 하는 텍스트 템플릿을 만들 수 있습니다. 이 작업을 수행 하려면 텍스트 템플릿 태그를 직접 지정할 필요 없이 이스케이프 시퀀스를 사용 해야 합니다. 이스케이프 시퀀스를 사용 하지 않는 경우 생성 된 텍스트 템플릿을 미리 정의 된 의미를 갖습니다. 텍스트 템플릿에서 이스케이프 시퀀스를 사용 하는 방법에 대 한 자세한 내용은 참조 [텍스트 템플릿에서 이스케이프 시퀀스를 사용 하 여](../modeling/using-escape-sequences-in-text-templates.md)합니다.  
  
### <a name="to-generate-a-text-template-from-within-a-text-template"></a>텍스트 템플릿 내에서 텍스트 템플릿을 생성 하려면  
  
-   백슬래시를 사용 하 여 (\\) 지시문, 문, 식에 대 한 텍스트 템플릿 내에서 필요한 태그를 생성 하 고 별도 텍스트 템플릿 파일의 기능 클래스에 이스케이프 문자로 합니다.  
  
    ```  
    \<#@ directive \#>  
    \<# statement \#>  
    \<#= expression \#>  
    \<#+ classfeature \#>  
    ```  
  
## <a name="example"></a>예제  
 다음 예제에서는 텍스트 템플릿에서 텍스트 서식 파일을 생성 하기 위해 이스케이프 문자를 사용 합니다. `output` 지시문 텍스트 템플릿 파일 형식 (.tt) 대상 파일 형식으로 설정 합니다.  
  
```csharp  
\<#@ output extension=".tt" \#>  
\<#@ assembly name="System.Xml.dll" \#>  
\<#@ import namespace="System.Xml" \#>  
\<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {\#>  
           \<#= attr.Name \#>  
       \<#}  
     }  
\#>  
```  
  
 생성된 된 텍스트 출력은 텍스트 템플릿입니다.  
  
```  
<#@ output extension=".tt" #>  
<#@ assembly name="System.Xml.dll" #>  
<#@ import namespace="System.Xml" #>  
<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {#>  
           <#= attr.Name #>  
       <#}  
     }  
#>  
```