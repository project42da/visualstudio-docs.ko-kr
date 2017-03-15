---
title: "A failure occurred writing to the licenses file | Microsoft Docs"
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
  - "vs.tasklisterror.fail_writing_licenses_file"
ms.assetid: 7ea1e2ac-fc94-4d53-8ce9-2ae31bcba85d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# A failure occurred writing to the licenses file
프로젝트 시스템에서 변환된 파일에 쓸 수 없습니다.  라이선스 준비 과정의 일부로 프로젝트 시스템에서는 텍스트 .licx 파일을 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 라이선스 시스템에서 인식할 수 있는 이진 라이선스 파일로 변환합니다.  
  
 이 오류가 발생하는 이유는 장치에 남은 디스크 공간이 없거나 파일 이름이 MAX\_PATH 한계를 초과했기 때문입니다.  
  
 **이 오류를 해결하려면**  
  
-   절대 경로 이름이 짧은 다른 폴더로 프로젝트를 옮기거나 출력 파일 이름을 짧게 만듭니다.  
  
     이 오류가 발생하면 빌드 프로세스는 실패합니다.  
  
## 참고 항목  
 [방법: 구성 요소 및 컨트롤 라이센스](../Topic/How%20to:%20License%20Components%20and%20Controls.md)