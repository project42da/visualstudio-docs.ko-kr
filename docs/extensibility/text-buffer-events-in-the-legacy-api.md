---
title: 레거시 API에서 텍스트 버퍼 이벤트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text buffer events
ms.assetid: 9be49e9f-1864-41c2-8a3c-f66895881341
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ab2812d30c0f02063e9ed3672e9b01855c77da22
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="text-buffer-events-in-the-legacy-api"></a>레거시 API에서 텍스트 버퍼 이벤트
텍스트 버퍼 개체는 다양 한 상황에 응답할 수 있도록 하는 여러 가지 이벤트를 내보냅니다.  
  
 레거시 API를 사용 하는 경우에 텍스트 버퍼에 대 한 변경에 대 한 알림을 수신 하려면 다음 인터페이스를 구현 해야 합니다. 사용 하 여 텍스트 버퍼에 대 한 인터페이스를 노출 된 `IConnectionPointContainer` 버퍼에서 줄의 알림 메시지를 받으려면 텍스트 버퍼에는 인터페이스가 변경 합니다. 자세한 내용은 참조 [하는 방법: 레거시 API를 사용 하 여 텍스트 버퍼 이벤트 등록](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)합니다. 경우 `IVsTextStreamEvents` 또는 `IVsTextLinesEvents` 인터페이스의 경우 변경 내용이 반환 됩니다 어느 하나 또는 two 차원 좌표에서 각각.  
  
## <a name="text-buffer-interfaces"></a>텍스트 버퍼 인터페이스  
 텍스트 버퍼 개체에서 구현한 인터페이스는 다음과가 같습니다.  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|복합 작업 (즉, 단일 실행 취소/다시 실행 단위로 그룹화 하는 작업)를 만들 수 있도록 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|텍스트 버퍼에 의해 관리 되는 문서 데이터의 지 속성을 사용 하도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|기본 서비스를 제공합니다. 많은 클라이언트에서 사용 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|제공 읽기 및 쓰기 2 차원 좌표를 사용 하는 능력. `IVsTextBuffer`에서 상속됩니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|버퍼에서 텍스트에 대 한 스트림 지향, 순차적 액세스를 신속 하 고 제공합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|제공 읽기 및 쓰기 1 차원 좌표를 사용 하는 능력. `IVsTextBuffer`에서 상속됩니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|일반 속성 컬렉션에 대 한 액세스를 제공합니다. 가장 중요 한 속성 이름, 또는 버퍼의 모니커를입니다. 이 인터페이스를 사용 하 여 버퍼에서 GUID를 만들고 키로 사용 하 여 난수 데이터를 저장할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|이벤트에 대 한 연결 지점을 지원합니다.|  
  
## <a name="text-buffer-event-interfaces"></a>텍스트 버퍼 이벤트 인터페이스  
 다음은 텍스트 버퍼 이벤트 알림에 대 한 인터페이스입니다.  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferEvents>|새 언어 서비스 텍스트 버퍼와 연결 된 경우 클라이언트를 알립니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferDataEvents>|텍스트 버퍼를 초기화할 때 및 데이터 텍스트 버퍼에 변경 내용이 있을 때 클라이언트를 알립니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStreamEvents>|1 차원 좌표에서 내부 텍스트 버퍼에 대 한 변경의 클라이언트를 알립니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>|2 차원 좌표에서 내부 텍스트 버퍼에 대 한 변경의 클라이언트를 알립니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserDataEvents>|사용자 데이터에 대 한 변경의 클라이언트를 알립니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsPreliminaryTextChangeCommitEvents>|이벤트를 트리거할 마지막 커밋 제스처의 클라이언트에 알립니다 하 고 변경 하는 텍스트 범위를 제공 합니다. `IVsPreliminaryTextChangeCommitEvents` 인터페이스에 대 한 응답을 취소 하거나 명령을 다시 실행 되지 않습니다. 실행 취소 관리자가 버퍼에 대 한 이벤트만 발생 합니다. `IVsPreliminaryTextChangeCommitEvents` 다른 이벤트는 변경 내용이 커밋되기 전에 텍스트를 변경 하지 않는 되었는지 확인 하기 위해 마땅한 목록 등의 다른 이벤트 전에 발생 합니다. VSPackage 하나를 모니터링 해야 합니다는 `IVsPreliminaryTextChangeCommitEvents` 인터페이스 또는 `IVsFinalTextChangeCommitEvents` 인터페이스 중 하나만 있습니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFinalTextChangeCommitEvents>|이벤트를 트리거할 마지막 커밋 제스처의 클라이언트에 알립니다 하 고 변경 하는 텍스트 범위를 제공 합니다. `IVsFinalTextChangeCommitEvents` 인터페이스에 대 한 응답을 취소 하거나 명령을 다시 실행 되지 않습니다. 실행 취소 관리자가 버퍼에 대 한 이벤트만 발생 합니다. `IVsFinalTextChangeCommitEvents` 언어 서비스 또는 편집 완전히 제어 하는 다른 개체에만 사용을 위한 것입니다. VSPackage 하나를 모니터링 해야 합니다는 `IVsPreliminaryTextChangeCommitEvents` 인터페이스 또는 `IVsFinalTextChangeCommitEvents` 인터페이스 중 하나만 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [레거시 API를 사용 하 여 텍스트 버퍼에 액세스](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)   
 [방법: 레거시 API 사용 하 여 텍스트 버퍼 이벤트 등록](../extensibility/how-to-register-for-text-buffer-events-with-the-legacy-api.md)