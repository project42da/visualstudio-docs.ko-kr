---
title: "사용자 지정 문서를 저장합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "지 속성, 사용자 지정 문서 저장"
  - "프로젝트 [Visual Studio SDK] 사용자 지정 문서 저장"
  - "사용자 지정 문서를 저장 하는 편집기 [Visual Studio SDK]"
ms.assetid: 040b36d6-1f0a-4579-971c-40fbb46ade1d
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 사용자 지정 문서를 저장합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

환경 핸들은 **Save**, **Save As**, 및 **Save All** 명령입니다.  사용자를 클릭할 때  **저장**,  **다른 이름으로 저장**,  **또는 모두 저장** 에 있는  **파일** 메뉴 또는 발생 결과 모두 저장에서 다음 프로세스 솔루션을 닫습니다.  
  
 ![고객 편집기 저장](../../extensibility/internals/media/private.gif "Private")  
저장, 다른 이름으로 저장 및 처리에 대 한 사용자 지정 편집기 모두 저장 명령  
  
 다음 단계에서는이 프로세스를 자세히 설명 합니다.  
  
1.  에 대 한의  **저장** 및  **다른 이름으로 저장** 명령, 환경을 사용 하는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 현재 문서 창의 확인을 서비스 하 고 어떤 항목을 따라서 저장 해야 합니다.  현재 문서 창의 알게 되 면 환경 계층 구조의 포인터와 항목 식별자 \(itemID\)을 실행 문서 테이블에서 문서를 찾습니다.  자세한 내용은 [실행 중인 Document 테이블](../../extensibility/internals/running-document-table.md)를 참조하십시오.  
  
     모두 저장 명령에 대 한 환경 정보를 저장 하려면 모든 항목의 목록을 컴파일하는 데 실행 문서 테이블에 사용 합니다.  
  
2.  솔루션을 받는 시기는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 반복 호출 하는 선택한 항목 집합을 통해 \(노출, 여러 항목을 선택은 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 서비스\).  
  
3.  선택 영역에 있는 각 항목을 솔루션 계층 구조 포인터 사용 호출 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IsItemDirty%2A> 저장 메뉴 명령을 활성화 해야 하는지 여부를 확인 하는 방법입니다.  다음 항목에는 변경 되지 않으면 저장 명령은 사용할 수 있습니다.  계층 표준 편집기를 사용 하는 경우 다음에 대 한 쿼리 계층 대리자 편집기 상태를 호출 하 여 더러운는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.IsDocDataDirty%2A> 메서드가 있습니다.  
  
4.  변경 된 각 선택한 항목에 솔루션 계층 구조 포인터 사용 호출 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> 메서드는 해당 계층에 있습니다.  
  
     경우에 사용자 지정 편집기, 프로젝트 및 문서 데이터 개체 간의 통신 전용입니다.  따라서이 두 개체 간에 지 속성 특별 한 질문이 처리 합니다.  
  
    > [!NOTE]
    >  사용자의 지 속성을 구현 하는 경우 호출 해야 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> 시간을 절약 하는 방법.  이 메서드를 검사 하 여 안전 하 게 파일을 저장할 수 있는지 확인 합니다 \(예를 들어, 파일이 읽기 전용으로 수 없습니다\).  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)