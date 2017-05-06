---
title: "방법: 기능 지역화"
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
  - "기능[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 지역화"
ms.assetid: 66a0b389-1f71-421f-9817-a19840765d83
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# 방법: 기능 지역화
  기본적으로 기능 제목 및 설명에는 하드 코드된 문자열 값이 사용됩니다.  기능 제목 및 설명을 지역화하려면 지역화된 리소스를 참조하는 식으로 문자열을 바꿉니다.  
  
## 기능 지역화  
  
#### 기능을 지역화하려면  
  
1.  **솔루션 탐색기**에서 **Feature1** 노드에 대한 바로 가기 메뉴를 열고 **기능 리소스 추가**를 선택합니다.  
  
2.  **리소스 추가** 대화 상자에서, 기본 언어 기능 리소스 파일에 대한 문화권으로 **고정 언어** 를 목록에서 선택합니다  
  
3.  지역화된 언어마다 이전 단계를 반복하고 지역화된 기능 리소스 파일에 대한 언어를 선택합니다.  
  
     기본 언어와 지원할 지역화된 언어마다 하나씩 별도의 기능 리소스 파일을 만듭니다.  
  
4.  리소스 편집기에서 각 리소스 파일을 연 다음, 모든 문자열 ID 및 그들의 값을 입력합니다.  
  
     예를 들어, 기본 기능 리소스 파일에서 내 기능 제목의 값과 함께 제목의 문자열 ID를 입력하고 내 기능 설명의 값과 함께 설명의 두 번째 문자열 ID를 입력합니다.  지역화된 각 리소스 파일에 대해 기본 기능 리소스에서 사용된 동일한 문자열 ID를 사용하지만 값의 지역화된 문자열을 입력합니다.  
  
5.  모든 리소스 값을 입력 한 후, Feature1.feature 기능과 같은 기능에 대한 바로 가기 메뉴를 연 다음 **뷰 디자이너** 를 선택하여 기능 디자이너에서의 기능을 엽니다.  
  
6.  기능에서 **제목** 및 **설명** 필드를 지역화하려면 다음 형식을 사용하여 해당 상자에 값을 입력합니다.  
  
     `$Resources:` *String ID*  
  
     예를 들어, **기능 제목** 상자에 $Resources:Title을 입력하고 **기능 설명** 상자에 $Resources:Description을 입력합니다.  
  
     문자열 ID는 리소스 파일에서 사용되는 것과 일치해야 합니다.  
  
7.  프로젝트를 빌드하고 실행하려면 F5 키를 선택합니다.  
  
8.  SharePoint의 **사이트 작업** 메뉴에서 **사이트 설정**을 클릭한 다음 **사이트 작업** 섹션에서 **사이트 기능 관리** 링크를 클릭합니다.  
  
9. SharePoint에서 기본 표시 언어를 변경합니다.  
  
     지역화된 기능 제목과 설명이 응용 프로그램에 표시됩니다.  지역화된 리소스를 표시하려면 SharePoint 서버에 리소스 파일의 문화권과 일치하는 언어 팩이 설치되어 있어야 합니다.  
  
## 참고 항목  
 [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)   
 [방법: 리소스 파일 추가](../sharepoint/how-to-add-a-resource-file.md)   
 [방법: ASPX 태그 지역화](../sharepoint/how-to-localize-aspx-markup.md)   
 [방법: 코드 지역화](../sharepoint/how-to-localize-code.md)  
  
  