---
title: "방법: 이스케이프 시퀀스를 사용하여 템플릿에서 템플릿 생성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "텍스트 템플릿, 템플릿에서 템플릿 생성"
ms.assetid: 4126156a-7cea-48b8-925e-7790806cfe6c
caps.latest.revision: 35
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 35
---
# 방법: 이스케이프 시퀀스를 사용하여 템플릿에서 템플릿 생성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

생성된 텍스트 출력으로 또 다른 텍스트 템플릿을 만드는 텍스트 템플릿을 만들 수 있습니다.  이렇게 하려면 이스케이프 시퀀스를 사용하여 텍스트 템플릿 태그를 나타내야 합니다.  이스케이프 시퀀스를 사용하지 않는 경우 생성된 텍스트 템플릿에는 미리 정의된 의미가 있습니다.  텍스트 템플릿에서 이스케이프 시퀀스를 사용하는 방법에 대한 자세한 내용은 [텍스트 템플릿에서 이스케이프 시퀀스 사용](../modeling/using-escape-sequences-in-text-templates.md)을 참조하십시오.  
  
### 텍스트 템플릿 내에서 텍스트 템플릿을 생성하려면  
  
-   백슬래시\(\\\)를 이스케이프 문자로 사용하여 별도의 텍스트 템플릿 파일에 있는 지시문, 문, 식 및 클래스 기능에 대한 필요한 태그를 텍스트 템플릿 안에 생성합니다.  
  
    ```  
    \<#@ directive \#>  
    \<# statement \#>  
    \<#= expression \#>  
    \<#+ classfeature \#>  
    ```  
  
## 예제  
 다음 예제에서는 이스케이프 문자를 사용하여 텍스트 템플릿에서 텍스트 템플릿을 생성합니다.  `output` 지시문은 대상 파일 형식을 텍스트 템플릿 파일 형식\(.tt\)으로 설정합니다.  
  
```c#  
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
  
 생성된 텍스트 출력은 텍스트 템플릿입니다.  
  
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