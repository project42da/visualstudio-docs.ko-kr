---
title: "기타 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.newfile"
  - "VS.OpenWith"
  - "MiscellaneousFilesProject"
helpviewer_keywords: 
  - "솔루션, 기타 파일"
  - "빌드[Visual Studio], 기타 파일"
  - "독립 실행형 파일"
  - "솔루션 탐색기, 기타 파일"
  - "기타 파일 폴더"
  - "파일[Visual Studio], 컨테이너 외부"
  - "파일[Visual Studio], 기타 파일 폴더"
ms.assetid: 5b96640b-8efe-48a4-8d0a-1ae3f9587e44
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 기타 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 편집기를 사용하여 프로젝트 또는 솔루션과는 독립적으로 파일에 대해 작업을 수행할 수 있습니다.  솔루션이 열려 있는 상태에서 솔루션이나 프로젝트에 파일을 추가하지 않고 파일을 열어 수정할 수 있습니다.  컨테이너와는 독립적으로 작업을 수행하려는 파일을 기타 파일이라고 합니다.  기타 파일은 솔루션 및 프로젝트 외부에 있는 파일로, 빌드에 포함되지 않으며 소스 제어에서 사용되는 솔루션에 포함될 수 없습니다.  
  
 컨테이너와는 별도로 파일을 여는 것은 여러 가지 이유로 유용합니다.  프로젝트 기반 솔루션을 개발하는 동안 볼 수 있기를 원하지만 솔루션 개발에는 포함되지 않는 파일이 있을 수 있습니다.  일반적인 예제로는 개발 메모 또는 지침, 데이터베이스 스키마 및 코드 클립을 들 수 있습니다.  또한 독립 실행형 파일을 만들 수도 있습니다.  
  
 ![솔루션 프로젝트](~/docs/ide/reference/media/projects_solutions_misc.gif "Projects\_Solutions\_Misc")  
  
 기타 파일 폴더 옵션이 활성화되면 솔루션 탐색기에는 파일에 대한 기타 파일 폴더가 표시될 수 있습니다.  이 옵션은 [옵션 대화 상자, 환경, 문서](../../ide/reference/documents-environment-options-dialog-box.md)에서 설정될 수 있습니다.  관련 옵션이 활성화되지 않으면 기타 파일이 닫힌 후에 파일은 특정 솔루션이나 프로젝트와 연관되지 않습니다.  
  
 기타 파일 폴더는 파일을 링크로 나타냅니다.  이 폴더는 솔루션에 속하지 않지만, 솔루션을 마지막으로 닫았을 때 열었던 일부 또는 전체 기타 파일은 솔루션을 열 때 폴더에 대한 설정에 따라 다시 열립니다.  
  
> [!NOTE]
>  .zip 및 .doc 파일과 같이 IDE에서 수정할 수 없는 파일은 기타 파일 폴더에 나타나지 않습니다.  IDE에서는 외부 편집기를 통해서만 수정할 수 있는 파일을 추적하지 않습니다.  
  
## IDE에서 사용할 수 있는 명령  
 기타 파일에 포함된 메뉴, 도구 모음 및 명령은 열린 파일의 형식에 따라 다릅니다.  예를 들어, 텍스트 파일을 열면 텍스트 편집기 도구 모음이 나타나며 해당 명령을 사용할 수 있습니다.  XML 스키마 파일을 열면 XML 스키마 도구 모음이 나타납니다.  XML 스키마를 편집하는 동안에는 텍스트 편집기의 도구 모음 명령이나 도구 모음 자체를 사용할 수 없습니다.  XML 스키마가 활성 창이므로 현재의 선택 영역 컨텍스트를 포함합니다.  프로젝트 파일과 기타 파일 간을 전환하면 프로젝트 관련 명령은 모두 사라지고 기타 파일과 직접 연관된 명령만 나타납니다.  
  
## 폴더 표시 옵션  
 기타 파일을 열지 않은 경우에도 Miscellaneous Folder가 나타나도록 이 폴더에 대한 표시 옵션을 설정할 수 있습니다.  솔루션 파일은 기타 파일 목록을 영구히 관리하지 않으며  가장 최근에 각 사용자가 사용한 파일 목록을 저장할 수 있도록 하는 선택적 기능을 사용합니다.  
  
## 참고 항목  
 [솔루션 및 프로젝트](../../ide/solutions-and-projects-in-visual-studio.md)   
 [옵션 대화 상자, 환경, 문서](../../ide/reference/documents-environment-options-dialog-box.md)