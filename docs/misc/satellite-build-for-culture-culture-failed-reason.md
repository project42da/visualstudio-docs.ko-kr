---
title: "Satellite build for culture &#39;culture&#39; failed. &lt;reason&gt; | Microsoft Docs"
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
  - "vs.tasklisterror.satellite_build_failed"
ms.assetid: c97c589f-cf4d-4f6b-941a-7526a1091fce
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Satellite build for culture &#39;culture&#39; failed. &lt;reason&gt;
특정 culture에 대한 위성 어셈블리를 빌드할 수 없습니다.  이 오류가 발생하면 빌드 프로세스는 실패합니다.  
  
 이 오류는 다음 두 가지 이유로 인해 나타납니다.  
  
1.  ALINK.EXE가 시스템에 설치되어 있지 않습니다.  
  
2.  ALINK.EXE가 실패했지만 확장 오류 정보를 반환하지 않았습니다.  
  
 **이 오류를 해결하려면**  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 설치하거나 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]만 다시 설치합니다.  
  
-   \<reason\>이 "어셈블리 링커를 시작할 수 없습니다.  파일이 있습니다."로 보고되면 파일이 생성된 Temp 폴더\(예: C:\\Documents and Settings\\\<user\>\\Local Settings\\Temp\)를 비웁니다.  
  
## 참고 항목  
 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)