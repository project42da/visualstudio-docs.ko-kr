---
title: "VSTextBuffer 개체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSTextBuffer
helpviewer_keywords:
- VSTextBuffer object, reference
- views [Visual Studio SDK], VSTextBuffer object
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d25551d6af9b2250275713541dc9c9df39ca90ec
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="vstextbuffer-object"></a>VSTextBuffer 개체
텍스트 버퍼 개체는 파일와 일반적으로 연결 되는 유니코드 텍스트 스트림을 나타냅니다. A <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체는 마법사의 경우 핵심 편집기의 컨텍스트 외부에서 사용할 수 있습니다.  
  
 다음 표에서의 인터페이스를 보여 줍니다. `VSTextBuffer`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797)|표준 OLE 인터페이스입니다. 실행 취소/다시 실행 버퍼에 처리에 주로 사용 됩니다.|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|표준 OLE 인터페이스입니다.|  
|[IPersistStream](http://msdn.microsoft.com/library/windows/desktop/ms690091)|표준 OLE 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|복합어 동작 (즉, 단일 실행 취소/다시 실행 단위로 그룹화 하는 동작) 작성할을 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|텍스트 버퍼에 의해 관리 되는 문서 데이터의 지 속성을 사용 하도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|기본 서비스를 제공합니다. 많은 클라이언트에서 사용 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|버퍼를 검색 하는 데 사용 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|제공 읽기 및 쓰기 2 차원 좌표를 사용 하는 능력. `IVsTextBuffer`에서 상속됩니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|제공 읽기 및 쓰기 1 차원 좌표를 사용 하는 능력. `IVsTextBuffer`에서 상속됩니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|버퍼에서 텍스트에 대 한 스트림 지향, 순차적 액세스를 신속 하 고 제공합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|일반 속성 컬렉션에 대 한 액세스를 제공합니다. 가장 중요 한 속성 이름, 또는 버퍼의 모니커를입니다. 이 인터페이스를 사용 하 여 버퍼에서 GUID를 만들고 키로 사용 하 여 난수 데이터를 저장할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|이벤트에 대 한 연결 지점을 지원합니다.|  
  
## <a name="remarks"></a>설명  
 `VSTextBuffer` 에서 일반적으로 발견 되는 `QueryInterface` 에서 호출할 `IVsTextBuffer`합니다. 자세한 내용은 참조 [텍스트 버퍼](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [숫자 값 편집](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)