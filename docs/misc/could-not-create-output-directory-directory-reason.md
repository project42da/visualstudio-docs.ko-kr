---
title: "Could not create output directory &#39;directory&#39;. &lt;reason&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.cannot_create_output_dir"
ms.assetid: b4d1d19f-f582-49d0-a9a9-d3f4ce0a447b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Could not create output directory &#39;directory&#39;. &lt;reason&gt;
프로젝트 시스템에서 프로젝트 디렉터리를 만들 수 없습니다.  
  
 프로젝트 시스템에서 프로젝트를 연 즉시 모든 출력 디렉터리를 만들려고 합니다.  다음은 프로젝트 시스템에서 만든 출력 디렉터리 목록입니다.  
  
 *projectfolder*\\obj\\`configname`  
 임시 구성별 출력 디렉터리  
  
 *projectfolder*\\obj\\`configname`\\temp  
 컴파일러에 사용되는 작업 영역  
  
 *projectfolder*\\obj\\`configname`\\temppe  
 디자인 타임에 디자이너가 사용하는 임시 어셈블리가 이 디렉터리에 만들어집니다.  
  
 outputdir  
 출력 경로 속성에 지정된 디렉터리입니다.  자세한 내용은 [프로젝트 디자이너, 빌드 페이지\(C\#\)](../ide/reference/build-page-project-designer-csharp.md)를 참조하십시오.  
  
 obj 폴더 아래에 이러한 디렉터리를 만들 수 없는 가장 일반적인 이유는 디렉터리 이름이 MAX\_PATH 한계를 초과했기 때문입니다.  
  
 그 다음 일반적인 이유로는 사용 권한 거부와 디스크 공간 부족이 있습니다.  
  
 **이 오류를 해결하려면**  
  
-   경로가 너무 길면 프로젝트 위치를 변경하거나 프로젝트 구성 이름을 짧게 만듭니다.  
  
     이 오류가 발생하면 빌드 프로세스는 실패합니다.  
  
## 참고 항목  
 [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)