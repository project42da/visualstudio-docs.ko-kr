---
title: 레거시 언어 Service1에 매개 변수 정보 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, method tips
- method tips
- language services, parameter info tooltip
- IVsMethodData interface
- Parameter Info (IntelliSense)
ms.assetid: f367295e-45b6-45d2-9ec8-77481743beef
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 50450d1968c626e0a5b32dee4c6f03d005d6ede9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="parameter-info-in-a-legacy-language-service"></a>레거시 언어 서비스에 대 한 매개 변수 정보
IntelliSense 매개 변수 정보 도구 설명 사용자에 게 언어 구문이 있는 곳에 대 한 힌트를 제공 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 된 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 최신 방법입니다. 자세한 내용을 알아보려면 참조 [편집기 및 언어 서비스 확장](../../extensibility/extending-the-editor-and-language-services.md)합니다.  
  
> [!NOTE]
>  편집기를 사용 하 여 새 API 가능한 한 빨리 시작 하는 것이 좋습니다. 언어 서비스의 성능이 향상 되 고 새 편집기 기능을 이용할 수 있도록 합니다.  
  
## <a name="how-parameter-info-tooltips-work"></a>매개 변수 정보 표시 도구 설명의 작동 방식  
 편집기에서 문을 입력할 때 VSPackage에 입력 하 고 문의 정의 포함 하는 작은 도구 설명 창이 표시 됩니다. 예를 들어, Microsoft Foundation 클래스 (MFC) 문을 입력 하는 경우 (같은 `pMainFrame ->UpdateWindow`) 매개 변수를 나열 하 메서드 팁 나타나고의 정의 표시 하려면 왼쪽 괄호 키 누르기는 `UpdateWindow` 메서드.  
  
 매개 변수 정보 표시 도구 설명은 일반적으로 문 완성와 함께에서 사용 됩니다. 언어 매개 변수 또는 다른 형식이 지정 된 작업이 메서드 이름 또는 키워드 뒤에 가장 유용 합니다.  
  
 매개 변수 정보 도구 설명 명령 인터 셉 션을 통해 언어 서비스에서 시작 됩니다. 언어 서비스 개체를 사용자 문자를 가로채기 위해 구현 해야 합니다는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스 및 텍스트 보기에 대 한 포인터를 전달 하면 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 구현을 호출 하 여는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스. 명령 필터에는 코드 창에 입력 하는 명령을 차단 합니다. 사용자에 게 매개 변수 정보를 표시 하는 시기를 알아야 명령 정보를 모니터링 합니다. 문 완성, 오류 표식 등에 대 한 동일한 명령 필터를 사용할 수 있습니다.  
  
 언어 서비스 힌트를 제공할 수 있는 키워드를 입력 하는 경우 다음 언어 서비스 만듭니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow> 개체와 호출은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateTipWindow%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 힌트를 표시할 수 있도록 IDE에 알리는 인터페이스를 합니다. 만들기는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow> 개체 사용 하 여 `VSLocalCreateInstance` coclass를 지정 하 고 `CLSID_VsMethodTipWindow`합니다. `VsLocalCreateInstance` 함수를 호출 하는 헤더 파일 vsdoc.h에 정의 된 `QueryService` 로컬 레지스트리 및 호출에 대 한 `CreateInstance` 에 대 한이 개체에는 `CLSID_VsMethodTipWindow`합니다.  
  
## <a name="providing-a-method-tip"></a>메서드 설명 제공  
 호출 메서드 팁을 제공 하려면는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow> 인터페이스를 구현 전달는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> 인터페이스입니다.  
  
 경우에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> 클래스 호출 되 면 해당 메서드는 다음 순서로 호출 됩니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetContextStream%2A>  
  
     현재 텍스트 버퍼의 위치와 관련 데이터의 길이 반환합니다. 이렇게 하면 IDE에서이 도구 설명 창이 사용 하 여 해당 데이터를 가리지 합니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetCurMethod%2A>  
  
     처음에 표시 하려는 메서드 번호 (인덱스 0부터 시작)를 반환 합니다. 예를 들어 0을 반환 하는 경우 다음 첫 번째 오버 로드 된 메서드는 처음에 표시 됩니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetOverloadCount%2A>  
  
     현재 컨텍스트에 적용할 수 있는 오버 로드 된 메서드의 수를 반환 합니다. 값에이 방법에 대해 1 보다 큰 반환 하는 경우 다음 텍스트 보기 위쪽/아래쪽 화살표 동안 표시 있습니다. IDE 아래쪽 화살표를 클릭 하는 경우 호출 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.NextMethod%2A> 메서드. IDE를 호출 하는 위쪽 화살표를 클릭 하는 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.PrevMethod%2A> 메서드.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetMethodText%2A>  
  
     매개 변수 정보 도구 설명 텍스트를 여러 번 호출 하는 동안 생성 된는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetMethodText%2A> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetParameterText%2A> 메서드.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetParameterCount%2A>  
  
     표시할 메서드의 매개 변수 개수를 반환 합니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetParameterText%2A>  
  
     표시 하려는 오버 로드를 가진에 해당 하는 메서드 값을 반환 하는 경우이 메서드는, 다음에 호출 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.UpdateView%2A> 메서드.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.UpdateView%2A>  
  
     메서드 팁이 표시 될 때 편집기를 업데이트 하려면 해당 언어 서비스를 알립니다. 에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.UpdateView%2A> 메서드를 다음 호출 합니다.  
  
    ```  
    <pTxWin> ->UpdateTipWindow(<pTip>, UTW_CONTENTCHANGED | UTW_CONTEXTCHANGED).  
    ```  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A>  
  
     에 대 한 호출을 수신는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A> 메서드 팁 창의 닫을 때 메서드.