---
title: "경고: 같은 종속 어셈블리의 다른 버전 사이에서 충돌이 발생했습니다. | Microsoft Docs"
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
  - "ResolveAssemblyReference.SuggestedRedirects"
ms.assetid: fd14a789-bbdf-46c7-bcd3-9d3165adf96d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 경고: 같은 종속 어셈블리의 다른 버전 사이에서 충돌이 발생했습니다.
이 경고는 프로젝트의 종속성 그래프에 다른 버전의 동일한 어셈블리에 대한 참조가 포함되어 있을 경우 나타납니다.  
  
 app.config 파일이 있으면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 이 파일에 바인딩 리디렉션을 추가할 수 있습니다.  바인딩 리디렉션은 강제로 모든 어셈블리 참조를 가장 높은 버전의 어셈블리로 리디렉션합니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 리디렉션 정보를 app.config에 저장합니다.  바인딩 리디렉션을 사용하면 이 경고가 더 이상 나타나지 않습니다.  
  
 바인딩 리디렉션을 추가하지 않으면 프로젝트에서 이전과 마찬가지로 계속 동일한 버전의 어셈블리를 참조하지만.  이 경고는 계속 나타납니다.  
  
### 이 오류를 해결하려면  
  
-   "app.config 파일에 바인딩 리디렉션 레코드를 추가하여 충돌을 해결하시겠습니까?"라는 메시지가 나타나면 경고를 두 번 클릭한 다음 "예"를 선택합니다.