---
title: 텍스트 보기에 액세스 하는 레거시 API를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text view
ms.assetid: 8f751f72-c972-4be3-84ee-19c281e02e25
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 534016bda397ca998740c9fcc8252f4efbc8ccc2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="accessing-thetext-view-by-using-the-legacy-api"></a>레거시 API를 사용 하 여 텍스트 보기에 액세스
텍스트 뷰는 텍스트 버퍼에 저장 된 텍스트를 표시 합니다. 다음 섹션에 나와 있는 것 처럼 레거시 API를 사용 하 여 텍스트 보기에 액세스할 수 있습니다.

## <a name="text-view-object"></a>텍스트 뷰 개체
 각 보기 자체 텍스트 버퍼와 연결 되며는 뷰는 버퍼의 데이터에는 창. 다음 다이어그램으로 표시 된 텍스트 뷰 개체의 주요 인터페이스를 보여 줍니다. <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>합니다.

 ![Visual Studio 텍스트 뷰 개체](../extensibility/media/vstextview.gif "vstextview") 텍스트 뷰 개체

 보기는의 버퍼에서 텍스트를 표현 방법입니다. 버퍼에서 텍스트의 정확한 나타내지는 않습니다 보기에 표시 되는 내용 있도록에 개요, 자동 줄 바꿈 등의 기능을 포함 합니다.

 보기에는 다른 서비스 또는 들어오는 명령을 차단 하 고 작업을 수행 보기에 해당 작업을 수행 하기 전에 프로세스를 수 있습니다. 이 작업을 수행 하는 가장 일반적인 서비스는 언어 서비스입니다. 예를 들어 언어 서비스 명령 들여쓰기 사용자 지정 동작 또는 도구 팁을 제공 하려면 ENTER 키를 가로채기 위해 할 수 있습니다.

## <a name="adding-functionality-to-the-text-view"></a>텍스트 보기에 기능 추가
 특정 키 입력을 처리 하 여 텍스트 보기 동작을 사용자 지정할 수 있습니다. 키 입력을 차단 하려면 구현 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> 사용자 개체에 명령 대상을 제공 하 고 (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>) 모니터 및 절편 명령입니다.

 텍스트 보기 명령 필터에 대 한 순차적 아키텍처를 사용합니다. 새 명령 필터 (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 개체)를 호출 하 여 시퀀스에 추가 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 메서드.

 텍스트 보기에 대 한 이벤트 알림을 사용 하 여 제공 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents> 인터페이스입니다. 텍스트 보기에 대 한 변경 알림을 받는 데 클라이언트 개체에서이 인터페이스를 구현 합니다. 이 인터페이스는 텍스트 뷰를 사용 하 여 노출는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 보기에서 변경 알림을 수신 하도록 텍스트 보기에는 인터페이스입니다.

## <a name="see-also"></a>참고 항목

- [레거시 API를 사용 하 여 보기 설정 변경](../extensibility/changing-view-settings-by-using-the-legacy-api.md)
- [전역 설정을 모니터링 하는 텍스트 관리자를 사용 하 여](../extensibility/using-the-text-manager-to-monitor-global-settings.md)