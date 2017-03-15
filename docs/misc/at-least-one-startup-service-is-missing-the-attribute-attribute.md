---
title: "At least one startup service is missing the &#39;attribute&#39; attribute | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.projfile_missing_ss_attrib"
ms.assetid: 987c42dc-4394-4b07-b7fa-a8e7afc6fdfb
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# At least one startup service is missing the &#39;attribute&#39; attribute
시작 서비스에 ID 특성이 있어야 하는데 `<Service>` 요소에서 이 속성을 찾을 수 없습니다.  예를 들면 다음과 같습니다.  
  
```  
<Service ID="{0000-0000-0000-00000000-000000000000}"/>  
```  
  
 이는 프로젝트 파일이 손상되었음을 나타냅니다.  
  
 이 오류는 주로 프로젝트 파일을 직접 편집했을 때 발생합니다.  
  
 **이 오류를 해결하려면**  
  
-   프로젝트 파일을 저장합니다.  
  
     손상된 부분은 쓰여지지 않으므로 다음에 프로젝트를 열 때는 이 오류가 발생하지 않습니다.  
  
## 참고 항목  
 [NIB: Project Properties \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)