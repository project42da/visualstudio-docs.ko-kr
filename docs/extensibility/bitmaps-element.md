---
title: "비트맵 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSCT XML 스키마 요소를 비트맵"
  - "비트맵 요소 (VSCT XML 스키마)"
ms.assetid: 74652e1b-fcfa-421b-aa9f-fbc081d3b476
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 비트맵 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[비트맵 요소](../extensibility/bitmap-element.md) 요소를 그룹화합니다.  
  
## 구문  
  
```  
<Bitmaps>  
  <Bitmap>... </Bitmap>  
  <Bitmap>... </Bitmap>  
</Bitmaps>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[Bitmaps Element](../extensibility/bitmaps-element.md)|비트맵 요소를 그룹화합니다.|  
|[비트맵 요소](../extensibility/bitmap-element.md)|비트맵을 정의합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[Commands 요소](../extensibility/commands-element.md)|VSPackage 도구 모음에 있는 명령의 컬렉션을 나타냅니다.|  
  
## 예제  
  
```  
<Bitmaps> <Bitmap guid="guidWidgetIcons" href="WidgetToolbarIcons_32.bmp" /> <Bitmap guid="guidWidgetIcons2" resID="IDBMP_WIDGETICONS" usedList="1, 2, 3, 4"/> </Bitmaps>  
```  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)