---
title: "Licenses processor error/warning: &lt;reason&gt; | Microsoft Docs"
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
  - "vs.tasklisterror.licx_generator_task"
ms.assetid: 85750198-7bd3-4936-b1eb-954dcc3ff573
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Licenses processor error/warning: &lt;reason&gt;
도구가 .licx 파일을 처리하는 동안 오류나 경고를 반환하면 오류 메시지나 경고 메시지가 표시됩니다.  빌드 프로세스의 일부로 프로젝트 시스템에서는 Licenses.licx 파일이 있으면 이 파일을 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 라이선스 관리자가 인식할 수 있는 이진 파일로 변환합니다.  변환은 in\-process 도구를 사용하여 이루어집니다.  
  
 오류나 경고는 주로 잘못된 .licx 파일로 인해 발생합니다.  .licx 파일을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]가 아닌 다른 프로그램에서 편집하거나 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 내에서 텍스트 편집기를 사용하여 편집하면 파일이 손상될 수 있습니다.  
  
 이러한 파일은 일반적으로 Windows Forms 디자이너와 Web Forms 디자이너에서 관리합니다.  
  
### 이 오류를 해결하려면  
  
1.  .licx 파일의 형식을 수정합니다.  
  
     오류는 이진 파일이 생성되지 않았으므로 빌드 프로세스가 실패함을 나타내고,  경고는 정보를 제공하기 위한 것입니다.  
  
## 참고 항목  
 [File Types and File Extensions in Visual Basic and Visual C\#](http://msdn.microsoft.com/ko-kr/f793852c-da06-4d52-a826-65f635844772)