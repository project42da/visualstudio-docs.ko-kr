---
title: "템플릿 매개 변수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "항목 템플릿, 매개 변수"
  - "프로젝트 템플릿, 매개 변수"
  - "템플릿 매개 변수[Visual Studio]"
  - "Visual Studio 템플릿, 매개 변수"
ms.assetid: 1b567143-08c6-4d7a-b484-49f0671754fe
caps.latest.revision: 24
caps.handback.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 템플릿 매개 변수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

템플릿에 매개 변수를 사용하여, 템플릿이 인스턴스화될 때, 서식 파일, 네임 스페이스, 클래스 이름 등의 주요 부분 값을 바꿀 수 있습니다.  사용자가 **새 프로젝트** 및 **새 항목 추가** 대화 상자에서 **확인**을 클릭하면 백그라운드에서 실행되는 템플릿 마법사에 의해 이러한 매개 변수가 대체됩니다.  
  
## 템플릿 매개 변수 선언 및 활성화  
 템플릿 매개 변수는 $*parameter*$ 형식으로 선언됩니다.  예를 들면 다음과 같습니다.  
  
-   $safeprojectname$  
  
-   $guid1$  
  
-   $guid5$  
  
#### 템플릿에서 매개 변수 대체를 활성화하려면  
  
1.  템플릿의 .vstemplate 파일에서 매개 변수 대체를 활성화하려는 항목에 해당하는 `ProjectItem` 요소를 찾습니다.  
  
2.  `ProjectItem` 요소의 `ReplaceParameters` 특성을 `true`로 설정합니다.  
  
3.  프로젝트 항목에 대한 코드 파일에서 적절한 위치에 매개 변수를 포함합니다.  예를 들어 다음 매개 변수는 안전한 프로젝트 이름이 파일의 네임스페이스에 사용되도록 지정합니다.  
  
    ```  
    namespace $safeprojectname$  
    ```  
  
## 예약된 템플릿 매개 변수  
 다음 표에서는 모든 템플릿에 사용할 수 있는 예약된 템플릿 매개 변수 목록을 보여 줍니다.  
  
> [!NOTE]
>  템플릿 매개 변수는 대\/소문자를 구분합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`clrversion`|CLR\(공용 언어 런타임\)의 현재 버전|  
|`GUID [1-10]`|프로젝트 파일에서 프로젝트 GUID를 대체하는 데 사용되는 GUID.  최대 10개의 고유 GUID를 지정할 수 있습니다\(예: `guid1)`.|  
|`itemname`|**새 항목 추가** 대화 상자에서 사용자가 제공한 이름|  
|`machinename`|현재 컴퓨터 이름\(예: Computer01\)|  
|`projectname`|**새 프로젝트** 대화 상자에서 사용자가 제공한 이름|  
|`registeredorganization`|HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\RegisteredOrganization에 있는 레지스트리 키 값|  
|`rootnamespace`|현재 프로젝트의 루트 네임스페이스.  이 매개 변수는 항목 템플릿에 적용됩니다.|  
|`safeitemname`|**새 항목 추가** 대화 상자에서 사용자가 제공한 이름으로, 안전하지 않은 문자와 공백은 모두 제거됩니다.|  
|`safeprojectname`|**새 프로젝트** 대화 상자에서 사용자가 제공한 이름으로, 안전하지 않은 문자와 공백은 모두 제거됩니다.|  
|`time`|DD\/MM\/YYYY 00:00:00 형식의 현재 시간|  
|`SpecificSolutionName`|솔루션의 기본 이름.  "솔루션 디렉터리 만들기"를 선택한 경우 `SpecificSolutionName` 은 솔루션 이름이 있습니다.  "솔루션 디렉터리 만들기" 선택 되지 않은 경우 `SpecificSolutionName` 는 비어 있습니다.|  
|`userdomain`|현재 사용자 도메인|  
|`username`|현재 사용자 이름|  
|`webnamespace`|현재 웹 사이트의 이름입니다.  이 매개 변수는 웹 폼 템플릿에서 고유한 클래스 이름을 보장하는 데 사용됩니다.  웹 사이트가 웹 서버의 루트 디렉터리에 있는 경우 이 템플릿 매개 변수는 웹 서버의 루트 디렉터리가 됩니다.|  
|`year`|YYYY 형식의 현재 연도|  
  
## 사용자 지정 템플릿 매개 변수  
 매개 변수를 대체하는 동안 자동으로 사용되는 예약된 템플릿 매개 변수 외에 직접 만든 템플릿 매개 변수와 값을 지정할 수 있습니다. 자세한 내용은 다음 [CustomParameters 요소\(Visual Studio 템플릿\)](../extensibility/customparameters-element-visual-studio-templates.md) 을 참조하십시오.  
  
## 예제: 파일 이름 대체  
 `TargetFileName` 특성이 있는 매개 변수를 사용하여 프로젝트 항목에 대해 가변 파일 이름을 지정할 수 있습니다.  예를 들어 프로젝트 이름을 `$projectname$`에 지정하여 파일 이름으로 사용하도록 .exe 파일에 지정할 수 있습니다.  
  
```  
<TemplateContent>  
    <ProjectItem  
        ReplaceParameters="true"  
        TargetFileName="$projectname$.exe">  
            File1.exe  
    </ProjectItem>  
      ...  
</TemplateContent>  
```  
  
## 예제: 네임스페이스 이름에 프로젝트 이름 사용  
 Class1.cs라는 Visual C\# 클래스 파일에서 네임스페이스에 프로젝트 이름을 사용하려면 다음 구문을 사용합니다.  
  
```  
#region Using directives  
  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
#endregion  
  
namespace $safeprojectname$  
{  
    public class Class1  
        {  
            public Class1()  
                {  
  
                }  
         }  
}  
```  
  
 프로젝트 템플릿의 .vstemplate 파일에서 Class1.cs 파일을 참조할 때 다음 XML을 포함합니다.  
  
```  
<TemplateContent>  
    <ProjectItem ReplaceParameters="true">  
        Class1.cs  
    </ProjectItem>  
    ...  
</TemplateContent>  
```  
  
## 참고 항목  
 [템플릿 사용자 지정](../ide/customizing-project-and-item-templates.md)