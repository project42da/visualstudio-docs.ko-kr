---
title: "방법: 뷰와 XML 편집기 간 전환 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cb69fbbd-d99c-439e-9498-5df9050f8df0
caps.latest.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 2
---
# 방법: 뷰와 XML 편집기 간 전환
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 XML 스키마 디자이너\(XSD 디자이너\) 뷰와 XML 편집기 간을 전환하는 방법을 보여 줍니다.이 예제에서는 [구매 주문 스키마](../xml-tools/sample-xsd-file-simple-schema.md)를 사용합니다.  
  
### 뷰와 XML 편집기 사이를 전환하려면  
  
1.  새 XML 스키마 파일을 만들고 편집하려면 [방법: XSD 스키마 파일 만들기 및 편집](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)의 단계를 수행합니다.  
  
2.  XML 편집기에서 XML 스키마 디자이너로 전환하려면 XML 편집기의 아무 곳이나 마우스 오른쪽 단추로 클릭하고 **뷰 디자이너**를 선택합니다.  
  
3.  워터마크를 사용하여 그래프 뷰로 전환하려면 시작 뷰에서 **그래프 뷰를 사용하여 노드 간 관계 보기** 링크를 클릭합니다.  
  
4.  XML 스키마 탐색기에서 그래프 뷰로 `USAddress` 노드를 끌어 옵니다.그래프 뷰에서 `USAddress` 노드를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **콘텐츠 모델 뷰로 표시**를 선택합니다.  
  
     `USAddress` 노드 정보가 있는 콘텐츠 모델 뷰가 나타납니다.  
  
5.  도구 모음을 사용하여 콘텐츠 모델 뷰에서 시작 뷰로 전환하려면 XSD 도구 모음에서 시작 뷰 단추를 클릭합니다.  
  
6.  바로 가기 키를 사용하여 뷰 간을 전환하려면 시작 뷰의 경우 Ctrl\+1, 그래프 뷰의 경우 Ctrl\+2, 콘텐츠 모델 뷰의 경우 Ctrl\+3을 누릅니다.  
  
7.  콘텐츠 모델 뷰에서 XML 편집기로 이동하려면 노드를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **코드 보기**를 선택합니다.