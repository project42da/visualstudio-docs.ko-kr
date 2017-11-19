---
title: "표준 문서 저장 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], saving standard documents
- projects [Visual Studio SDK], saving standard documents
- persistence, saving standard documents
ms.assetid: d692fedf-b46e-4d60-84bd-578635042235
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73ef7f1b347dc2fdcfe2904ef19a2d52036d927e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="saving-a-standard-document"></a>표준 문서 저장
환경이 저장, 다른 이름으로 저장 및 모두 저장 명령을 처리합니다. 사용자가 선택할 때 **저장**, **다른 이름으로 저장**, 또는 **모두 저장** 에서 **파일** 메뉴에 솔루션을 닫고 또는  **모두 저장**, 다음 프로세스가 발생 합니다.  
  
 ![표준 편집기](../../extensibility/internals/media/public.gif "공개")  
다른 이름으로 저장 하 고 모두 저장 명령 표준 편집기에 대 한 처리 저장  
  
 이 프로세스는 다음 단계에 자세히 설명 되어 있습니다.  
  
1.  경우는 **저장** 및 **다른 이름으로 저장** 명령을 선택, 환경을 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 서비스는 현재 문서 창 확인 하 고 따라서 시킨 항목 저장 해야 합니다. 현재 문서 창 확인 되 면 환경을 실행 중인 문서 테이블에서 해당 문서에 계층 포인터와 항목 식별자 (itemID)를 찾습니다. 자세한 내용은 참조 [실행 중인 문서 테이블](../../extensibility/internals/running-document-table.md)합니다.  
  
     경우는 **모두 저장** 명령을 선택한 경우, 환경 정보를 사용 하는 실행 중인 document 테이블에 저장 하는 모든 항목의 목록을 컴파일합니다.  
  
2.  솔루션을 받을 때는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 호출을 반복 하는 선택한 항목 집합 (즉, 다중 선택이 가능한에 의해 노출 된 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 서비스).  
  
3.  각 항목은 선택 영역에 대해 솔루션 포인터를 사용 하는 계층 구조를 호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IsItemDirty%2A> 확인할 수 있는 방법은 여부는 **저장** 메뉴 명령을 활성화 해야 합니다. 항목이 하나 이상의 손상 된 경우 하면 **저장** 명령을 사용할 수 있습니다. 계층 표준 편집기를 사용 하는 경우 다음에 대 한 쿼리 계층 구조 대리자 커밋되지 않음 상태 편집기를 호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.IsDocDataDirty%2A> 메서드.  
  
4.  변경 하는 각 선택된 항목에 솔루션 포인터를 사용 하는 계층 구조를 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> 적절 한 계층에는 메서드.  
  
     표준 편집기를 사용 하 여 문서를 편집 하는 계층에 대 한 일반적인 됩니다. 지원 해야 해당 편집기에 대 한 문서 데이터 개체 하는 경우에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> 인터페이스입니다. 수신 시는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> 메서드 호출에서 프로젝트를 호출 하 여 문서를 저장 하는 편집기 알려야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.SaveDocData%2A> 문서 데이터 개체에서 메서드. 편집기 환경 처리를 허용할 수는 **다른 이름으로 저장** 호출 하 여 대화 상자, `Query Service` 에 대 한는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> 인터페이스입니다. 에 대 한 포인터를 반환 합니다.는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 인터페이스입니다. 편집기는 다음 호출 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A> 메서드를 편집기의에 대 한 포인터를 전달 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> 구현 방법으로 `pPersistFile` 매개 변수입니다. 환경에서 다음 저장 작업을 수행 하 고 제공 된 **다른 이름으로 저장** 편집기에 대 한 대화 상자. 환경을 다음 콜백 편집기에서 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>합니다.  
  
5.  사용자가 문서 (즉, 이전에 저장 되지 않은 문서)를 저장 하려고 하는 경우 이름으로 저장 명령은 실제로 수행 됩니다.  
  
6.  환경 이름으로 저장 명령에 대 한 파일 이름에 대 한 사용자에 게 확인으로 저장 대화 상자를 표시 합니다.  
  
     파일의 이름이 변경 된 경우 계층 구조는 호출 하 여 캐시 된 정보는 문서 프레임의 업데이트에 대해 책임이 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A>(VSFPROPID_MkDocument).  
  
 경우는 **다른 이름으로 저장** 명령으로는 문서의 위치를 이동 하 고 계층 구조는 문서 위치에 중요 한 다음 계층 구조는 다른 계층으로 열려 있는 문서 창의 소유권 전달 하는 일을 담당 합니다. 예를 들어이 프로젝트 파일이 프로젝트를 기준으로 한 내부 또는 외부 파일 (기타) 인지 여부를 추적 하는 경우 발생 합니다. 기타 파일 프로젝트에 파일의 소유권을 변경 하려면 다음 절차를 따르십시오.  
  
## <a name="changing-file-ownership"></a>파일 소유권 변경  
  
#### <a name="to-change-file-ownership-to-the-miscellaneous-files-project"></a>기타 파일 프로젝트에 파일 소유권을 변경 하려면  
  
1.  서비스에 대 한 쿼리는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsExternalFilesManager> 인터페이스입니다.  
  
     에 대 한 포인터 <xref:Microsoft.VisualStudio.Shell.Interop.IVsExternalFilesManager2> 반환 됩니다.  
  
2.  호출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsExternalFilesManager2.TransferDocument%2A> (`pszMkDocumentNew`, `punkWindowFrame`) 메서드를 새 계층에 문서를 전송 합니다. 다른 이름으로 저장 명령을 수행 하는 계층 구조는이 메서드를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [프로젝트 항목 열기 및 저장](../../extensibility/internals/opening-and-saving-project-items.md)