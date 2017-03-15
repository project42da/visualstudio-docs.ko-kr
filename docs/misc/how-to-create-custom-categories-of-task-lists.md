---
title: "방법: 작업 목록의 사용자 지정 범주 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "작업 목록, 사용자 지정 범주"
ms.assetid: 5e4ac1b1-9afb-46c5-9dcc-6cab9c5ceee8
caps.latest.revision: 9
caps.handback.revision: 9
manager: "douge"
---
# 방법: 작업 목록의 사용자 지정 범주 만들기
작업의 사용자 지정 범주에 작업이 표시 되는 방법을 제어할 제공의  **작업 목록** 창.  
  
 다음과 같은 경우에 사용자 지정 작업 종류를 구현 합니다.  
  
-   표시 되는 범주 컨트롤 \(범주 목록에서 정렬 됨\) 하 여 합니다.  
  
-   사용자 범주에 다른 작업 간에 정렬 하지 않고 정렬 하려는 작업의 여러 하위 범주가 있습니다.  
  
-   작업을 표시할 사용자 지정 보기를 만들려고 합니다.  
  
    > [!NOTE]
    >  사용자 지정 범주를 실제로 구현 하지 않고 사용자 지정 범주에 비슷한 효과 얻을 수 있습니다.  예를 들어, 구현 하 여 범주 또는 하위 범주에 대 한 비트맵을 표시할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2.ImageList%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2.ImageListIndex%2A>.  작업 공급자의 목록을 제공 하 고 각 작업 인덱스 목록으로 제공 합니다.  
  
 사용자 지정 범주를 만들 수 있는  **작업 목록**, 등록은  **작업 목록** 다음 절차를 사용 하 여.  
  
### 사용자 지정 작업 목록 범주를 등록 하려면  
  
-   호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RegisterCustomCategory%2A> 작업 목록에 사용자 지정 범주를 등록 합니다.  
  
     각 사용자 지정 범주에 지정 된 고유 GUID를 가져야 합니다는 `guidCat` 매개 변수.  에 있는 `dwSortOrder` 매개 변수를 위치의 \(목록이 범주별으로 정렬 되는 경우\)를 정렬 합니다.이 범주는 위치를 제공 합니다.  이 메서드를 다음 실제 정렬을 배치 큰 범주 목록에서 사용자 지정 범주를 반환합니다.  
  
     정렬에 정의 된 기본 제공 작업 범주에 대 한 주문은 <xref:Microsoft.VisualStudio.Shell.Interop.VSTASKCATEGORY> 열거형을 다음 테이블에 있습니다.  
  
    |범주|값|설명|  
    |--------|-------|--------|  
    |CAT\_ALL|1|실제 범주입니다.  작업 목록 보기에서 모든 작업을 표시 하도록 허용 하는 데 사용 되는  **작업 목록**.|  
    |CAT\_BUILDCOMPILE|10|오류, 경고 및 배포 오류를 빌드하십시오.|  
    |CAT\_COMMENTS|20|"TODO"와 같은 특수 한 주석을 생성 하는 작업 "실행 취소" 또는 "해킹"|  
    |CAT\_CODESENSE|30|소스 코드를 입력할 때 발생 하는 오류입니다.|  
    |CAT\_SHORTCUTS|40|코드로 바로 가기입니다.|  
    |CAT\_USER|50|사용자가 입력 하는 작업입니다.|  
    |CAT\_MISC|60|Vspackages에 추가 할 수도 있습니다 기타 작업은  **작업 목록**.|  
    |CAT\_HTML|70|웹 페이지 개발에 관련 된 작업입니다.|  
  
     예를 들어, CAT\_CODESENSE와 CAT\_SHORTCUTS 사이의 범주를 포함 하려면 정렬 순서 31 값에 전달할 수 있습니다.  그러나, 31 값은 다른 사용자 정의 작업 범주 공급자가 이미 사용 될 수 있으므로  **작업 목록** 다음 빈 슬롯에 대 한 작업 종류를 지정 합니다.  이 값이 다시에 전달 되는 `pCat` 매개 변수.  
  
### 사용자 지정 작업 목록 범주 등록을  
  
-   호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.UnregisterCustomCategory%2A> 사용자 지정 범주를 등록 취소 합니다.  
  
## 참고 항목  
 [사용자 지정 작업 목록 보기 만들기](../misc/creating-custom-task-list-views.md)