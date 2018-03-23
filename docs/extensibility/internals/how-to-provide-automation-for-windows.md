---
title: '방법: Windows에 대 한 자동화를 제공 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], tool windows
- tool windows, automation
ms.assetid: 512ab2a4-7987-4912-8f40-8804bf66f829
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: aa4b95a67adb4c282d90eafdd237776e7de1c911
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-provide-automation-for-windows"></a>방법: Windows에 대 한 자동화를 제공 합니다.
문서 창과 도구 창에 대 한 자동화를 제공할 수 있습니다. 제공 하는 자동화 개체를 사용 하는 창에 사용할 수 있도록 하 고 환경에 이미 있지 때마다 자동화 좋습니다 작업 목록에서와 마찬가지로 이미 만들어진 자동화 개체를 제공 합니다.

## <a name="automation-for-tool-windows"></a>도구 창에 대 한 자동화
 환경 자동화 기능을 제공 하는 도구 창에는 표준 반환 하 여 <xref:EnvDTE.Window> 다음 절차에 설명 된 대로 개체:

#### <a name="to-provide-automation-for-tool-windows"></a>도구 창에 대 한 자동화를 제공 하려면

1.  호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 메서드를 사용 하 여 환경을 통해 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> 으로 `VSFPROPID` 매개 변수를는 `Window` 개체입니다.

2.  호출자를 통해 도구 창에 대 한 VSPackage 관련 자동화 개체를 요청 하는 경우 <xref:EnvDTE.Window.Object%2A>, 환경 `QueryInterface` 에 대 한 `IExtensibleObject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>, 또는 `IDispatch` 인터페이스입니다. 둘 다 `IExtensibleObject` 및 `IVsExtensibleObject` 제공는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject.GetAutomationObject%2A> 메서드.

3.  환경을 다음 호출 하는 경우는 `GetAutomationObject` 전달 메서드 `NULL`, VSPackage 관련 개체를 다시 전달 하 여 응답 합니다.

4.  호출 하는 경우 `QueryInterface` 에 대 한 `IExtensibleObject` 및 `IVsExtensibleObject` 실패 하는 환경 호출 `QueryInterface` 에 대 한 `IDispatch`합니다.

## <a name="automation-for-document-windows"></a>문서 창에 대 한 자동화
 표준 <xref:EnvDTE.Document> 편집기의 자체 구현을 가질 수 있지만 개체는 환경에서 사용할 수는 <xref:EnvDTE.Document> 개체를 구현 하 여 `IExtensibleObject` 인터페이스에 응답 하 고 `GetAutomationObject`합니다.

 또한 편집기 통해 검색 하는 VSPackage 관련 자동화 개체를 제공할 수는 <xref:EnvDTE.Document.Object%2A> 메서드를 구현 하 여는 `IVsExtensibleObject` 또는 `IExtensibleObject` 인터페이스입니다. [VSSDK 샘플](http://aka.ms/vs2015sdksamples) RTF 문서 관련 자동화 개체를 제공 합니다.

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>