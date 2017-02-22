---
title: "방법: 템플릿 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio 템플릿, 문제 해결"
ms.assetid: 3e577ad2-f725-4c11-93b3-477f2404ec81
caps.latest.revision: 10
caps.handback.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: 템플릿 문제 해결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

템플릿을 개발 환경에 로드할 수 없는 경우 몇 가지 방법으로 문제를 해결할 수 있습니다.  
  
## .vstemplate 파일의 유효성 검사  
 템플릿의 .vstemplate 파일이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 템플릿 스키마를 따르지 않으면 해당 템플릿은 **새 프로젝트** 대화 상자에 나타나지 않을 수 있습니다.  
  
#### .vstemplate 파일의 유효성을 검사하려면  
  
1.  템플릿을 포함하는 .zip 파일을 찾습니다.  
  
2.  .zip 파일의 압축을 풉니다.  
  
3.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 **파일** 메뉴에서 **열기**를 클릭한 다음 **파일**을 클릭합니다.  
  
4.  해당 템플릿의 .vstemplate 파일을 선택한 다음 **열기**를 클릭합니다.  
  
5.  .vstemplate 파일의 XML이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 템플릿 스키마를 따르는지 확인합니다.  .vstemplate 스키마에 대한 자세한 내용은 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)를 참조하십시오.  
  
    > [!NOTE]
    >  .vstemplate 파일을 작성하는 동안 IntelliSense 지원을 받으려면 `VSTemplate` 요소에 `xmlns` 특성을 추가하고 이 특성에 http:\/\/schemas.microsoft.com\/developer\/vstemplate\/2005 값을 할당합니다.  
  
6.  .vstemplate 파일을 저장한 다음 닫습니다.  
  
7.  템플릿에 포함된 파일을 선택하고 마우스 오른쪽 단추를 클릭한 다음 **보내기**를 선택하고 **압축\(ZIP\) 폴더**를 클릭합니다.  선택한 파일이 .zip 파일로 압축됩니다.  
  
8.  새 .zip 파일을 이전 .zip 파일과 같은 디렉터리에 넣습니다.  
  
9. 추출된 템플릿 파일과 이전 템플릿 .zip 파일을 삭제합니다.  
  
## 이벤트 로그 모니터링  
 템플릿 .zip 파일을 처리할 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 로그 오류가 발생했습니다.  템플릿이 **새 프로젝트** 대화 상자에 예상대로 표시되지 않으면 **이벤트 뷰어**를 사용하여 문제를 해결할 수 있습니다.  
  
#### 이벤트 뷰어에서 템플릿 오류를 찾으려면  
  
1.  Windows에서 **시작**, **제어판**을 차례로 클릭한 다음 **관리 도구**, **이벤트 뷰어**를 차례로 두 번 클릭합니다.  
  
2.  왼쪽 창에서 **응용 프로그램**을 클릭합니다.  
  
3.  **소스** 값이 `Visual Studio - VsTemplate`인 이벤트를 찾습니다.  
  
4.  오류를 볼 템플릿 이벤트를 두 번 클릭합니다.  
  
## 참고 항목  
 [템플릿 사용자 지정](../ide/customizing-project-and-item-templates.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)