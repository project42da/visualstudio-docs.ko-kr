---
title: "빌드된 출력을 웹에 복사할 수 없습니다. | Microsoft Docs"
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
  - "vs.tasklisterror.cantcopyoutputstoweb"
ms.assetid: 59cf714b-cf7d-4df9-81ae-d3254969d5bc
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 빌드된 출력을 웹에 복사할 수 없습니다.
프로젝트 시스템에서 하나 이상의 빌드 출력 파일\(예: 빌드된 DLL, PDB 또는 위성 어셈블리\)을 웹 서버에 복사할 수 없습니다.  
  
 이 오류는 하나 이상의 빌드 출력 파일이 웹 서버에 복사되지 않았음을 나타냅니다.  
  
 일반적으로 빌드의 출력 파일이 잠겨 있거나 서버에서 읽기 전용인 경우에 이 오류가 발생합니다. 서버에서 파일이 잠겨 있는 경우는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 런타임이 현재 서버에 있는 어셈블리, 위성 또는 디버그 기호를 올바르게 복사하지 않았음을 의미합니다.  
  
 또한 서버의 디스크 공간이 부족하거나 네트워크 문제로 인해 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 파일을 웹에 업로드하지 못하는 경우일 수도 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  디스크 공간을 확인하세요.  
  
2.  파일이 잠긴 경우 웹 서버를 다시 시작하여 영향받은 파일의 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 잠금을 해제하세요.  
  
## 참고 항목  
 [PDB Files](http://msdn.microsoft.com/ko-kr/1761c84e-8c2c-4632-9649-b5f99964ed3f)