---
title: "Resources processor error/warning: &lt;reason&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.resx_generator_task"
ms.assetid: eb9a1bd0-7e63-4a2b-ad37-54f6e67d9b5a
caps.latest.revision: 7
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Resources processor error/warning: &lt;reason&gt;
도구가 .resx 파일을 처리하는 동안 오류나 경고를 반환하면 오류 메시지나 경고 메시지가 표시됩니다.  빌드 프로세스의 일부로 프로젝트 시스템에서는 각 .resx 파일을 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 리소스 관리자가 인식할 수 있는 이진 파일로 변환합니다.  변환은 in\-process 도구를 사용하여 이루어집니다.  
  
 오류나 경고는 주로 잘못된 .resx 파일로 인해 발생합니다.  .resx 파일을 Visual Studio가 아닌 다른 프로그램에서 편집하거나 Visual Studio 내에서 텍스트 편집기를 사용하여 편집하면 파일이 손상될 수 있습니다.  
  
 이러한 파일은 일반적으로 Windows Forms 디자이너와 Web Forms 디자이너에서 관리합니다.  
  
### 이 오류를 해결하려면  
  
1.  .resx 파일의 형식을 수정합니다.  
  
     오류는 이진 파일이 생성되지 않았으므로 빌드 프로세스가 실패함을 나타내고,  경고는 정보를 제공하기 위한 것입니다.  
  
## 참고 항목  
 [Resources in .Resx File Format](http://msdn.microsoft.com/ko-kr/0c476133-87e4-47e8-b0ef-4b88f4ef3dc5)