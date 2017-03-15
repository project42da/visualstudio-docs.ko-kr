---
title: "레거시 언어 Service1의 매개 변수 정보 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스, 메서드 팁"
  - "메서드 팁"
  - "언어 서비스, 매개 변수 정보 도구 설명"
  - "IVsMethodData 인터페이스"
  - "매개 변수 정보 (IntelliSense)"
ms.assetid: f367295e-45b6-45d2-9ec8-77481743beef
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 레거시 언어 서비스의 매개 변수 정보
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

IntelliSense 매개 변수 정보 도구 설명 언어 구문에는 것에 대 한 힌트를 통해 사용자를 제공 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 자세한 내용을 참조 하십시오 [편집기 및 언어 서비스 확장](../../extensibility/extending-the-editor-and-language-services.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
## 매개 변수 정보 표시 도구 설명의 작동 방법  
 편집기에서 문을 입력할 때 VSPackage에 입력 하 고 문의 정의 포함 하는 작은 도구 설명 창이 표시 됩니다. 예를 들어, Microsoft Foundation 클래스 \(MFC\) 문을 입력 하는 경우 \(예: `pMainFrame ->UpdateWindow`\) 여는 괄호 메서드 팁 나타나고의 정의 표시 한 매개 변수를 나열 하려면 키를 누릅니다는 `UpdateWindow` 메서드.  
  
 매개 변수 정보 표시 도구 설명 문 완성와 함께에서 일반적으로 사용 됩니다. 언어 매개 변수 또는 메서드 이름이 나 키워드 후 다른 형식이 지정 된 정보에 대 한 가장 유용 합니다.  
  
 매개 변수 정보 도구 설명 명령 가로채기를 통해 언어 서비스에 의해 시작 됩니다. 언어 서비스 개체를 가로채 사용자 문자를 구현 해야는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스 및 텍스트 보기에 대 한 포인터를 전달 하면 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 를 호출 하 여 구현은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스. 명령 필터에는 코드 창에 입력 하는 명령을 차단 합니다. 사용자에 게 매개 변수 정보를 표시 하는 시기를 알아야 명령 정보를 모니터링 합니다. 문 완성, 오류 표식 및 그에 대 한 동일한 명령 필터를 사용할 수 있습니다.  
  
 언어 서비스 힌트를 제공할 수 있는 키워드를 입력 하는 경우 다음 언어 서비스를 만듭니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow> 개체와 호출 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateTipWindow%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 힌트를 표시 하도록 IDE에 알리는 인터페이스를 합니다. 만들기는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow> 개체를 사용 하 여 `VSLocalCreateInstance` coclass를 지정 하 고 `CLSID_VsMethodTipWindow`합니다.`VsLocalCreateInstance` 함수를 호출 하는 헤더 파일 vsdoc.h에 정의 된 `QueryService` 로컬 레지스트리 및 호출에 대 한 `CreateInstance` 이 개체에 대 한는 `CLSID_VsMethodTipWindow`합니다.  
  
## 메서드 설명 제공  
 호출 메서드 팁을 제공 하려면는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow> 인터페이스를 구현 전달는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> 인터페이스입니다.  
  
 경우에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData> 클래스에서 호출 되 면 해당 메서드는 다음 순서로 호출 됩니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetContextStream%2A>  
  
     현재 텍스트 버퍼의 위치와 관련 된 데이터의 길이 반환합니다. 이렇게 하면 IDE에서이 도구 설명 창의 사용 하 여 해당 데이터를 가리지 합니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetCurMethod%2A>  
  
     처음에 표시 하려는 메서드 수 \(0부터 시작 하는 인덱스\)를 반환 합니다. 예를 들어 0을 반환 하는 경우 다음 첫 번째 오버 로드 된 메서드는 처음에 표시 됩니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetOverloadCount%2A>  
  
     현재 컨텍스트에 적용할 수 있는 오버 로드 된 메서드 수를 반환 합니다. 값을이 메서드에 대 한 1 보다 큰 반환 하는 경우는 텍스트 보기를 표시 합니다 위쪽 및 아래쪽 화살표가 있습니다. IDE를 호출 하는 아래쪽 화살표를 클릭 하는 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.NextMethod%2A> 메서드. IDE를 호출 하는 위쪽 화살표를 클릭 하는 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.PrevMethod%2A> 메서드.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetMethodText%2A>  
  
     매개 변수 정보 도구 설명의 텍스트를 여러 번 호출 하는 동안 생성 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetMethodText%2A> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetParameterText%2A> 메서드.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetParameterCount%2A>  
  
     표시할 메서드의 매개 변수 개수를 반환 합니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.GetParameterText%2A>  
  
     표시 되는 오버 로드와 해당 하는 메서드 값을 반환 하는 경우이 메서드는 호출 하 여 뒤에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.UpdateView%2A> 메서드.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.UpdateView%2A>  
  
     메서드 설명에 표시 되 면 편집기를 업데이트 하 여 언어 서비스를 알립니다. 에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.UpdateView%2A> 메서드를 다음 호출 합니다.  
  
    ```  
    <pTxWin> ->UpdateTipWindow(<pTip>, UTW_CONTENTCHANGED | UTW_CONTEXTCHANGED).  
    ```  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A>  
  
     에 대 한 호출을 받을 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A> 메서드 팁 창의 닫을 때 메서드.