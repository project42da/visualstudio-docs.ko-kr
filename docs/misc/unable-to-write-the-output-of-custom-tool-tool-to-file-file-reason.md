---
title: "Unable to write the output of custom tool &#39;tool&#39; to file &#39;file&#39;. &lt;reason&gt; | Microsoft Docs"
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
  - "vs.tasklisterror.cannot_write_gen_output"
ms.assetid: eafcee9e-186b-4019-9042-8d8f9fc0925a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Unable to write the output of custom tool &#39;tool&#39; to file &#39;file&#39;. &lt;reason&gt;
프로젝트 시스템에서 사용자 지정 도구의 출력을 지정한 파일에 쓸 수 없습니다.  
  
 사용자 지정 도구의 입력 파일 이름을 변경하지 않았으면 사용자 지정 도구의 출력을 같은 파일에 쓸 수 있습니다.  이 오류는 생성된 출력이 디스크에 잠겨 있을 때 발생합니다.  
  
 **이 오류를 해결하려면**  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 시작하고 해당 파일을 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **사용자 지정 도구 실행**을 선택하여 사용자 지정 도구를 다시 실행합니다.  
  
     프로젝트 시스템에서 파일을 업데이트할 수 없으므로 생성된 파일은 최신이 아닐 수 있습니다.