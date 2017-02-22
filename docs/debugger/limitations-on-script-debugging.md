---
title: "스크립트 디버깅의 제한 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ASPX 중단점 매핑, 제한 사항"
  - "중단점 매핑, 제한 사항"
  - "스크립트 디버깅, 제한 사항"
ms.assetid: 280eead5-693c-47af-967f-dfe9d23f84db
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 스크립트 디버깅의 제한 사항
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]는 클라이언트 쪽 스크립트의 디버깅을 지원하며, 여기에는 이 항목의 제한 사항이 적용됩니다.  
  
## 클라이언트 쪽 스크립트를 사용하는 중단점 매핑에 대한 제한 사항  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하면 런타임에 클라이언트 쪽 파일로 변환되는 서버 쪽 ASPX 또는 HTML 파일에서 중단점을 설정할 수 있습니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]는 서버 쪽 파일의 중단점을 클라이언트 쪽 파일의 해당 중단점에 매핑하며, 여기에는 다음과 같은 제한이 적용됩니다.  
  
-   중단점은 `<script>` 블록 내에서 설정되어야 합니다.  인라인 스크립트 또는 `<% %>` 블록에 있는 중단점은 매핑할 수 없습니다.  
  
-   페이지의 브라우저 URL에는 페이지 이름이 포함되어야 합니다.  예를 들면 http:\/\/microsoft.com\/default.apsx와 같이 사용할 수 있습니다.  중단점 매핑은 http:\/\/microsoft.com 등의 주소에서 기본 페이지로의 리디렉션을 인식할 수 없습니다.  
  
-   중단점은 ASPX 컨트롤\(ascx\) 파일, 마스터 페이지 또는 해당 페이지에 포함된 다른 파일에서가 아니라 브라우저 URL에 지정된 페이지에서 설정되어야 합니다.  포함된 페이지에서 설정된 중단점은 매핑할 수 없습니다.  
  
-   `<script defer=true>` 블록에서 설정된 중단점은 매핑할 수 없습니다.  
  
-   `<script id="">` 블록에서 설정된 중단점의 경우 중단점 매핑에서 `id` 특성이 무시됩니다.  
  
## 중단점 매핑 및 중복된 줄  
 서버 쪽 및 클라이언트 쪽 스크립트에서 해당하는 위치를 찾기 위해 중단점 매핑 알고리즘은 각 줄의 코드를 검사합니다.  이 알고리즘에서는 각 줄이 고유하다고 가정합니다.  두 개 이상의 줄에 같은 코드가 포함된 경우 이 중복된 줄 중 하나에 중단점을 설정하면 중단점 매핑 알고리즘이 클라이언트 쪽 파일에서 다른 중복된 줄을 잘못 선택할 수 있습니다.  이 문제를 방지하려면 중단점을 설정한 줄에 주석을 추가합니다.  예를 들면 다음과 같습니다.  
  
```  
i++ ;  
i ++; // I added a comment, so this line is now unique  
i ++;  
```