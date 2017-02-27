---
title: "정렬, 필터링 및 그룹화(XML 스키마 탐색기) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4a914de0-9ffc-4526-9603-92e460e52513
caps.latest.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 2
---
# 정렬, 필터링 및 그룹화(XML 스키마 탐색기)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 XML 스키마 탐색기 도구 모음의 **정렬, 필터링 및 그룹화 옵션** 메뉴에서 사용할 수 있는 옵션에 대해 설명합니다.  
  
## 필터 옵션  
 사용할 수 있는 필터 옵션은 다음과 같습니다.기본적으로 **네임스페이스 표시** 및 **스키마 파일 표시** 옵션이 선택되어 있습니다.  
  
-   **네임스페이스 표시**  
  
-   **스키마 파일 표시**  
  
-   **작성자 표시\(sequence\/choice\/all\)**  
  
## 정렬 옵션  
 사용할 수 있는 정렬 옵션은 다음과 같습니다.기본값은 **형식으로 정렬**입니다.정렬 기준 옵션은 파일 및 네임스페이스에 적용되지 않습니다.  
  
-   **형식으로 정렬**  
  
-   **이름으로 정렬**  
  
-   **문서 순서**  
  
### 형식으로 정렬  
 **형식으로 정렬** 옵션을 선택하면 전역 노드가 다음 순서로 정렬됩니다.그런 다음 노드가 각 그룹 내에서 알파벳순으로 정렬됩니다.  
  
1.  `import` 노드  
  
2.  `include` 노드  
  
3.  `redefine` 노드  
  
4.  `attribute` 노드  
  
5.  `attributeGroup` 노드  
  
6.  `complexType` 노드  
  
7.  `simpleType` 노드  
  
8.  `element` 노드  
  
9. `group` 노드  
  
### 이름으로 정렬  
 **이름으로 정렬** 옵션을 선택하면 전역 노드가 다음 순서로 정렬됩니다.  
  
1.  `import` 노드\(네임스페이스의 알파벳 순서로 정렬\)  
  
2.  `include` 노드\(`schemaLocation` 특성의 알파벳 순서로 정렬\)  
  
3.  `redefine` 노드\(`schemaLocation` 특성의 알파벳 순서로 정렬\)  
  
4.  기타 전역 노드\(알파벳 순서로 정렬\)  
  
### 문서 순서  
 **문서 순서** 옵션은 **스키마 파일 표시** 옵션을 선택한 경우 사용할 수 있습니다.**문서 순서**를 선택하면 전역 노드가 스키마 파일에 나타나는 순서대로 표시됩니다.  
  
## 정렬\/필터 옵션 유지  
 설정이 변경될 때 솔루션 또는 파일이 열려 있는지 여부에 상관없이 정렬, 필터링 및 그룹화 옵션이 각 사용자에 대한 레지스트리에 저장됩니다.