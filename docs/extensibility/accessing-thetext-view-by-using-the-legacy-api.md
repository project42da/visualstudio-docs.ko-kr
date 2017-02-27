---
title: "텍스트 보기에 액세스 하는 레거시 API를 사용 하 여 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-텍스트 보기"
ms.assetid: 8f751f72-c972-4be3-84ee-19c281e02e25
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# 텍스트 보기에 액세스 하는 레거시 API를 사용 하 여
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 뷰 프레젠테이션의 텍스트 버퍼에 저장 된 텍스트입니다.  다음 섹션에 나와 있는 것 처럼 기존 API를 사용 하 여 텍스트가 보기에 액세스할 수 있습니다.  
  
## 텍스트 뷰 개체  
 각 보기는 고유한 텍스트 버퍼를 연결 된 및 버퍼에 있는 데이터의 보기입니다.  다음 다이어그램으로 표시 되며 텍스트 뷰 개체의 핵심 인터페이스를 보여 줍니다. <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>.  
  
 ![Visual Studio 텍스트 뷰 개체](../extensibility/media/vstextview.png "vstextview")  
텍스트 뷰 개체  
  
 보기 버퍼에 텍스트를 표시 하는 방법입니다.  보기에서 보이는 텍스트 버퍼에서는 정확 하 게 표현 되지 않도록 줄 바꿈 및 개요와 같은 기능이 포함 되어 있습니다.  
  
 뷰는 다른 서비스 또는 프로세스를 들어오는 명령을 차단 하 고 보기에서 역할을 수행 하기 전에 사용자에 역할을 할 수 있습니다.  이 작업을 수행 하는 가장 일반적인 서비스는 언어 서비스가입니다.  언어 서비스, 예를 들어, 들여쓰기 사용자 지정 동작이 나 도구 팁을 제공 합니다에 대 한 명령을 차단 해야 합니다.  
  
## 텍스트 보기 기능 추가  
 특정 키 입력을 처리 하 여 텍스트 보기 동작을 사용자 지정할 수 있습니다.  키 입력을 가로채어 하려면 구현 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> 사용자 개체에서 명령 대상 제공 \(<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>\) 모니터 및 절편 명령.  
  
 텍스트 보기에 대 한 필터 명령을 순차적 아키텍처를 사용합니다.  새 명령 필터 \(<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 개체\)를 호출 하 여 시퀀스에 추가 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 메서드.  
  
 텍스트 보기에 대 한 이벤트 알림을 사용 하 여 제공 된는 `T:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents` 인터페이스입니다.  텍스트 보기에 변경 알림을 받으려면 클라이언트 개체에이 인터페이스를 구현 합니다.  텍스트 보기에이 인터페이스를 사용 하 여 노출의 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 인터페이스에서 텍스트 보기 보기에서 변경 알림을 받을 수 있습니다.  
  
## 참고 항목  
 [레거시 API를 사용 하 여 보기 설정 변경](../extensibility/changing-view-settings-by-using-the-legacy-api.md)   
 [텍스트 관리자를 사용 하 여 전역 설정 모니터링](../extensibility/using-the-text-manager-to-monitor-global-settings.md)