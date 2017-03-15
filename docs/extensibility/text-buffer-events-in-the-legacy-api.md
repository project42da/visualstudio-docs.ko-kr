---
title: "레거시 API에서 텍스트 버퍼 이벤트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-텍스트 버퍼 이벤트"
ms.assetid: 9be49e9f-1864-41c2-8a3c-f66895881341
caps.latest.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 16
---
# 레거시 API에서 텍스트 버퍼 이벤트
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 버퍼 개체가 서로 다른 상황에 대처 하는 데 사용할 수 있는 여러 가지 이벤트를 내보냅니다.  
  
 기존 API를 사용할 때 텍스트 버퍼에 변경 알림을 수신 하려면 다음 인터페이스를 구현 해야 합니다.  인터페이스를 사용 하 여 텍스트 버퍼에 노출의 `IConnectionPointContainer` 인터페이스에서 텍스트 버퍼 줄 알림을 받도록 버퍼에서 변경 합니다.  자세한 내용은 [방법: 레거시 API와 함께 텍스트 버퍼 이벤트에 등록](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)를 참조하십시오.  `IVsTextStreamEvents` 또는 `IVsTextLinesEvents` 인터페이스 변경 내용이 반환 된 어느 하나 또는 2 차원 좌표에 각각.  
  
## 텍스트 버퍼 인터페이스  
 다음 텍스트 버퍼 개체에 의해 구현 된 인터페이스입니다.  
  
|Interface|설명|  
|---------------|--------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|복합 동작 \(즉, 단일 실행 취소\/다시 실행 단위로 그룹화 하는 동작\)을 만들을 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|텍스트 버퍼에서 관리 되는 문서 데이터의 지 속성을 사용 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|기본 서비스를 제공합니다. 많은 클라이언트에서 사용 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|설명 읽기 \/ 쓰기 기능을 사용 하 여 2 차원 좌표입니다.  `IVsTextBuffer`에서 상속됩니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|신속 하 고 스트림 지향, 순차적 액세스 버퍼에 텍스트를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|제공 1 차원 좌표를 사용 하 여 기능을 읽고 있습니다.  `IVsTextBuffer`에서 상속됩니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|일반 속성 컬렉션에 대 한 액세스를 제공합니다.  가장 중요 한 속성은 이름 또는 모니커 버퍼입니다.  사용자 임의 데이터 버퍼를이 인터페이스에서 GUID를 만들고 키로 사용 하 여 저장할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|연결 지점에 대 한 이벤트를 지원합니다.|  
  
## 텍스트 버퍼의 이벤트 인터페이스  
 다음 인터페이스에 대 한 텍스트 버퍼 이벤트 알림입니다.  
  
|Interface|설명|  
|---------------|--------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferEvents>|새 언어 서비스는 텍스트 버퍼에 연결 된 클라이언트를 알립니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferDataEvents>|클라이언트를 텍스트 버퍼 초기화 될 때 텍스트 버퍼에서 데이터를 변경할 때 알립니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStreamEvents>|변경 내용을 기본 텍스트 버퍼 1 차원 좌표에서 클라이언트를 게 알립니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>|클라이언트를 변경 하려면 기본 텍스트 버퍼의 2 차원 좌표를 알립니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserDataEvents>|사용자가 데이터 변경 내용을 클라이언트를 게 알립니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsPreliminaryTextChangeCommitEvents>|이벤트를 트리거하기 위해 마지막 커밋 제스처의 클라이언트에 게 알립니다 하 고 변경할 텍스트 범위를 제공 합니다.  `IVsPreliminaryTextChangeCommitEvents` 인터페이스 Undo 또는 Redo 명령에 응답을 발생 하지 않습니다 것입니다.  실행 취소 관리자가 버퍼에 대해서만 발생 합니다.  `IVsPreliminaryTextChangeCommitEvents`예쁜 목록과 같은 다른 이벤트를 하기 전에 변경 내용을 커밋하기 전에 다른 이벤트 텍스트를 변경 하지 않는 있는지 확인 하기 위해 발생 합니다.  하면 VSPackage 하나 모니터링 해야는 `IVsPreliminaryTextChangeCommitEvents` 인터페이스 또는 `IVsFinalTextChangeCommitEvents` 인터페이스, 하지만 둘 다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFinalTextChangeCommitEvents>|이벤트를 트리거하기 위해 마지막 커밋 제스처의 클라이언트에 게 알립니다 하 고 변경할 텍스트 범위를 제공 합니다.  `IVsFinalTextChangeCommitEvents` 인터페이스 Undo 또는 Redo 명령에 응답을 발생 하지 않습니다 것입니다.  실행 취소 관리자가 버퍼에 대해서만 발생 합니다.  `IVsFinalTextChangeCommitEvents`언어 서비스 또는 편집 완전 한 컨트롤에 있는 다른 개체에만 사용할 수 있습니다.  하면 VSPackage 하나 모니터링 해야는 `IVsPreliminaryTextChangeCommitEvents` 인터페이스 또는 `IVsFinalTextChangeCommitEvents` 인터페이스, 하지만 둘 다.|  
  
## 참고 항목  
 [레거시 API를 사용 하 여 텍스트 버퍼에 액세스](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)   
 [방법: 레거시 API와 함께 텍스트 버퍼 이벤트에 등록](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)