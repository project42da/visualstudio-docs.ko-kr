---
title: "대규모 프로젝트 빌드 시 메모리의 효율적인 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "캐싱(MSBuild)"
  - "메모리 사용(MSBuild)"
  - "msbuild, 효율적인 메모리 사용 대형 트리 빌드"
ms.assetid: 853a21ed-69f7-4817-af00-57f73e2c74b5
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 대규모 프로젝트 빌드 시 메모리의 효율적인 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

대규모 프로젝트는 종종 많은 하위 프로젝트와 다른 종속성을 포함하고 있고 빌드 시 많은 시스템 메모리를 사용할 수 있습니다.  사용 가능한 시스템 메모리가 줄어들면 시스템 성능도 저하될 수 있습니다.  이전 버전의 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 프로젝트가 메모리에 유지되었고, 3.5 버전에서는 프로젝트가 제거되었지만 이후 검색을 위해 빌드 결과가 캐시에 유지되었습니다.  
  
 4.0 버전에서는 이러한 메모리 관리를 자동으로 처리하므로, 프로젝트에서 `UnloadProjectsOnCompletion` 및 `UseResultsCache`와 같은 속성을 사용할 필요가 없습니다.  
  
## 참고 항목  
 [병렬로 여러 프로젝트 빌드](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)