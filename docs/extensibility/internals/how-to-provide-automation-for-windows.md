---
title: "방법: Windows에 대 한 자동화를 제공 합니다. | Microsoft Docs"
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
  - "자동화 [Visual Studio SDK], 도구 창"
  - "도구 창, 자동화"
ms.assetid: 512ab2a4-7987-4912-8f40-8804bf66f829
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: Windows에 대 한 자동화를 제공 합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

자동화 도구 및 문서 창에 제공할 수 있습니다.  작업 목록을 함께 자동화 개체는 창에 사용할 수 있도록 설정할 때마다 환경이 이미 미리 만들어진 자동화 개체를 제공 하지 않습니다 자동화를 제공 하는 것이 좋습니다입니다.  
  
## 도구 창에 대 한 자동화  
 표준 반환 하 여 환경을 자동화 도구 창에 제공 <xref:EnvDTE.Window> 개체는 다음 절차에서 설명 하는 대로:  
  
#### 자동화 도구를 제공  
  
1.  호출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 메서드를 통해 사용 환경 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> 로 `VSFPROPID` 를 얻으려면 매개 변수는 `Window` 개체입니다.  
  
2.  호출자가 사용자 도구 창을 통해에 대 한 특정 VSPackage 자동화 개체를 요청할 때 <xref:EnvDTE.Window.Object%2A>, 환경 호출 `QueryInterface` 에 대 한 `IExtensibleObject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>, 나는 `IDispatch` 인터페이스입니다.  Both `IExtensibleObject` and `IVsExtensibleObject` provide a <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject.GetAutomationObject%2A> method.  
  
3.  환경 다음 호출 하는 경우는 `GetAutomationObject` 전달 메서드 `NULL`, 다시 VSPackage 특정 개체를 전달 하 여 응답 합니다.  
  
4.  호출 하는 경우 `QueryInterface` 에 대 한 `IExtensibleObject` 및 `IVsExtensibleObject` 환경을 호출 하 고 실패 `QueryInterface` 에 대 한 `IDispatch`.  
  
## 문서 창에 대 한 자동화  
 표준 <xref:EnvDTE.Document> 개체 편집기의 고유한 구현을 지정할 수 있지만 환경에서 사용할 수 있는 것도 `T:EnvDTE.Document` 를 구현 하 여 개체 `IExtensibleObject` 인터페이스 및 응답 `GetAutomationObject`.  
  
 편집기를 통해 검색 된 VSPackage 특정 자동화 개체를 제공할 수 있습니다 뿐만 아니라는 <xref:EnvDTE.Document.Object%2A> 메서드를 구현 하 여,는 `IVsExtensibleObject` 또는 `IExtensibleObject` 인터페이스입니다.  [VSSDK 샘플](../../misc/vssdk-samples.md) RTF 문서 관련 자동화 개체에 기여 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>