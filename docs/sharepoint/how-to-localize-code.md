---
title: "방법: 코드 지역화 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "코드 지역화[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 지역화"
ms.assetid: 0e852052-5ad4-4517-81cf-8865ec304441
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# 방법: 코드 지역화
  지역화되지 않은 코드에서는 하드 코드된 문자열 값을 사용합니다.  코드 문자열을 지역화하려면 지역화된 리소스를 참조하는 메서드인 <xref:System.Web.HttpContext.GetGlobalResourceObject%2A>를 호출하여 코드 문자열을 바꿉니다.  
  
## 코드 지역화  
  
#### 코드를 지역화하려면  
  
1.  **솔루션 탐색기**에서 바로가기 메뉴에서 프로젝트 항목을 열고 **추가** , **모듈** 을 선택합니다.  
  
     **리소스 파일** 템플릿을 선택합니다.  
  
    > [!NOTE]  
    >  리소스 파일을 SharePoint 프로젝트 항목에 추가하여 배포 형식 속성을 사용할 수 있도록 설정합니다.  이 속성은 이 절차에서 이후에 필요합니다.  
  
2.  기본 언어 리소스 파일에 선택한 이름을 지정하고 .resx 확장명을 추가합니다\(예: MyAppResources.resx\).  
  
3.  1단계와 2단계를 반복하여 기본 언어와 지역화된 언어마다 하나씩 별도의 리소스 파일을 SharePoint 프로젝트 항목에 추가합니다.  
  
     지역화된 각 리소스 파일에 동일한 기본 이름을 사용하지만 문화권 ID를 추가합니다.  예를 들어, 독일어 지역화된 리소스의 이름을 MyAppResources.de\-DE.resx로 지정합니다.  
  
4.  각 리소스 파일을 열고 지역화된 문자열을 추가합니다.  각 파일에서 동일한 문자열을 사용합니다.  
  
5.  각 리소스 파일의 **배포 형식** 속성을 **AppGlobalResource** 로 변경하여 각 파일이 서버의 App\_GlobalResources 폴더에 배포되도록 합니다.  
  
6.  **포함된 소스**로 각 파일의 **빌드 작업** 속성의 값을 남겨 둡니다.  
  
     포함 리소스는 프로젝트의 DLL로 컴파일됩니다.  
  
7.  프로젝트를 빌드하여 리소스 위성 DLL을 만듭니다.  
  
8.  **패키지 디자이너**에서 **고급** 탭을 클릭하고 위성 어셈블리를 추가합니다.  
  
9. **위치** 상자에서 문화권 ID 폴더를 위치 경로에 추가합니다.\(예: de\-DE\\*Project Item Name*.resources.dll\).  
  
10. 솔루션에서 System.Web 어셈블리를 참조하지 않는 경우 이 어셈블리에 대한 참조를 추가하고 코드에서 <xref:System.Web>에 지시문을 추가합니다.  
  
11. UI 텍스트, 오류 및 메시지 텍스트와 같은 사용자에게 표시 되는 코드에서 모든 하드 코드 된 문자열을 찾습니다.  다음 구문을 사용하여 <xref:System.Web.HttpContext.GetGlobalResourceObject%2A> 메서드를 호출하여 바꿉니다.:  
  
    ```  
    HttpContext.GetGlobalResourceObject("Resource File Name", "String ID")  
    ```  
  
12. 프로젝트를 빌드하고 실행하려면 F5 키를 선택합니다.  
  
13. SharePoint에서 기본 표시 언어를 변경합니다.  
  
     지역화된 문자열이 응용 프로그램에 표시됩니다.  지역화된 리소스를 표시하려면 SharePoint 서버에 리소스 파일의 문화권과 일치하는 언어 팩이 설치되어 있어야 합니다.  
  
## 참고 항목  
 [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)   
 [방법: 기능 지역화](../sharepoint/how-to-localize-a-feature.md)   
 [방법: ASPX 태그 지역화](../sharepoint/how-to-localize-aspx-markup.md)   
 [방법: 리소스 파일 추가](../sharepoint/how-to-add-a-resource-file.md)  
  
  