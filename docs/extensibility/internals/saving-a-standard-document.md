---
title: "표준 문서 저장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 표준 문서 저장"
  - "프로젝트 [Visual Studio SDK] 표준 문서 저장"
  - "지 속성, 표준 문서 저장"
ms.assetid: d692fedf-b46e-4d60-84bd-578635042235
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# 표준 문서 저장
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

환경 저장, 다른 이름으로 저장 및 모두 저장 명령을 처리합니다.  사용자가 선택할 때  **저장**,  **다른 이름으로 저장**, 또는  **모두 저장** 에서  **파일** 메뉴 또는 있는 솔루션을 닫고는  **모두 저장**, 다음과 같은 프로세스가 발생 합니다.  
  
 ![표준 편집기](../../extensibility/internals/media/public.png "Public")  
저장, 다른 이름으로 저장 및 처리에 대 한 표준 편집기 모두 저장 명령  
  
 다음 단계에서는이 프로세스를 자세히 설명 합니다.  
  
1.  때는  **저장** 및  **다른 이름으로 저장** 명령이 선택 되어, 환경을 사용 하는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 현재 문서 창의 확인을 서비스 하 고 어떤 항목을 따라서 저장 해야 합니다.  현재 문서 창의 알게 되 면 환경 계층 구조의 포인터와 항목 식별자 \(itemID\)을 실행 문서 테이블에서 문서를 찾습니다.  자세한 내용은 [실행 중인 Document 테이블](../../extensibility/internals/running-document-table.md)를 참조하십시오.  
  
     경우는  **모두 저장** 명령을 선택 하면 환경 정보 실행 문서 테이블에 저장 하는 모든 항목의 목록을 컴파일하는 데 사용 합니다.  
  
2.  솔루션을 받는 시기는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 반복 호출 하는 선택한 항목 집합을 통해 \(노출, 여러 항목을 선택은 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 서비스\).  
  
3.  선택 영역에 있는 각 항목을 솔루션 계층 구조 포인터 사용 호출 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IsItemDirty%2A> 확인할 수 있는 방법은 여부는 **Save** 메뉴 명령을 활성화 합니다.  추가 하거나 부적절 한 경우 다음에 **Save** 명령을 사용할 수 있습니다.  계층 표준 편집기를 사용 하는 경우 다음에 대 한 쿼리 계층 대리자 편집기 상태를 호출 하 여 더러운는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.IsDocDataDirty%2A> 메서드가 있습니다.  
  
4.  변경 된 각 선택한 항목에 솔루션 계층 구조 포인터 사용 호출 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> 메서드는 해당 계층에 있습니다.  
  
     표준 편집기를 사용 하 여 문서를 편집 하는 계층 구조에 대 한 일반적입니다.  이 경우 해당 편집기를 지원 해야 합니다 문서 데이터를 개체의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> 인터페이스입니다.  수신 시는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> 메서드 호출 프로젝트를 호출 하 여 문서에 저장 되는 편집기를 알리기 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.SaveDocData%2A> 문서 데이터 개체 메서드를.  편집기를 처리 하는 환경을 수 있습니다는  **다른 이름으로 저장** 를 호출 하 여 대화 상자를 `Query Service` 에 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> 인터페이스.  이에 대 한 포인터를 반환의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 인터페이스입니다.  다음 편집기를 호출 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A> 편집기의 포인터를 전달 하는 메서드, <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> 구현으로는 `pPersistFile` 매개 변수.  환경 다음 저장 작업을 수행 하 고 제공을  **으로 저장** 대화 상자 편집기의.  환경 다음 다시 편집기에서 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>.  
  
5.  사용자 \(즉, 이전에 저장 되지 않은 문서\) 문서를 저장 하려고 하는 경우 다른 이름으로 저장 명령은 실제로 수행 합니다.  
  
6.  다른 이름으로 저장 명령에 대 한 환경 라는 파일 이름을 다른 이름으로 저장 대화 상자를 표시 합니다.  
  
     파일의 이름을 변경 하 고 문서 프레임 업데이트 정보를 호출 하 여 캐시에 대 한 계층 구조를 담당 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A>\(VSFPROPID\_MkDocument\).  
  
 경우는  **으로 저장** 명령으로 문서에서의 위치를 이동 하 고 계층 구조의 문서 위치에 중요 한 것 다음 계층 구조를 다른 계층 구조에 열려 있는 문서 창 소유권 해제 처리를 위해 담당 합니다.  예를 들어, 프로젝트 파일 프로젝트에는 내부 또는 외부 파일 \(기타\) 인지 여부를 추적 하는 경우 발생 합니다.  기타 파일 프로젝트에는 파일의 소유권을 변경 하려면 다음 절차를 따르십시오.  
  
## 파일 소유권 변경  
  
#### 기타 파일 프로젝트에 파일 소유권을 변경 하려면  
  
1.  서비스에 대 한 쿼리는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsExternalFilesManager> 인터페이스입니다.  
  
     포인터를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsExternalFilesManager2> 이 반환 됩니다.  
  
2.  호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsExternalFilesManager2.TransferDocument%2A> \(`pszMkDocumentNew`, `punkWindowFrame`\) 문서를 전송 하는 방법입니다.  이 메서드를 호출 하는 다른 이름으로 저장 명령을 수행 하는 계층 구조입니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)