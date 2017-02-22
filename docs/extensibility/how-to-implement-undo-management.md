---
title: "방법: 실행 취소 관리 구현 | Microsoft Docs"
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
  - "편집기 [Visual Studio SDK] 레거시-취소 관리"
ms.assetid: 1942245d-7a1d-4a11-b5e7-a3fe29f11c0b
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 실행 취소 관리 구현
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

실행 취소 관리에 사용 되는 기본 인터페이스입니다 <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager>, 환경에 의해 구현 됩니다.  실행 취소 관리 지원, 별도 실행 취소 단위를 구현 합니다 \(즉, <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit>는 여러 개별 단계를 포함할 수 있습니다.  
  
 실행 취소 관리를 구현 하는 방법를 편집기 다중 뷰 또는 않습니다 지원 여부에 따라 달라 집니다.  각 구현에 대 한 절차는 다음 섹션에서 자세히 나와 있습니다.  
  
## 여기서는 단일 보기 편집기를 지 원하는 경우  
 이 시나리오에서 여러 개의 뷰 편집기를 지원 하지 않습니다.  하나의 편집기와 문서를 있고는 취소를 지원 합니다.  다음 절차에 따라 실행 취소 관리를 구현 합니다.  
  
#### 실행 취소 관리에 대 한 단일 뷰 편집기를 지원  
  
1.  호출 `QueryInterface` 에 있는 `IServiceProvider` 인터페이스에는 창 프레임을 `IOleUndoManager`, 실행 취소 관리자에 액세스 하려면 문서 보기 개체에서 \(`IID_IOLEUndoManager`\).  
  
2.  뷰를 창 프레임에 배치 될 때 호출에 사용할 수 있는 사이트 포인터를 가져옵니다. `QueryInterface` 에 대 한 `IServiceProvider`.  
  
## 위치 여러 개의 뷰 편집기를 지 원하는 경우  
 문서와 뷰 분리 되어 있으면 다음 문서와 연관 된 일반적으로 하나의 실행 취소 관리자가 있습니다.  문서 데이터 개체와 관련 된 하나의 실행 취소 관리자를 모두 실행 취소 단위가 배치 됩니다.  
  
 문서 데이터 개체의 각 보기에 대해 하나씩 실행 취소 관리자를 위한 보기 쿼리 대신 호출 <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> 실행 취소 관리자를 인스턴스화할 수는 clsid\_oleundomanager의 클래스 식별자를 지정 합니다.  클래스 식별자는 OCUNDOID.h 파일에 정의 됩니다.  
  
 사용 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> 직접 실행 취소 관리자 인스턴스를 만들려면 실행 취소 관리자를 환경에 연결 하려면 다음 절차를 따르십시오.  
  
#### 실행 취소 관리자를 환경에 연결 하려면  
  
1.  호출 `QueryInterface` 에서 반환 된 개체에서 <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2> 에 대 한 `IID_IOleUndoManager`.  포인터를 저장할 <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager>.  
  
2.  Call `QueryInterface` on `IOleUndoManager` for `IID_IOleCommandTarget`.  포인터를 저장할 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
3.  릴레이 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 및 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 호출을 저장된 `IOleCommandTarget` 다음 StandardCommandSet97 명령에 대 한 인터페이스.  
  
    -   cmdidUndo  
  
    -   cmdidMultiLevelUndo  
  
    -   cmdidRedo  
  
    -   cmdidMultiLevelRedo  
  
    -   cmdidMultiLevelUndoList  
  
    -   cmdidMultiLevelRedoList  
  
4.  Call `QueryInterface` on `IOleUndoManager` for `IID_IVsChangeTrackingUndoManager`.  포인터를 저장할 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>.  
  
     포인터를 사용 하 여 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager> 를 호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager.MarkCleanState%2A>, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager.AdviseTrackingClient%2A>, 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager.UnadviseTrackingClient%2A> 메서드.  
  
5.  Call `QueryInterface` on `IOleUndoManager` for `IID_IVsLinkCapableUndoManager`.  
  
6.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkCapableUndoManager.AdviseLinkedUndoClient%2A> 사용 하 여 문서에는 또한 구현할는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoClient> 인터페이스입니다.  문서를 닫을 때 호출 `IVsLinkCapableUndoManager::UnadviseLinkedUndoClient`.  
  
7.  문서를 닫을 때 호출 `QueryInterface` 에 대 한 실행 취소 관리자를 `IID_IVsLifetimeControlledObject`.  
  
8.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLifetimeControlledObject.SeverReferencesToOwner%2A>를 호출합니다.  
  
9. 문서를 변경할 때 호출 <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager.Add%2A> 의 관리자와는 `OleUndoUnit` 클래스입니다.  <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager.Add%2A> 메서드 유지 개체에 참조 대개를 해제한 후 오른쪽에 <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager.Add%2A>.  
  
 `OleUndoManager` 클래스는 단일 실행 취소 스택에 인스턴스를 나타냅니다.  따라서 실행 취소 또는 다시 실행에 대 한 추적 데이터 엔터티 마다 하나의 실행 취소 관리자 개체가입니다.  
  
> [!NOTE]
>  실행 취소 관리자 개체는 텍스트 편집기로 광범위 하 게 사용 하는 동안 텍스트 편집기는 지원 되지 않습니다 특정 있는 일반 구성 요소입니다.  다단계 실행 취소 또는 다시 실행을 지원 하려는 경우이 작업을 수행 하려면이 개체를 수 있습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLifetimeControlledObject>   
 [방법: 실행 취소 스택을 지웁니다.](../extensibility/how-to-clear-the-undo-stack.md)