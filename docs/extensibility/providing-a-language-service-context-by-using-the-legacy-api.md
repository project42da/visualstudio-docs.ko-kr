---
title: 레거시 API를 사용 하 여 언어 서비스 컨텍스트를 제공 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - language service context
ms.assetid: daa2df22-9181-4bad-b007-a7d40302bce1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3556fcce3d14d5069854c64d81cb780123a979d2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="providing-a-language-service-context-by-using-the-legacy-api"></a>레거시 API를 사용 하 여 언어 서비스 컨텍스트를 제공 합니다.
사용 하 여 사용자 컨텍스트를 제공 하는 언어 서비스에 대 한 다음과 같은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 편집기: 텍스트 표식 컨텍스트를 제공 하거나 모든 사용자 컨텍스트를 제공 합니다. 각각의 차이점 여기에서 설명 합니다.  
  
 컨텍스트를 사용자 고유의 편집기에 연결 된 언어 서비스 제공에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 편집기에 대 한 컨텍스트를 제공](../extensibility/how-to-provide-context-for-editors.md)합니다.  
  
## <a name="provide-text-marker-context-to-the-editor"></a>편집기 텍스트 표식 컨텍스트를 제공 합니다.  
 텍스트 표식으로 표시 하는 컴파일러 오류에 대 한 컨텍스트를 제공 하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 핵심 편집기를 구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> 인터페이스입니다. 이 시나리오에서는 텍스트 표식에 커서가 있을 때만 언어 서비스 컨텍스트를 제공 합니다. 이렇게 하면 커서를에서 키워드를 제공 하는 편집기는 **동적 도움말** 특성이 없는 창.  
  
## <a name="provide-all-user-context-to-the-editor"></a>편집기에 모든 사용자 컨텍스트를 제공 합니다.  
 언어 서비스를 만들 하 고 사용 하는 경우는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기를 구현할 수 있습니다 다음 핵심는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> 언어 서비스에 대 한 컨텍스트를 제공 하는 인터페이스입니다.  
  
 구현에 대 한 `IVsLanguageContextProvider`, 컨텍스트 모음 (컬렉션) 컨텍스트 모음 업데이트를 편집기에 연결 됩니다. 경우는 **동적 도움말** 창 호출은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserContext.Update%2A> 인터페이스 컨텍스트 모음 유휴 시간에이 컨텍스트 모음에 대 한 업데이트에 대 한 편집기를 쿼리 합니다. 편집기는 편집기를 업데이트 해야 컨텍스트 모음에 대 한 포인터를 전달 하는 언어 서비스 다음에 알립니다. 호출 하 여 이렇게는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider.UpdateLanguageContext%2A> 메서드를 편집기에서 언어 서비스를 합니다. 포인터를 사용 하 여 컨텍스트 모음에, 언어 서비스 이제 추가 및 제거할 수 특성과 키워드가 있습니다. 자세한 내용은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider>을 참조하세요.  
  
 구현 하는 방법에 두 가지가 `IVsLanguageContextProvider`:  
  
-   컨텍스트 모음 하는 키워드를 제공 합니다.  
  
     편집기 상황에 맞는 모음을 업데이트 하려면 호출 되 면 적절 한 키워드 및 특성에 전달 하 고 다음 반환 `S_OK`합니다. 반환 값이 편집기에는 커서를 상황에 맞는 모음에서 키워드를 제공 하는 대신 키워드 및 특성 컨텍스트를 유지 하도록 지시 합니다.  
  
-   커서 위치에 키워드에서 키워드를 가져옵니다  
  
     편집기 상황에 맞는 모음을 업데이트 하려면 호출 되 면 적절 한 특성에 전달 하 고 다음 반환 `E_FAIL`합니다. 반환 값이 편집기에는 컨텍스트 모음에 특성을 보유 하지만 커서 위치에는 키워드와 함께 컨텍스트 모음을 업데이트 하도록 지시 합니다.  
  
 다음 다이어그램은 구현 하는 언어 서비스에 대 한 컨텍스트를 제공 하는 방법을 보여 줍니다. `IVsLanguageContextProvider`합니다.  
  
 ![LangServiceImplementation2 그래픽](../extensibility/media/vslanguageservice2.gif "vsLanguageService2")  
언어 서비스에 대 한 컨텍스트  
  
 다이어그램에서 볼 수 있듯이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 텍스트 편집기에 연결 된 컨텍스트 모음이 있습니다. 이 컨텍스트 모음 세 개의 별도 하위 백 가리키는: 언어 서비스, 기본 편집기 및 텍스트 표식입니다. 언어 서비스 및 텍스트 표식 하위 백 경우 포함 될 특성 및 언어 서비스에 대 한 키워드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageContextProvider> 인터페이스가 구현 된 텍스트의 표식 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerContextProvider> 인터페이스를 구현 합니다. 이러한 인터페이스를 구현 하지 않으면 편집기는 기본 편집기 하위 모음의의 커서 위치 키워드에 대 한 컨텍스트를 제공 합니다.  
  
## <a name="context-guidelines-for-editors-and-designers"></a>편집기 및 디자이너에 대 한 상황에 맞는 지침  
 디자이너와 편집기 편집기 또는 디자이너 창에 대 한 일반적인 키워드를 제공 해야 합니다. 이렇게는 f1 키를 누를 때 디자이너 또는 편집기에 대 한 도움말 항목을 일반, 하지만 적절 하 게 표시 됩니다. 편집기, 이외에 현재 커서 위치에 키워드를 제공 하거나 해야 주요 용어는 현재 선택한 내용에 기반을 제공 합니다. 이 옵션은 텍스트 또는 UI 요소에 대 한 도움말 항목 가리키는 또는 f1 키를 누를 때 표시를 선택한 보장 하기 위해 수행 됩니다. 디자이너에서 폼에 단추와 같은 디자이너에서 선택한 항목에 대 한 컨텍스트를 제공 합니다. 편집기 및 디자이너도에 연결 해야 하는 언어 서비스에 설명 된 대로 [레거시 언어 서비스 Essentials](../extensibility/internals/legacy-language-service-essentials.md)합니다.