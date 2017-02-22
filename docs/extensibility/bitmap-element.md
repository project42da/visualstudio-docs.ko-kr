---
title: "비트맵 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSCT XML 스키마 요소를 비트맵"
  - "비트맵 요소 (VSCT XML 스키마)"
ms.assetid: edcd7891-f4e7-416d-809d-5e2eed9f17e4
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# 비트맵 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

비트맵을 정의합니다. 비트맵 파일 또는 리소스에서 로드 됩니다.  
  
## 구문  
  
```  
<Bitmap guid="guidImages" href="images\MyImage.bmp" usedList="bmp1, bmp2, bmp3" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|guid|필수 요소. GUID\/ID 명령 식별자의 GUID입니다.<br /><br /> 비트맵에 대 한 guid 특성 모든 VSPackage 또는 다른 명령 그룹 연결입니다.  비트맵 정의에 고유 해야 하 고 다른 용도로 쓰일 수 없습니다.|  
|resID|ID는 GUID\/ID 명령 식별자입니다. ResID 또는 href 특성 중 하나는 필요 합니다.<br /><br /> ResID 명령 테이블을 병합 하는 동안 로드 하는 비트맵 스트립을 결정 하는 정수 리소스 ID입니다.  명령 테이블 로드 되 고, 리소스 ID로 지정 된 비트맵은 동일한 모듈의 리소스에서 로드 됩니다.|  
|usedList|ResID 특성이 있으면 경우 필요 합니다. 비트맵 스트립에서 사용 가능한 이미지를 선택합니다.|  
|href|비트맵에 대 한 경로입니다. ResID 또는 href 특성 중 하나는 필요 합니다.<br /><br /> 포함 경로 결과 이진 파일에 포함 된 지정 된 이미지 파일을 검색 합니다.  명령 테이블 병합 하는 동안 이미지는 복사 하 고 추가 리소스 조회 또는 부하 필요 하지 않습니다.  UsedList 특성이 없으면, 스트립에서 모든 이미지를 사용할 수 있습니다. **Note:**  이미지는.bmp,.png 및.gif를 포함 하는 여러 가지 형식 중 하나에 제공 될 수 있습니다.  이전 버전의 컴파일러는 알파 정보가 부분 투명도 대 한 32 비트 비트맵 이미지를 지원 하지 않습니다. 이러한 버전에 대 한 해결.png 형식을 사용 하는 것입니다.|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[비트맵 요소](../extensibility/bitmaps-element.md)|비트맵 요소를 그룹화합니다.|  
  
## 예제  
  
```  
<Bitmap guid="guidWidgetIcons" href="WidgetToolbarIcons_32.bmp" /> <Bitmap guid="guidWidgetIcons2" resID="IDBMP_WIDGETICONS" usedList="1, 2, 3, 4"/>  
```  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)