---
title: "Icon 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSCT XML 스키마 요소 아이콘"
  - "Icon 요소 (VSCT XML 스키마)"
ms.assetid: 73c58fe3-d53c-4f4e-b025-29567c6cbb7c
caps.latest.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 5
---
# Icon 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

아이콘 태그의 guid 특성에는 정의 된 비트맵의 guid입니다.  Id 특성 비트맵 스트립에서 슬롯을 선택합니다. 이 요소는 선택적입니다.  이 요소를 생략 하면 값 **guidOfficeIcon:msotcidNoIcon** 암시 됩니다.  
  
## 구문  
  
```  
<Icon guid="guidImages" id="bmpPic1" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|guid|필수 요소. 정의 된 비트맵의 guid입니다.|  
|ID|필수 요소. 비트맵 스트립에서 슬롯을 선택합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|없음|없음|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[단추 요소](../extensibility/buttons-element.md)||  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)