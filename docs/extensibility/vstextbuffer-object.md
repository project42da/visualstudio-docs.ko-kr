---
title: "VSTextBuffer 개체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VSTextBuffer"
helpviewer_keywords: 
  - "VSTextBuffer 개체 참조"
  - "뷰 [Visual Studio SDK] VSTextBuffer 개체"
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# VSTextBuffer 개체
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 버퍼 개체는 유니코드 텍스트 파일을 일반적으로 연관 된 스트림을 나타냅니다. A <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 마법사의 경우 코어 편집기의 컨텍스트 외부에서 개체를 사용할 수 있습니다.  
  
 다음 표에서의 인터페이스를 보여 줍니다. `VSTextBuffer`합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797)|표준 OLE 인터페이스입니다. 실행 취소\/다시 실행 버퍼에 처리에 주로 사용 됩니다.|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|표준 OLE 인터페이스입니다.|  
|[IPersistStream](http://msdn.microsoft.com/library/windows/desktop/ms690091)|표준 OLE 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|음소 동작 \(즉, 단일 실행 취소\/다시 실행 단위로 그룹화 되는 동작\)를 만들 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|텍스트 버퍼에 의해 관리 되는 문서 데이터의 지 속성을 수 있습니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|기본 서비스를 제공합니다. 여러 클라이언트에서 사용 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|버퍼를 검색 하는 데 사용 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|제공 읽기 및 쓰기 2 차원 좌표를 사용 하 여 기능 합니다.`IVsTextBuffer`에서 상속됩니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|제공 읽기 및 쓰기 1 차원 좌표를 사용 하는 능력.`IVsTextBuffer`에서 상속됩니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|텍스트 버퍼에 스트림 지향, 순차적 액세스를 신속 하 고 제공합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|속성의 제네릭 컬렉션에 대 한 액세스를 제공합니다. 가장 중요 한 속성 이름, 또는 버퍼의 모니커를입니다. 이 인터페이스를 사용 하 여 버퍼에서 GUID를 만들고 키로 사용 하 여 임의 데이터를 저장할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|이벤트에 대 한 연결 포인트를 지원합니다.|  
  
## 설명  
 `VSTextBuffer` 에서 일반적으로 발견 되는 `QueryInterface` 에서 호출 `IVsTextBuffer`합니다. 자세한 내용은 참조 [텍스트 버퍼](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [Figures Edit](http://msdn.microsoft.com/ko-kr/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)